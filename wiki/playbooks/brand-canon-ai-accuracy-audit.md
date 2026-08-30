---
type: playbook
tags: [aeo]
updated: 2026-08-30
---

# Brand Canon: Auditing AI Factual Accuracy About Your Brand

Why/when to use this: use when you need to know whether AI models are
*accurate* about your brand, not just how often they mention it or what
tone they use. Per [[seer-brand-canon-2026]] (28,123 responses across 6
AI models, ~70% factual accuracy baseline), "visibility without
accuracy is being wrong at scale" — a distinct workstream from
[[geo-content-optimization-tactics]]'s "Sentiment monitoring and
correction" (which audits *tone*/framing) and from
[[brand-entity-seo-strategy]] (which builds machine-legible entity
signals rather than auditing what's already being said about the
brand).

## Why a documented ground truth is necessary

Most companies have no reference document that states what's actually
true about them and how they want to be positioned — without one,
"accuracy" has nothing to be measured against, and errors (deprecated
product names, stale analyst citations, competitor confusion) go
undetected until a customer notices.

## The three-layer framework

1. **The Canon (Specification)** — the reference document: true claims
   and desired positioning, each sourced and dated.
2. **Claim Inventory (Test Suite)** — convert the canon into
   falsifiable, checkable assertions, tiered by revenue impact (test
   the claims that matter most to the business first).
3. **Accuracy Score (Test Run)** — run the claim inventory against AI
   platforms and measure pass/fail rates.

## Five canon categories

| Category | Content | Type |
|---|---|---|
| Facts | Company details, leadership, products | Sourced |
| Desired positioning | 2-3 market claims to own | Declared |
| Brand description | Category, customers, elevator pitch | Declared |
| Differentiators | Capabilities and advantages | Both |
| Falsehoods | Retired products, old taglines, competitors | Both |

Build the **Falsehoods** category proactively — predict failure modes
(a discontinued product name, an old tagline, a stale analyst report,
confusion with a similarly-named competitor) rather than waiting to
discover them reactively in a customer conversation.

## Four scoring dimensions

- **Factual correctness** — is the stated fact actually true?
- **Canon alignment** — does the answer match the *desired* positioning,
  not just avoid being factually wrong?
- **Attribution quality** — is the AI's information sourced from
  owned content, credible third-party content, or a competitor's
  content?
- **Hallucination presence** — is there a fabricated claim with no
  traceable source at all?

Note a plausible (not proven) mechanistic contributor for static
pre-trained-data models specifically: per
[[sej-google-subject-object-entity-order-2026]], models can fail to
*recall* a fact even when it's encoded in training, particularly when
a query reverses the subject/object entity order the fact was learned
in — so some factual-correctness failures may be recall failures
rather than missing/absent brand information. See
[[generative-engine-optimization]]'s static-LLM taxonomy section for
the mechanism.

## Fixing what you find: two different timeframes

- **Retrieval fixes (weeks)** — update your own content, correct
  third-party listings (directories, review sites, Wikipedia), and
  optimize pages for exact-query matching so the correct answer is what
  gets retrieved live.
- **Corpus fixes (quarters)** — build an authoritative web footprint
  aimed at the *next* model training cycle. You cannot directly edit a
  model's training data — this only pays off on a training-cycle
  timescale, not immediately.

## Process notes

- **Human review is required.** Don't rely on a model to grade its own
  accuracy — self-assessment isn't statistically reliable.
- **Refresh the canon on a cadence.** A stale canon produces stale
  benchmarking — re-date and re-verify claims periodically, especially
  after product launches, rebrands, or leadership changes.
- **Accurate visibility beats high visibility with low accuracy** — a
  smaller number of correct AI mentions is worth more than a large
  number that are ~30% wrong, outdated, or declined.

## See also

- [[geo-content-optimization-tactics]] — "Sentiment monitoring and
  correction" section: the companion *tone*-auditing workstream.
- [[brand-entity-seo-strategy]] — building the machine-legible entity
  signals (Knowledge Graph, structured data, branded-query strategy)
  that this audit's "corpus fixes" ultimately rely on.
