---
type: source
tags: [seo, aeo]
date_published: 2025-12-18
date_ingested: 2026-07-07
origin: raw/articles/google-how-search-works.md
---

# How Google Search Works

**Citation:** Google Search Central. "How Search Works." Last updated
2025-12-18 UTC.
https://developers.google.com/search/docs/fundamentals/how-search-works

## Key takeaways

- Three-stage pipeline: **Crawling** (Googlebot fetches pages) →
  **Indexing** (Google analyzes content and stores it in the index,
  including canonicalization/duplicate-clustering and signal collection)
  → **Serving** (ranking programmatically against hundreds of relevancy
  factors, with results varying by location, device, and query type).
- Neither indexing nor serving is guaranteed, even for
  guideline-compliant pages: "Google doesn't guarantee that it will
  crawl, index, or serve your page."
- Google explicitly renders JavaScript during crawling using a recent
  Chrome version — content that only appears after JS execution is
  visible to Google, but rendering failures are a real risk.
- A page can be indexed (visible in Search Console) yet never appear in
  results — that's a serving-stage failure (irrelevance, low quality, or
  robots meta blocks), distinct from a crawling or indexing failure.
- No pay-for-crawl or pay-for-rank at any stage.

## What this updated in the wiki

- Created [[how-google-search-works]] (concept): the crawl/index/serve
  pipeline, as the technical foundation for "retrieval eligibility"
  referenced elsewhere in the wiki.
- Added a technical crawlability checklist to
  [[geo-content-optimization-tactics]].
- Cross-linked from [[generative-engine-optimization]] and
  [[e-e-a-t-and-page-quality]], both of which reference "technical
  crawlability" without previously defining it.
- No conflicts — foundational technical documentation.
