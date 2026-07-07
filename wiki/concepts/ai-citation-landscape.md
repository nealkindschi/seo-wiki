---
type: concept
tags: [seo, aeo]
updated: 2026-07-07
---

# AI Citation Landscape

Empirical patterns in what generative AI answer engines actually cite in
practice, as distinct from [[generative-engine-optimization]] (which
covers *tactics* for increasing citation-stage visibility). Based on
[[muckrack-generative-pulse-ai-reading-may-2026]], an analysis of 25M+
citation links across ChatGPT, Claude, and Gemini.

## Non-paid, earned media dominates

~99% of citations come from non-paid sources; paid/advertorial content is
just 0.3% of all citations. Journalism accounts for 27% of citations
overall; earned media broadly (journalism, academic/research, government/
NGO, encyclopedic, social, third-party corporate content) accounts for
~84%, with owned + paid content making up the remaining ~16%.

## Providers are three separate information environments

ChatGPT, Claude, and Gemini cite very differently, both in *how often*
and *how much*, and pull from largely non-overlapping sources:

- **ChatGPT**: cites in 96% of responses, ~5 citations each — a
  near-universal but concise citer.
- **Gemini**: cites in 82% of responses, ~8 citations each.
- **Claude**: cites in only 55% of responses (leans on training
  knowledge more), but averages **13** citations when it does go to the
  web — more than twice ChatGPT's depth.

Cross-provider overlap in top cited domains is minimal — Wikipedia is
the only domain that appears near the top for all three. Among
journalism outlets specifically, only Forbes appears in more than one
provider's top 5. Practical implication: optimizing for "generative
engines" as a monolith is misleading — tactics may need to be
provider-specific.

## Wikipedia, Reddit, and YouTube diverge sharply by provider

- **Wikipedia** is a top-3 cited domain in 12/17 industries for ChatGPT,
  8/17 for Claude, but only 3/17 for Gemini. Investment in Wikipedia
  presence benefits ChatGPT and Claude visibility much more than Gemini.
- **Reddit** is Gemini's single most-cited domain (2.4% of all its
  citations) but essentially absent from ChatGPT (~0.003%) and Claude
  (0%).
- **YouTube**: Claude never cites it (0%); it's ~2% of citations for
  both ChatGPT and Gemini.

## The Axios anomaly

Journalism citations are spread across 20,000+ distinct outlets with no
single dominant publication — except Axios, which appears in ChatGPT's
top-3 cited domains across 13 of 17 industries, a level of cross-sector
breakthrough no other outlet or provider combination matches. By
contrast, Reuters and The New York Times don't appear in the top 3 for
any industry, for any provider, and Claude's top journalism outlet
(CNBC) only cracks the top 3 in a single industry. This is consistent
with Axios's short-form, cross-topic coverage model.

## Recency matters

Among journalism citations with a known publish date, 57% were published
within the past 12 months, accelerating from 50%/11 months measured in
Muck Rack's December 2025 report. Citation volume peaks sharply in the
first month after publication and decays quickly through month six,
though a long tail past three years still accounts for a meaningful
share.

## Query type and sector shape citation mix

"Industry Trend" queries cite journalism at 46% — more than twice the
rate of How-To or Comparative queries (~18-19%) — and drive nearly all
press-release citations (1.16% of Industry Trend responses vs. 0.09% for
How To). Journalism citation rate also varies by sector: highest in
Media/Entertainment (36%) and Finance/Insurance (32%), lowest in
Education and Industrial/Manufacturing (~19% each).

## Local queries lean on Google Maps, not articles

For "best of" local queries (best hotels, restaurants, services),
ChatGPT systematically cites Google Maps search results — 188 citations
per 1,000 such queries, averaging ~7 map pins per response — rather than
reviews or editorial content. Claude cited Google Maps only once in the
entire study.

## Citations change what the model actually says

Not just a visibility/attribution mechanism: enabling web citations can
change the substantive correctness of an answer, not just add sources to
an otherwise-fixed response. Example from the source: asked for the
worst MLB team ever, a model without citations answered with an outdated
fact (1962 Mets), while with citations enabled it correctly cited a more
recent record-holder (2024 White Sox). This reinforces
[[google-ai-optimization-guide]]'s framing of generative answers as
grounded in retrieval (RAG), not a static trained "understanding."

## See also

- [[generative-engine-optimization]] — tactics for increasing citation
  visibility once retrieved.
- [[geo-content-optimization-tactics]] — actionable playbook, now
  including provider-specific guidance drawn from this landscape data.
