---
type: source
tags: [seo, aeo]
date_published: 2024-02-06
date_ingested: 2026-07-11
origin: raw/articles/ipullrank-optimize-for-sge.md
---

Garrett Sussman, "How to Optimize for AI Overviews" (iPullRank, published 2024-02-06, discussing Google's then-named SGE).

## Key takeaways

- **Note on age**: this is the oldest AEO/GEO-tactics source in the wiki
  (Feb 2024, pre-dating the general AI-Overviews rollout and every
  other source in [[geo-content-optimization-tactics]]). Treat its
  chunk-level framing as a durable mental model but its specific
  case-study results (3 examples) as dated/anecdotal next to the
  large-n studies elsewhere in that playbook.
- **"Fraggles"**: AI Overviews' RAG pipeline retrieves and cites
  text *chunks*, not whole pages — reinforces the wiki's existing
  focused-over-comprehensive guidance
  ([[airops-fan-out-effect-2026]]) with the underlying mechanism:
  optimize the specific chunk/section likely to be retrieved, not just
  the page as a whole.
- **Citation-position data point**: an Authoritas study (1,000 queries)
  found 93.8% of AI Overview citations weren't in top-10 organic
  results, while Mike King's study (90K queries) found citations
  concentrated at organic positions 1, 2, and 9 — the source itself
  flags these as in tension. Distinct from, and not directly
  comparable to, [[ahrefs-why-chatgpt-cites-pages-2026]]'s "88% of
  ChatGPT citations come from the search index" (different engine,
  different metric — search-index-membership vs. organic rank
  position) — noting for context, not resolving as a wiki-level
  conflict.
- **Keyword strategy addition**: supplement seed keywords with People
  Also Ask queries and the platform's own follow-up/related searches —
  a concrete technique to fold into
  [[keyword-mapping-and-cannibalization]]'s "expand keyword variations"
  step when targeting AI Overviews specifically.
- **Content-relevance tooling**: MarketBrew's AI Overviews Visualizer,
  Orbitwise, SurferSEO, and MarketMuse can score a chunk's similarity to
  what's currently being surfaced — target 80%+ similarity to
  top-performing chunks as a practical, testable benchmark before
  publishing.
- **Three AI Overview content-format types** (informational, local,
  shopping) — a page-type taxonomy not previously captured in the wiki;
  useful for deciding which optimization tactics apply (e.g. Shopping
  Graph integration only matters for ecommerce/shopping-format
  queries).

## Updated

- [[geo-content-optimization-tactics]] — added a "chunk-level (Fraggle)
  optimization and relevance-scoring tools" section, folded the PAA/
  follow-up-query keyword tactic in, and noted the AI-Overview
  content-format taxonomy.
