---
type: concept
tags: [seo, aeo]
updated: 2026-08-12
---

# Rerankers and Passage Selection

The mechanism underneath why some content gets cited by AI answer
engines and other content — even when indexed, ranking, and
retrieved — doesn't. Based on
[[peec-ai-rerankers-for-geo-aeo-2026]]. Complements the empirical
findings in [[ai-citation-landscape]] and [[airops-fan-out-effect-2026]]
(what happens) with the model architecture that produces them (why it
happens).

## The four-stage pipeline

1. **Query planning** — the user's question is rewritten and split into
   multiple search queries ("query fanout" — see
   [[ai-citation-landscape]]'s "Query fanout mechanics" section for the
   engine-injection side of this).
2. **Retrieval (wide net)** — keyword search (BM25, exact word
   matching) and vector search (embeddings, semantic meaning) run in
   parallel; results merge via **Reciprocal Rank Fusion (RRF)**, which
   rewards documents ranking well in both lists.
3. **Reranking (fine sieve)** — a neural model re-scores dozens or
   hundreds of shortlisted candidates against the query; only the
   strongest advance.
4. **Generation** — the LLM writes the answer from surviving passages
   and selects which to cite.

**Diagnostic framework** for a citation failure: no retrieval at all →
indexing/coverage/authority/freshness problem; retrieved but losing →
answer-shape or passage-relevance problem; strong passage but still no
citation → source quality, diversity, or generation-stage behavior.

## Passages are scored independently of pages

Many retrieval systems don't evaluate your page as one URL — parts of
it are retrieved and scored as separate passages/chunks. A strong page
can contain one weak candidate passage; a less authoritative page can
contain the single clearest extractable answer. This is the model-level
mechanism behind the "Fraggle"/chunk-level optimization guidance already
in [[geo-content-optimization-tactics]].

## Bi-encoders vs. cross-encoders

- **Bi-encoders** (embedding models) — embed query and document
  separately into vectors, compare via cosine similarity/dot product.
  Enable millisecond search across millions of documents, but
  fine-grained query-document interactions get blurred. Used for the
  cheap wide net.
- **Cross-encoders** (most rerankers) — process query and passage
  together; every query word attends to every passage word through the
  whole network. Far more accurate, but require a full model run per
  query-passage pair and can't be precomputed. Used for the expensive
  reranking stage on a shortlist only.

This split is *why* the pipeline runs in two stages rather than one: no
single model is both cheap enough to score millions of documents and
precise enough to pick the best few.

## Model families (for context, not endorsement)

- **MS MARCO** — Microsoft's Bing-query dataset with human relevance
  labels; most classic English rerankers are fine-tuned on it (a
  "ms-marco" name signals training lineage, not raw click-log learning).
- **MiniLM / TinyBERT** — compact cross-encoders (23M/33M/~4M params),
  CPU-friendly, good for triage.
- **RoBERTa / XLM-RoBERTa** — BERT trained longer/on more data;
  XLM-RoBERTa is multilingual (2.5TB, ~100 languages) and underlies the
  BGE reranker family.
- **BGE-reranker family** (BAAI) — base/large/v2-m3; v2-m3 handles 100+
  languages and longer inputs, the default multilingual pick.
- **ELECTRA** — trains by detecting fake word replacements; useful as a
  "second opinion" from a different backbone.
- **ModernBERT** (Dec 2024) — 8,192-token context (16x classic BERT's
  512), faster inference; basis for the Ettin family (2025).
- **Qwen3-Reranker** (Alibaba, 2025) — decoder-LLM-based relevance
  judge, instruction-following, 32,000-token input, near the top of
  multilingual retrieval benchmarks.

**No evidence connects any specific open model to any specific
production system** — the author is explicit that this describes how
modern retrieval systems commonly work, not a claim about what ChatGPT,
Google AI Overviews, or Perplexity actually run. OpenAI's documented
**File Search** (800-token chunks, 400-token overlap,
text-embedding-3-large, semantic + keyword search, optional reranker)
is the one concretely documented production pipeline cited.

## Diagnostic reranker families

For content teams testing why a passage isn't winning, not just picking
a production reranker:

- **SPLADE** — expands text into weighted vocabulary terms; relevance =
  sum of matched term weights. The most interpretable family for
  diagnosis (exact term-contribution decomposition), but is
  fundamentally a smart keyword system — doesn't deeply model whether a
  sentence *answers* a question.
- **ColBERT (late interaction)** — embeds each token separately, then
  matches query tokens to document tokens via MaxSim (each query token
  finds its best-matching document token). Reveals per-word alignment
  quality — e.g. a passage can score low because the query word "best"
  only matched "most" in the text, not "best" itself.
- **LLM-based rerankers** — prompted directly ("Does the document
  answer the query? Yes/No"), scored from output-token probabilities.
  Inherit world knowledge and instruction-following, but are 10-100x
  heavier than a MiniLM and the hardest family to inspect.

**Diagnosis method**: run several models from different families and
look for agreement. One model's score is an opinion; five models from
three architectures agreeing is a diagnosis.

## Key experimental findings

1. **Answer-bearing beats topically relevant.** For "what are the best
   aeo tools," a product-description passage scored near-zero on strict
   rerankers while a passage directly naming specific tools scored
   >99% on transformed scales — "about the topic" and "answers this
   query" are measurably different things to a reranker.
2. **Listicles win via answer-shape alignment, not inherent list
   bias.** A good "best X" listicle names several entities, covers
   several attributes, and satisfies multiple fanout sub-queries at
   once — an alternative mechanistic explanation for
   [[listicles-in-ai-search]]'s findings that doesn't require a format
   preference, just intent-to-answer-shape alignment. The practical
   implication is the same either way: match answer shape to intent,
   don't reflexively "turn every page into a list."
3. **Missing concepts hurt more than word order.** Scrambled-query and
   unrelated-control testing found missing concepts mattered more than
   shuffled word order for most tested models.
4. **Attention is not editorial guidance.** ~24% of BGE-large's measured
   attention lands on punctuation/structural tokens ("attention sink,"
   Clark et al. 2019) — a tool showing "the model focused on this one
   word" is often misleading. Prefer, in order: exact score components
   (SPLADE term contributions, ColBERT token alignments), controlled
   rewrite tests (change one thing, re-measure), then attention
   visualization as a hypothesis to validate, not evidence on its own.

## Measurement discipline

- **Three separate metrics, don't blend them**: retrieval exposure
  (does content enter the candidate set at all), candidate/reranker
  strength (position after reranking), citation/mention rate (final use
  in the generated answer). This is a passage-level sharpening of
  [[generative-engine-optimization]]'s brand-level "citation rate /
  mention rate / share of voice" measurement framework.
- **Segment by query intent** — don't average brand, definition, and
  "best X" queries into one score; they have different answer shapes
  and different reranker behavior.
- **Reproducibility**: report model version, query set, locale, date,
  and passage window — without them a reranker score isn't
  reproducible.
- **Score interpretation**: treat sigmoid-transformed logits as
  normalized model scores, not observed citation probabilities. A high
  open-model score helps diagnose content; it doesn't prove a URL will
  be cited.

## Practical tactics

See [[geo-content-optimization-tactics]]'s "Reranker diagnostics for
citation troubleshooting" section for the intent-to-answer-shape
content table, high-impact edits, and what-not-to-do guidance derived
from this mechanism.

## See also

- [[geo-content-optimization-tactics]] — the actionable tactics and
  diagnostic checklist drawn from this mechanism.
- [[ai-citation-landscape]] — the empirical "retrieval rank dominates
  citation" and query-fanout findings this page explains mechanistically.
- [[airops-fan-out-effect-2026]] — the large-scale ChatGPT retrieval
  study whose findings this page's pipeline model explains.
- [[richsanger-ai-overview-patent-insights]] — a patent-specific version
  of the same embedding-distance/relevance-scoring mechanism, for
  Google AI Overviews specifically.
- [[ipullrank-optimize-for-sge]] — the earlier (2024) "Fraggle"/chunk-
  retrieval framing this page updates with current model detail and a
  caution against over-literal chunk-size optimization.
- [[listicles-in-ai-search]] — the listicle-citation findings this
  page's "answer-shape alignment" finding offers an alternative
  mechanistic explanation for.
- [[generative-engine-optimization]] — the brand-level measurement
  framework this page's passage-level metrics sharpen.
