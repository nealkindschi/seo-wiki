---
type: source
tags: [seo]
date_published: 2026-07-11
date_ingested: 2026-07-11
origin: raw/articles/google-robots-txt-intro.md
---

# Google: Robots.txt Introduction

**Citation:** Google Search Central. "Robots.txt Introduction."
https://developers.google.com/search/docs/crawling-indexing/robots/intro

## Key takeaways

- **Purpose**: Robots.txt manages crawler traffic and prevents server overload—NOT a security tool or indexing control mechanism.
- **Critical misconception**: robots.txt does NOT prevent indexing. Even blocked URLs can appear in search results if externally linked (they appear "without a description").
- **For web pages (HTML/PDF)**: Can manage crawl allocation and reduce redundant crawling, but cannot hide pages from results.
- **For media**: Can prevent images, videos, and audio from appearing in specialized Google search results.
- **Actual indexing prevention**: Use `noindex` meta tag, `X-Robots-Tag: noindex` header, password protection, or content removal instead.
- **Limitations**: Not all crawlers respect robots.txt; different crawlers interpret syntax differently; blocked pages can still be indexed if externally linked.
- **Security**: robots.txt is NOT a security mechanism. Use password protection for truly private files.

## What this updates in the wiki

- Created new concept [[robots-txt-strategy]] (what robots.txt is, what it isn't, misconceptions, proper use cases)
- Created new playbook [[robots-txt-audit-checklist]] (crawl optimization rules, syntax validation, common mistakes, monitoring via GSC)
- Complements [[google-search-fundamentals-get-started]] (which mentioned robots.txt strategy) with detailed crawl-control guidance
- Cross-links to [[how-google-search-works]] (crawl stage, crawl budget mechanics) and [[technical-seo-audit-checklist]] (crawl validation)
- No conflicts — foundational official guidance reinforcing the "robots.txt ≠ indexing control" principle already referenced in the wiki
