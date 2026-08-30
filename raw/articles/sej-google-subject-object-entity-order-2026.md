# Google: Subject/Object Entity Order Affects AI Answers

Source: https://www.searchenginejournal.com/google-subject-object-entity-order-affects-ai-answers/586089/
Author: Roger Montti (SEJ Staff)
Publish Date: 2026-08-17

## Research cited

Primary: "Empty Shelves or Lost Keys? Recall Is the Bottleneck for
Parametric Factuality" (arxiv.org/pdf/2602.14080). Secondary: Google's
explainer "Why does recall fail?"

## Primary finding

LLMs *encode* 95-98% of tested facts, but fail to directly *recall*
26-34% of them. The recall bottleneck is not a training-data-coverage
problem — it's a retrieval-from-parameters problem.

## Encoding vs. recall

Frontier models (Gemini-3-Pro, GPT-5) have saturated factual encoding —
they already "know" nearly everything tested. But recall failures
account for more than 70% of GPT-5.2's errors, meaning recall (not
encoding) is now the limiting factor for factual accuracy.

## Subject/object entity reversal

When a fact is encountered in training with a specific entity order
(e.g., "Oasis played their first gig at the Boardwalk club" — Oasis as
subject, Boardwalk club as object), models struggle when a question
reverses that order (asking about the Boardwalk club first, Oasis
second). Models can still recognize the correct answer in
multiple-choice format even when free-recall fails — the information
is encoded but not reliably retrievable by direct recall in the
reversed order.

## Other findings

- **Question rephrasing barely matters** — only subject/object order
  reversal produced a material recall difference; wording variations
  did not.
- **Long-tail (rare) facts show a larger encoding-to-recall gap** than
  popular facts, though both are recall-bottlenecked.
- **"Thinking" (extended reasoning) improves recall**: failure rate
  drops from 26-34% direct to 11-12% when a model's thinking/reasoning
  process is engaged (recovering 40-65% of otherwise-failed recalls).

## Recommended writing tactics (speculative, not proven)

The article suggests — without direct empirical validation — that
ordering subject/object entities in content to match common query
phrasing patterns might improve recall odds. Explicitly flagged as
theoretical, not evidence-backed for SEO purposes specifically.

## Key takeaways

1. Recall, not insufficient training data, is the bottleneck.
2. Entity order matters: models struggle when subject/object
   relationships in a query reverse the order seen in training.
3. Multiple-choice recognition works while free-recall fails —
   confirms information is encoded but poorly accessible.
4. Scaling model size doesn't fix this on its own.
5. SEO/content implications remain theoretical — no direct evidence
   yet that reordering entities in written content changes which
   sources get cited.
