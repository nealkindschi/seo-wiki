---
type: source
tags: [seo]
date_published: 2026-07-11
date_ingested: 2026-07-11
origin: raw/articles/google-sitemaps-overview.md
---

# Google Sitemaps Overview

**Citation:** Google Search Central. "Sitemaps Overview."
https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview

## Key takeaways

- **Sitemap definition**: XML file listing URLs and metadata, signaling to search engines which pages you consider important and providing details about them.
- **Metadata sitemaps can include**: Last update dates, alternate language versions, video metadata (runtime, ratings, age-appropriateness), image locations, news article titles/publication dates. Metadata enables specialized search features (video results, news results, image results).
- **Sitemap types**: XML (standard), Video, Image, News, Mobile App — each optimized for specific content types.
- **When to create a sitemap**: 500+ pages, newly launched sites with few backlinks, sites with substantial video/image/news content, complex internal linking. NOT needed for small sites (500 pages) with good internal link discovery.
- **Automatic generation**: WordPress, Wix, Blogger, Shopify, Squarespace auto-generate; manually generated sitemaps available via tools/scripts.
- **Critical limitation**: Sitemap inclusion does NOT guarantee indexing. Sitemaps are discovery aids; Google still crawls, renders, evaluates quality independently. Low-quality or robots.txt-blocked pages won't index even if in sitemap.
- **Submission**: Via Google Search Console (primary), robots.txt reference, or manual submission.
- **Monitoring**: Search Console "Sitemaps" report shows submission status, discovered URLs, indexation status, errors/warnings.
- **Size limits**: Standard XML sitemaps: 50,000 URLs max, 50MB uncompressed; use sitemap index files for larger sites.
- **Role in pipeline**: Sitemaps are primarily a *discovery* tool in the crawl→index→serve pipeline; they don't influence ranking directly.

## What this updates in the wiki

- Complements [[google-search-fundamentals-get-started]] (which mentioned sitemaps strategically for crawl budget management). This source provides sitemap-specific deep-dive: metadata types, CMS auto-generation, submission methods, monitoring in GSC.
- Updated [[technical-seo-audit-checklist]] §1 with sitemap submission checklist: verify sitemap exists, check GSC Sitemaps report, confirm GSC sees all important URLs, monitor for errors.
- Cross-linked from [[how-google-search-works]] (crawling stage) — sitemaps as a discovery mechanism that feeds the crawl stage.
- No conflicts — supplementary reference for sitemap-specific implementation. Both this source and Google Fundamentals align on sitemap role and strategy.
