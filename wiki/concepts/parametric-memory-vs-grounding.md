---
type: concept
tags: [aeo]
updated: 2026-10-08
---

# Parametric Memory vs. Web-Search Grounding

An AI assistant can put a brand or fact into an answer by two different
routes, and they behave differently for visibility:

- **Parametric memory** — knowledge stored in the model's weights during
  pre-training, recalled with no lookup. Term from Lewis et al.'s 2020
  RAG paper, contrasted with non-parametric memory (an external index
  searched at request time).
- **Web-search grounding** — the model runs a live search, reads what
  comes back, and cites some of it. The "dynamic memory layer" of AI
  assistants, and per [[dejan-link-building-outreach-ai-search]] the most
  significant type of retrieval is grounding with organic search.

## Parametric memory

- **Where it sits**: spread across weights, not addressable records.
  Feed-forward layers act as key-value memories (Geva et al., 2021);
  ROME (Meng et al., 2022) traced and edited single facts in middle-layer
  MLP weights.
- **How much fits**: ~2 bits per parameter when a fact appears ~1,000
  times in training, ~1 bit at ~100 exposures (Allen-Zhu & Li, 2024).
  A 7B-parameter model holds roughly 1.75 GB of factual content.
  **Exposure count is the binding constraint** — a fact seen a few times
  is encoded weakly or not at all; one repeated across many sources is
  recalled reliably.
- **Frozen at the knowledge cutoff**: changing it needs fine-tuning,
  further pre-training, or weight editing — none run per query. A model
  can know today's date and still hold a world months or years old.
- **Failure mode**: a weakly encoded fact still yields fluent text,
  because the weights carry no "never stored" signal — the mechanism
  behind hallucination.

## Grounding funnel

Every platform runs: pages **received** → pages with **readable**
content → pages **cited**. The received-to-cited gap is where platforms
differ. DEJAN's single-query head-to-head (anecdotal, n=1):

| Platform | Received | Cited |
|---|---|---|
| Google | 7 | 7 |
| OpenAI | 39 | 2 |
| Anthropic | 14 | 9 |

Directionally consistent with the provider-level breadth-vs-depth
differences in [[ai-citation-landscape]], but not evidence on its own.

## Implications for SEO/AEO

- **Widely and consistently mentioned brands** get answered from
  memory — with no citation and no link back. Repetition across many
  independent sources is what gets a fact encoded, which is one
  mechanism behind off-site mention correlations in
  [[ai-visibility-correlation-factors]].
- **Newer or less-mentioned brands** exist for the model only through
  retrieval, so crawlability, freshness, and surviving the funnel
  (retrieved → readable → cited) are everything. See
  [[how-google-search-works]] and [[ai-overview-grounding-and-fidelity]].
- Because grounding leans on organic search, AI visibility and organic
  visibility are tightly coupled — and so are their link-building
  inputs. Placed mentions aimed at AI answers face the same
  incongruence detection as placed links; see
  [[editorial-link-integration]].
- Agent research appears to lean much more heavily on retrieval than
  memory: [[ora-ax-is-the-new-aeo-2026]] found training data supplied
  only 7–10% of agent answers.

## See also

- [[generative-engine-optimization]] — the static vs.
  search-augmented vs. reasoning LLM taxonomy.
- [[agent-experience-ax]] — agent-researched answers and own-site
  readability.
