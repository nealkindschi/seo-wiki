# Wiki Index

Catalog of every page in this wiki, organized by category. Updated by
Claude on every ingest (see `CLAUDE.md`). One line per page: link + a
short summary.

## Concepts

- [[generative-engine-optimization]] — What GEO/AEO is, why traditional SEO tactics don't transfer to generative engines, how visibility is measured, and the equity effect favoring lower-ranked content.
- [[ai-citation-landscape]] — Empirical patterns in what ChatGPT, Claude, and Gemini actually cite: media mix, provider differences, Wikipedia/Reddit/Axios patterns, recency, and query-type/sector effects.
- [[ai-visibility-correlation-factors]] — Which brand/SEO metrics correlate with AI-mention visibility (YouTube mentions strongest, content volume near-zero), platform differences, and cross-platform brand-overlap data.
- [[aio-ctr-impact]] — The traffic/CTR economics of being cited (or not) in Google AI Overviews: the citation premium, the 2026 recovery, query-format AIO-prevalence, and a key impressions-vs-clicks measurement lesson.
- [[e-e-a-t-and-page-quality]] — Google's official Experience/Expertise/Authoritativeness/Trust framework, YMYL, the five Page Quality tiers, and the three AI-era abuse patterns (Scaled Content, Site Reputation, Expired Domain Abuse).
- [[search-intent-and-needs-met]] — Google's query intent taxonomy (Know/Know Simple/Do/Website/Visit-in-person) and the Needs Met rating scale.
- [[google-algorithm-update-history]] — Taxonomy of Google's named ranking updates (core, spam, helpful content, product reviews, page experience, Discover) and the pattern of helpful-content/reviews updates merging into core updates over time. Full dated list in `wiki/timeline.md`.
- [[how-google-search-works]] — The crawl/index/serve pipeline underlying "technical crawlability" and "retrieval eligibility": crawling, canonicalization/indexing, and serving-stage ranking, plus their distinct failure modes.
- [[traditional-seo-ranking-factors]] — Classic organic-SERP ranking correlation data (text relevance strongest, backlinks moderate, keyword-matching/Schema/content-length weak), with a direct comparison to AI-citation correlation factors.

## Playbooks

- [[geo-content-optimization-tactics]] — 9 content tactics ranked by measured visibility impact, plus domain-specific, provider-specific, brand-level correlational, query-format-risk, technical-crawlability, E-E-A-T, and Know-Simple guidance, plus a citability checklist.
- [[controlling-ai-feature-inclusion]] — how to limit/exclude content from Google's AI Overviews/AI Mode (robots.txt, nosnippet, data-nosnippet, max-snippet, noindex), and how to measure the effect.
- [[classic-seo-ranking-factors]] — Actionable classic-SERP ranking tactics (topical coverage, backlink building, reviews, auditing positions 2-20) with a classic-SEO-vs-AEO comparison table.
- [[link-and-anchor-text-best-practices]] — Crawlable link markup requirements, anchor text writing rules, site-structure/siloing/topic-cluster/cornerstone-content and reasonable-surfer internal linking guidance, pagination/crawler-accessibility, an internal-link audit workflow, and `rel` attribute (`nofollow`/`sponsored`/`ugc`) usage. Link count resolved in favor of Google's no-numeric-cap guidance.

## Sources

- [[geo-generative-engine-optimization-aggarwal-2023]] — "GEO: Generative Engine Optimization" (Aggarwal et al., KDD '24 / arXiv 2023) — the founding paper defining GEO/AEO, its visibility metrics, and GEO-bench.
- [[google-ai-optimization-guide]] — Google's official guidance on optimizing for AI Overviews/AI Mode: SEO fundamentals still apply, no special AI infrastructure (llms.txt, chunking) needed.
- [[google-ai-features-appearance-guide]] — Google's guide on how AI Overviews/AI Mode work, how content qualifies to appear, how to measure AI-feature traffic in Search Console, and how to control inclusion.
- [[muckrack-generative-pulse-ai-reading-may-2026]] — Muck Rack's analysis of 25M+ citation links across ChatGPT/Claude/Gemini: media mix, provider citation behavior, Wikipedia/Reddit/Axios patterns, recency, and sector/query-type effects.
- [[ahrefs-ai-brand-visibility-correlations]] — Ahrefs' 75k-brand Spearman-correlation study of brand/SEO metrics vs. AI-mention visibility across ChatGPT, AI Mode, and AI Overviews.
- [[seerinteractive-aio-ctr-impact-2026-update]] — Seer Interactive's 53-brand, 5.47M-query study of AI Overview impact on Google organic/paid CTR: the citation premium, 2026 recovery, and query-format AIO-prevalence.
- [[google-search-quality-evaluator-guidelines-2025-09]] — Google's official Search Quality Rater Guidelines (Sept 2025 edition): the canonical definition of E-E-A-T, YMYL, Page Quality, spam-abuse types, query intent, and Needs Met.
- [[google-search-status-dashboard-history]] — Google's live status dashboard listing ~34 dated ranking updates/incidents from July 2021–June 2026 (snapshot); backfilled the wiki's timeline.
- [[google-how-search-works]] — Google's fundamentals page on the crawl/index/serve pipeline: URL discovery, JS rendering, canonicalization, and why indexing/serving are never guaranteed.
- [[semrush-ranking-factors-study-2024]] — Semrush's 16,298-keyword, 300,000-position classic-SERP correlation study: text relevance strongest, backlinks moderate, keyword-matching/content-length/Schema weak.
- [[google-links-crawlable]] — Google's official guidance on crawlable link markup (`<a href>` requirements), anchor text writing rules, internal/external linking, and `rel` attribute usage.
- [[ahrefs-internal-links-for-seo]] — Ahrefs' internal-linking guide: PageRank/discovery/context functions, site structure (pyramid/siloing/topic clusters), reasonable-surfer link placement, a 3-5-links-per-article density heuristic, and an audit workflow.
- [[yoast-internal-linking-for-seo]] — Yoast's internal-linking guide: pillar-cluster model, cornerstone-content two-way linking, taxonomy/tag-page hubs, related/popular-posts modules, and a GEO framing of internal links as AI context signals.
