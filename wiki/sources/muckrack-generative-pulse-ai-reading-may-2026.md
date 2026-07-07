---
type: source
tags: [seo, aeo]
date_published: 2026-05-01
date_ingested: 2026-07-07
origin: raw/reports/muckrack-generative-pulse-ai-reading-may-2026.pdf
---

# Generative Pulse: What Is AI Reading? (Muck Rack, May 2026)

**Citation:** Muck Rack, "Generative Pulse: What Is AI Reading? May 2026."
https://media.muckrack.com/documents/What_Is_AI_Reading__May_2026.pdf
(exact publish day not specified by the publisher — cover page only gives
"May 2026"; full report/methodology at https://generativepulse.ai/report/)

## Methodology

Analyzed 25,000,000+ links cited by ChatGPT (OpenAI), Claude (Anthropic),
and Gemini (Google) across a large, diverse set of realistic consumer
prompts, some naming brands explicitly and some not. Every cited URL was
categorized into: Journalistic, Third Party Corporate/Blog (earned),
First Party Corporate/Blog (owned), Press Release, Academic/Research,
Government/NGO, Social/UGC, Aggregators/Encyclopedic, Tech Platforms.
Explicitly built around the same "Generative Engine Optimization (GEO)"
term as [[geo-generative-engine-optimization-aggarwal-2023]].

## Key takeaways

- **~99% of citations come from non-paid media**; paid/advertorial is
  just 0.3%. Journalism = 27% of all citations; earned media overall
  (journalism + academic + gov + encyclopedic + social + third-party
  corporate) ≈ 84%; owned + paid together ≈ 16%.
- **Providers cite at very different frequency and depth**: ChatGPT
  cites in 96% of responses (~5 citations, concise, near-universal
  citer); Gemini cites in 82% (~8 citations); Claude cites in only 55% of
  responses but averages **13** citations when it does — leans on
  training knowledge, dives deep when it goes to the web.
- **Almost no citation overlap between providers** — "three effectively
  separate information environments." Wikipedia is the only domain
  shared at the top across all three. Among journalism outlets, only
  Forbes appears in more than one provider's top 5 (#1 for Gemini, #5 for
  ChatGPT).
- **Wikipedia's importance is provider-specific**: top-3 cited domain in
  12/17 industries for ChatGPT, 8/17 for Claude, only 3/17 for Gemini
  (which leans on Reddit, brand domains, and Quora instead).
- **Reddit** is Gemini's single most-cited domain (2.4% of all its
  citations); ChatGPT cited it 16 times total (~0.003%); Claude 0 times.
- **Claude never cites YouTube** (0%); it's ~2% of citations for
  ChatGPT and Gemini.
- **Axios anomaly**: journalism citations are spread across 20,000+
  distinct outlets, but Axios alone appears in ChatGPT's top-3 cited
  domains across 13 of 17 industries — no other outlet or model
  approaches this. Reuters and The New York Times don't appear in the
  top 3 for any industry, for any provider.
- **Recency matters**: among journalism citations with known publish
  dates, 57% were published within the last 12 months (up from 50%/11
  months in Muck Rack's Dec 2025 report) — citation age peaks sharply in
  month 1 and decays, though a long tail past 3 years persists.
- **Query type shapes citations**: "Industry Trend" queries cite
  journalism at 46% (2x+ the rate of How To/Comparative queries, ~18-19%)
  and drive nearly all press-release citations (1.16% of responses vs.
  0.09% for How To queries).
- **Local/"best of" queries**: ChatGPT cites Google Maps results (not
  reviews or articles) at 188 citations per 1,000 such queries, averaging
  ~7 map pins per response when it appears. Claude cited Google Maps once
  in the entire study.
- **Sector variance in journalism citation rate**: Media/Entertainment
  highest (36%), Finance/Insurance (32%), down to Education and
  Industrial/Manufacturing lowest (~19% each). Full per-sector, per-provider
  top-cited-domains and top-cited-journalists tables for all 17 industry
  sectors are in the source PDF — not reproduced in full in this wiki.
- **Notable appendix finding**: enabling web citations doesn't just add
  sources, it changes the substance of an answer. Example: asked for the
  worst MLB team ever, with citations disabled the model answered "1962
  New York Mets" (outdated); with citations enabled, it correctly named
  the "2024 Chicago White Sox" (current record), citing cbssports.com.

## What this updated in the wiki

- Created [[ai-citation-landscape]] (concept) for the empirical
  citation-composition findings.
- Updated [[geo-content-optimization-tactics]] with a new
  provider/channel-specific tactics section.
- Cross-linked from [[generative-engine-optimization]].
- No conflicts — this data is complementary to and consistent with
  existing wiki content.
