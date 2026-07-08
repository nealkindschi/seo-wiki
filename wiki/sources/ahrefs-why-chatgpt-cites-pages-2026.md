---
type: source
tags: [aeo]
date_published: 2026-04-15
date_ingested: 2026-07-08
origin: raw/studies/ahrefs-why-chatgpt-cites-pages-2026.md
---

# Why ChatGPT Cites One Page Over Another (Ahrefs)

**Citation:** Linehan, Louise; Guan, Xibeijia (reviewed by Ryan Law).
"Why ChatGPT Cites One Page Over Another (Study of 1.4M Prompts)."
Ahrefs Blog. Published 2026-04-15.
https://ahrefs.com/blog/why-chatgpt-cites-pages/
(Methodology: 1.4M ChatGPT prompts, February 2025, ChatGPT 5.2 desktop,
cosine-similarity embeddings approximating semantic relevance,
segmented by reference type.)

## Key takeaways

- ChatGPT cites ~50% of retrieved URLs overall, but citation rate
  varies enormously by **source type**: Search 88.46%, News 12.01%,
  Reddit 1.93%, YouTube 0.51%, Academia 0.40%. ~88% of all citations
  come from the search-index reference type specifically.
- **Reddit is a heavily-used, rarely-cited background resource** —
  67.8% of all non-cited URLs are Reddit; ChatGPT retrieves it
  extensively for context/consensus but almost never attributes to it.
- **Semantic relevance (cosine similarity) is the strongest measured
  differentiator** within a retrieval set: cited pages score 0.602
  prompt-similarity vs. 0.484 for non-cited, and 0.656 against
  ChatGPT's internal fanout sub-queries specifically — directly
  supporting [[peec-ai-chatgpt-query-fanouts-2026]]'s framing that
  content should target fanout sub-questions, not just the surface
  prompt.
- **Natural-language URL slugs** correlate with higher citation
  (89.78% vs. 81.11%).
- **Content-age findings split by source type** — see Conflicting
  Evidence below: within search-result retrieval sets, older/
  established pages (median ~500 days, some 2,700+ days) are cited
  *more* than fresh ones; within the news vertical specifically,
  fresher articles (median ~200 days) are cited more than older ones
  (~300 days), acting as a relevance tiebreaker.
- Methodological caution: naive cited-vs-non-cited metadata
  comparisons (e.g. snippet/date field presence) were initially
  misleading due to compositional bias across reference types —
  segmenting by `ref_type` was necessary to get a clean signal.

## What this updated

- [[ai-citation-landscape]] — added a "Citation rate by source type
  and semantic relevance (ChatGPT)" section.
- [[geo-content-optimization-tactics]] — added semantic-relevance and
  URL-slug tactics; flagged a Conflicting Evidence entry against the
  existing freshness-by-vertical guidance.

## Conflict handling

**Claim in tension**: [[airops-fan-out-effect-2026]] (via
[[geo-content-optimization-tactics]]'s "Freshness by vertical"
section) found an optimal content age of 30-89 days, with citation
declining for content over 2 years old. This source instead finds
that, within search-result retrieval sets specifically, older/
established content (median ~500 days, some 7+ years old) is cited
*more* than fresher content. Logged as unresolved Conflicting Evidence
on [[ai-citation-landscape]] — plausible reconciliation offered
(different retrieval mechanisms/reference types: AirOps' dataset isn't
segmented by source type the way this study is, and this study's news
vertical specifically *does* show a freshness preference, partially
consistent with AirOps), but not resolved since neither source
directly tests the other's segmentation.
