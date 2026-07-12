---
type: source
tags: [seo, aeo]
date_published: 2026-07-11
date_ingested: 2026-07-11
origin: raw/articles/google-search-fundamentals-get-started.md
---

# Google Search Fundamentals: Get Started

**Citation:** Google Search Central. "Get Started with Google Search."
https://developers.google.com/search/docs/fundamentals/get-started

## Key takeaways

- **Canonical URLs**: Understand how canonicalization prevents duplicate
  content issues. Canonical tags signal the "true" version of duplicate
  pages.
- **robots.txt is for crawl control, not index control** — use it
  strategically to block unimportant pages, but don't rely on it for
  indexing (use noindex or login requirements instead).
- **Sitemaps are especially valuable for sites with rapidly changing
  content or pages not easily discoverable through links.**
- **Site migrations require step-by-step signaling**: 301 redirects
  first, sitemaps updated, then explicit Google notification via Search
  Console to forward signals.
- **JavaScript rendering happens at crawl time** — content that only
  appears after JS execution is visible to Google, but rendering
  failures are a real crawl failure risk.
- **Mobile-first indexing is the default** — over 60% of traffic is
  mobile, and Google crawls primarily with mobile Googlebot.
- **HTTPS is a confirmed ranking signal and browser trust signal.**
- **Crawlability prerequisites**: proper HTML `<a href>` tags for all
  links, `rel="nofollow"` for paid/untrusted/state-changing links, no
  crawl budget waste on low-value URLs.
- **Structured data helps Google and AI systems understand content type**
  — not required, but enables rich results and better context for
  generation.
- **Search Console is the primary monitoring tool** for indexing status,
  crawl errors, and search performance.

## What this updates in the wiki

- Extended [[technical-seo-audit-checklist]] §1 with additional
  robots.txt and sitemap best practices, and added reminders that
  canonicalization is prevention-focused (use before a duplicate problem
  exists).
- Extended [[technical-seo-audit-checklist]] §4 with official Google
  language on title tags, schema markup, and rich results (reframes
  priority calibration for elements).
- Extended [[technical-seo-audit-checklist]] §2 with explicit guidance
  on mobile-first indexing and the mobile-default crawl pattern.
- Cross-linked from [[how-google-search-works]] as the source for
  site-migration protocols and JS rendering behavior.
- Added reminder in [[link-and-anchor-text-best-practices]] that this
  source provides official crawlability guidance for HTML link markup,
  complementing the Ahrefs/Google-official internal and external linking
  tactics already there.
- No conflicts — reinforces and extends existing guidance with official
  Google documentation; slightly raises priority on mobile and HTTPS in
  audits.
