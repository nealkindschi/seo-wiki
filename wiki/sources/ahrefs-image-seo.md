---
type: source
tags: [seo]
date_published: 2020-10-28
date_ingested: 2026-07-11
origin: raw/articles/ahrefs-image-seo.md
---

Joshua Hardwick, "Image SEO: 12 Actionable Tips" (Ahrefs blog, updated 2020-10-28).

## Key takeaways

- Agrees with and substantially extends [[google-images-seo]]'s
  guidance with performance/technical depth Google's own doc doesn't
  cover: concrete compression-tool benchmarks (ImageOptim/ShortPixel/
  TinyPNG), file-type selection rules (JPEG/PNG/GIF/SVG/WebP), lazy
  loading, browser caching, and CDN usage (with a CNAME warning — don't
  link directly from bare CDN URLs, or you lose SEO value to the CDN
  domain).
- **Alt text formula**: complete "This is a(n) ___ of ___" and use the
  result as alt text — a concrete authoring method to pair with
  [[image-seo-checklist]]'s "specific, not keyword-stuffed" guidance.
- **Image sitemap tags**: `<image:loc>`, `<image:title>`,
  `<image:caption>` — adds the actual XML tag names to the wiki's
  existing image-sitemap guidance.
- **SVG for logos/icons**: minify + GZIP-compress; scalable without
  quality loss.
- **Evidence for alt text still mattering despite ML**: Google Cloud
  Vision API nailed cat photos but confused butter for cheese (91%
  confidence) — supports not relying on machine image-understanding
  alone.
- **Bonus tactic (net new)**: link-equity recovery — find backlinks
  pointing directly at image files (via Site Explorer) and request they
  redirect to the source article instead, reportedly high-converting
  outreach.
- No conflicts with [[google-images-seo]]; this source is more tactical/
  tooling-specific, that one more canonical/policy-level.

## Updated

- [[image-seo-checklist]] — added file-type selection table, compression
  benchmarks, the alt-text authoring formula, image-sitemap XML tags,
  SVG/lazy-loading/caching/CDN performance section, and the link-equity
  recovery tactic.
