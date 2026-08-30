---
type: source
tags: [aeo]
date_published: 2026-08-17
date_ingested: 2026-08-30
origin: raw/articles/sej-google-subject-object-entity-order-2026.md
---

# Google: Subject/Object Entity Order Affects AI Answers (SEJ)

**Citation:** Montti, Roger (SEJ Staff). "Google: Subject/Object Entity
Order Affects AI Answers." Search Engine Journal. Published
2026-08-17.
https://www.searchenginejournal.com/google-subject-object-entity-order-affects-ai-answers/586089/
Primary research: "Empty Shelves or Lost Keys? Recall Is the Bottleneck
for Parametric Factuality" (arxiv.org/pdf/2602.14080); secondary source:
Google's "Why does recall fail?" explainer.

## Key takeaways

- **Encoding vs. recall are different problems.** Frontier models
  (Gemini-3-Pro, GPT-5) encode 95-98% of tested facts — they already
  "know" nearly everything — but fail to directly *recall* 26-34% of
  them. Recall failures account for >70% of GPT-5.2's errors: recall,
  not training-data coverage, is the current bottleneck.
- **Subject/object entity order reversal breaks recall.** A fact
  learned as "Oasis played their first gig at the Boardwalk club"
  (Oasis=subject, Boardwalk club=object) is harder for the model to
  recall correctly when a question reverses that order. Models can
  still recognize the right answer in multiple-choice format even when
  free-recall fails — the fact is encoded but not reliably retrievable
  in the reversed direction.
- **Question rephrasing barely matters** — only subject/object order
  reversal produced a material recall difference, not general wording
  changes.
- **Long-tail facts have a larger encoding-recall gap** than popular
  facts.
- **"Thinking"/extended reasoning substantially improves recall**:
  failure rate drops from 26-34% (direct) to 11-12% when reasoning is
  engaged.
- **Scaling doesn't fix this** — it's a retrieval-from-parameters
  limitation, not something bigger models automatically resolve.
- **SEO/content implications are explicitly flagged as speculative** by
  the source itself — no direct evidence yet that reordering
  subject/object entities in written content changes which sources get
  cited or how accurately a model recalls facts about them.

## What this updated

Extended [[generative-engine-optimization]]'s "Static pre-trained-data
LLMs" taxonomy category with a new subsection on the encoding-vs-recall
distinction and entity-order sensitivity — this is a parametric-memory
mechanism specific to that category (static/training-data-answering
LLMs), distinct from the retrieval/RAG mechanisms (chunk retrieval,
embedding-distance verification) already documented for
search-augmented and AI-Overview-style engines elsewhere in the wiki.
Also cross-linked as a plausible (not proven) mechanistic contributor to
[[brand-canon-ai-accuracy-audit]]'s ~30% AI factual-inaccuracy finding —
recall failure on subject/object reversal could explain some errors
even where correct information exists in a model's training data. Added
the tactic to [[geo-content-optimization-tactics]] explicitly marked
speculative/unproven, per the source's own caveat. No conflicts.
