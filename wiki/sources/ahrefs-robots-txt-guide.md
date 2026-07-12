---
type: source
tags: [seo]
date_published: 2026-07-11
date_ingested: 2026-07-11
origin: raw/articles/ahrefs-robots-txt-guide.md
---

# Ahrefs: Robots.txt and SEO Implementation Guide

**Citation:** Ahrefs. "Robots.txt and SEO: Complete Guide."
https://ahrefs.com/blog/robots-txt/

## Key takeaways

- **File structure**: Root directory only (`domain.com/robots.txt`), ~500KB max size, new lines per directive
- **User-agents**: Googlebot, Googlebot-Image, Bingbot, Slurp, Baiduspider, DuckDuckBot; wildcard `*` for all crawlers
- **Directives**: `Disallow` (block paths), `Allow` (permit subdirs within blocked areas), `Sitemap` (reference location)
- **Trailing slashes matter**: `/de/` blocks only that directory; `/de` unintentionally blocks `/designer-dresses/` and `/delivery-information.html`—one character can damage SEO
- **Pattern matching**: Wildcards (`*`) and end-of-string (`$`) for specificity; comments with `#` for clarity
- **Subdomain strategy**: Separate robots.txt per subdomain to avoid conflicts
- **Dangerous mistakes**: Overly broad directives, incorrect trailing slashes, blocking important pages accidentally
- **GSC auditing**: Use Coverage report + URL Inspection tool to find submitted URLs blocked by robots.txt or indexed content that shouldn't be
- **Limitation**: Can't prevent indexing if externally linked (same as [[google-robots-txt-intro]]); use `noindex` instead

## What this updates in the wiki

- Extends [[robots-txt-audit-checklist]] with specific syntax rules, user-agent list, directive examples, pattern-matching guidance, and dangerous-mistake warnings
- Extends [[robots-txt-strategy]] with user-agent breakdown and directive types (Disallow/Allow/Sitemap)
- Provides practical implementation details complementing [[google-robots-txt-intro]]'s conceptual foundation
- Cross-links to both existing pages; no conflicts — Ahrefs' tactical guidance operationalizes Google's strategic framework with concrete syntax rules and error scenarios
