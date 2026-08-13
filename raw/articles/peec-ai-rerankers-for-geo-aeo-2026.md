---
title: "Rerankers for GEO/AEO: How AI search chooses passages and sources"
author: Metehan Yesilyurt
publication: Peec AI Blog
url: https://peec.ai/blog/rerankers-for-geo-aeo-how-ai-search-chooses-passages-and-sources
date_published: 2026-08-06
date_fetched: 2026-08-12
---

# Rerankers for GEO/AEO: How AI search chooses passages and sources

**Publication Date:** August 6, 2026
**Author:** Metehan Yesilyurt (Peec AI)

## Executive Summary

Explains how reranker models act as gatekeepers in AI search systems,
determining which passages/sources get cited even after a page is
indexed, ranks, and is retrieved. Distinguishes retrieval (discovery),
passage selection (reranking), and answer generation as separate
decision stages, and gives a diagnostic framework for why content loses
citations despite good rankings.

## Core AI search pipeline architecture (four stages)

1. **Query Planning** — user questions are rewritten and split into
   multiple search queries ("query fanout").
2. **Retrieval (wide net)** — keyword search (BM25, exact word
   matching) and vector search (embeddings, semantic meaning) run in
   parallel; results merge via Reciprocal Rank Fusion (RRF), which
   "rewards documents that rank well in both lists."
3. **Reranking (fine sieve)** — a neural model re-scores dozens/hundreds
   of candidates against the query; strongest candidates advance.
4. **Generation** — the LLM writes the answer from surviving passages
   and selects which to cite.

**Diagnostic framework**:
- No retrieval → indexing, coverage, authority, or freshness issue.
- Retrieved but losing → answer-shape or passage-relevance problem.
- Strong passage but no citation → source quality, diversity, or
  generation-stage behavior.

## Reranker function

After retrieval shortlists candidates, "a neural reranker usually reads
each candidate against the user's query and assigns a relevance score."
Some systems also draw on click/engagement signals (as documented for
classic Google web ranking), so neural relevance scoring is "an
important gate, not the only gate." Passages, not just whole pages, are
often scored independently — a strong page can contain a weak candidate
passage, and a weaker page can contain the clearest extractable answer.

## BERT and transformer fundamentals

- **BERT** (Google, Oct 2018) — bidirectional reading; trained via
  masked language modeling (hide 15% of words, guess them).
- **Bi-encoders** — embed query and document separately into vectors,
  compare via cosine similarity/dot product; fast (millisecond search
  across millions of docs) but fine-grained interactions get blurred.
- **Cross-encoders** (most rerankers) — process query+passage together;
  every query word attends to every passage word; far more accurate but
  can't be precomputed and require a full model run per pair. This is
  why the pipeline runs in two stages: bi-encoders/BM25 cast a cheap
  wide net, cross-encoders re-score the shortlist expensively.

## Model families

- **MS MARCO** — Microsoft's Bing-query dataset with human relevance
  labels; most classic English rerankers are fine-tuned on it (a
  "ms-marco" model name signals lineage, not that it learned from raw
  click logs).
- **MiniLM/TinyBERT** — compact cross-encoders (23M/33M/~4M params),
  CPU-friendly, good for triage.
- **RoBERTa / XLM-RoBERTa** — BERT trained longer/more data; XLM-R is
  multilingual (2.5TB, ~100 languages), basis for BGE rerankers.
- **BGE-reranker family** (BAAI) — base (278M), large (560M, "most
  popular open reranker in the world"), v2-m3 (568M, 100+ languages,
  longer inputs, default multilingual recommendation).
- **ELECTRA** — trains by detecting fake word replacements; useful as a
  "second opinion" from a different backbone.
- **ModernBERT** (Dec 2024) — 8,192-token context (16x classic BERT's
  512); Ettin family (Johns Hopkins, 2025) built on its recipe.
- **Qwen3-Reranker** (Alibaba, 2025) — decoder-LLM-based relevance
  judge, follows instructions, 32,000-token input, 0.6B/4B/8B sizes,
  near top of multilingual retrieval benchmarks.

## Alternative reranker families for diagnosis

- **SPLADE** — expands text into weighted vocabulary terms; relevance =
  sum of matched term weights. Most interpretable for content diagnosis
  (exact term-contribution decomposition) but is "fundamentally a very
  smart keyword system" — doesn't deeply model whether a sentence
  answers a question.
- **ColBERT (late interaction)** — embeds each token separately, then
  matches query tokens to document tokens via MaxSim (each query token
  finds its best partner). Shows per-word alignment quality — e.g. a
  passage scoring 0.36 average similarity revealed the query word
  "best" only matched "most" in the passage, not "best" itself.
- **LLM-based rerankers** (e.g. Qwen3-Reranker) — prompted "Does the
  document answer the query? Yes/No," scored from output-token
  probabilities. Inherit world knowledge and instruction-following but
  are 10-100x heavier than a MiniLM and hardest to inspect.

## Key findings from reranker testing

1. **Answer-bearing beats topically relevant.** For "what are the best
   aeo tools," a product-description passage scored very low on strict
   models while a passage directly naming specific tools scored >99%
   on transformed scales — "about the topic" and "answers this query"
   are different evaluations.
2. **Listicles win via answer shape, not inherent bias.** A good "best
   X" listicle names several entities, covers several attributes,
   answers comparison sub-queries, and satisfies multiple fanout
   queries at once. The principle is intent-to-answer-shape alignment,
   not "turn every page into a list."
3. **Missing concepts matter more than word order.** Scrambled-query and
   unrelated-control testing showed missing concepts hurt scores more
   than shuffled word order for most tested models.
4. **Passage quality can be a local bottleneck**, distinct from
   page-level authority — some RAG products (e.g. File Search) retrieve
   chunks; web systems can combine page- and passage-level signals.
5. **Attention is not editorial guidance.** ~24% of BGE-large's measured
   attention lands on punctuation/structural tokens ("attention sink,"
   Clark et al. 2019) — attention visualizations can be misleading.
6. **Model disagreement reveals, not defeats.** One permissive model
   accepting a weak passage while strict models reject it is diagnostic
   signal, not noise to average away.

## Evidence about production systems

**Documented**: OpenAI File Search chunks at 800 tokens (400-token
overlap), embeds with text-embedding-3-large, runs semantic + keyword
search, then an optional reranker. ChatGPT Web Search uses a mix of
third-party search providers (Microsoft Bing named among them) plus
OpenAI-partner content. Google and Bing have both publicly described
BERT-based/transformer-based ranking; Google has described passage-based
ranking within pages.

**What cannot be concluded**: there isn't enough public evidence to name
which open model is closest to what ChatGPT runs internally. No evidence
OpenAI uses Qwen3-Reranker or any specific BGE/MiniLM checkpoint —
these are presented as useful open examples, not evidence of actual
usage.

## Practical model-selection guide

- **Explainability**: SPLADE first, then ColBERT.
- **Max accuracy, GPU available**: Qwen3-Reranker 4B/8B.
- **CPU/high-volume/low-latency**: ms-marco-MiniLM-L-6-v2 (or a managed
  API, ~$0.00001/request).
- **Non-English content**: BGE-reranker-v2-m3 or Qwen3-Reranker — don't
  trust ms-marco English models on non-English text; they degrade
  quietly rather than failing loudly.
- **Long documents**: ModernBERT/Ettin or LLM-based rerankers.
- **Two-stage baseline**: BM25 + bi-encoder merged via RRF, then a
  reranker on the top 50-100 candidates.
- **Diagnosis**: run several models from different families and look
  for agreement — one model's score is an opinion, five models from
  three architectures agreeing is a diagnosis.

## Content strategy: intent-to-answer-shape mapping

| Query intent | Answer shape | Citeable requirements |
|---|---|---|
| "What is X?" | Concise definition | Entity name, category, distinguishing facts, sourceable support |
| "Best X for Y" | Shortlist with criteria | Named options, inclusion criteria, trade-offs, audience fit, current evidence |
| "X vs Y" | Like-for-like comparison | Same criteria applied to both, differences stated directly |
| "How to do X" | Ordered procedure | Prerequisites, steps, expected outcome, exceptions |
| Price/date/status | Direct fact with timestamp | Exact value, effective date, primary source, update context |

**High-impact edits**: add a direct-answer sentence in the first two
lines of each target section; name the subject explicitly (replace
"it"/"this tool" pronouns); cover missing decision criteria only when
they belong in the answer; make sections self-contained so any window
survives alone; use question-form subheadings for query-targeted
sections.

**What NOT to do**: don't micro-optimize chunk sizes (every system
chunks differently, you can't control it); don't make every paragraph
robotic ("content that wins the reranker but loses the reader is a net
loss"); don't sacrifice persuasive flow on conversion/landing pages —
their job is converting humans, not winning a reranker score.

## Measurement and reporting framework

**Diagnostic workflow (7 steps)**: (1) define query cluster/intent,
keep brand/definition/comparison/selection/how-to separate; (2) collect
passage-level candidates (your section + competitor passages currently
cited); (3) locate the failure stage (discovery vs. passage relevance
vs. final source use); (4) run multiple model families — one
cross-encoder + SPLADE/ColBERT, plus an LLM reranker for complex
intent; (5) read the strongest evidence (exact term contributions,
token alignments; treat attention as hypothesis only); (6) make the
smallest useful rewrite; (7) validate twice — re-score against the same
competitors, then monitor real outcomes over time.

**Three separate metrics, don't blend them**: retrieval exposure
(whether content enters the candidate set), candidate/reranker strength
(position after reranking), citation/mention rate (final use in the
generated answer).

**Reproducibility**: report model version, query set, locale, date, and
passage window — without them a reranker score isn't reproducible.
Treat sigmoid-transformed logits as normalized model scores, not
observed citation probabilities.

## Scope and limitations (author's own caveats)

"This guide describes how modern retrieval systems commonly work. It's
not a claim that ChatGPT, Google AI Overviews, or Perplexity use any
specific open-source model." "A high open-model score helps you
diagnose content but it doesn't prove a URL will be cited." "Reranker
percentages don't guarantee a citation. They are mainly used to sort
available passages by relevance within one model and query."
