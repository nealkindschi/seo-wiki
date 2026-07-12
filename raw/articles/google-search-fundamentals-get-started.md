# Google Search Fundamentals: Get Started

**Source:** https://developers.google.com/search/docs/fundamentals/get-started
**Type:** Official Google documentation
**Accessed:** 2026-07-11

## Overview

Google's authoritative guide to maintaining website SEO through technical practices, crawling optimization, and user experience management. Foundational reference material for understanding how Google discovers, indexes, and ranks content.

## Core Topics

### Controlling Crawl and Indexing

**Canonical Pages and Duplicates**
- Understand canonical URLs to prevent duplicate content issues
- Canonical tags signal the "true" version of duplicate content

**Resource Accessibility**
- Ensure images, CSS, and other resources aren't blocked by robots.txt
- Google must be able to crawl any resources meant for indexing

**Robots.txt Best Practices**
- Use robots.txt strategically to block duplicate/unimportant content
- Don't use robots.txt for indexing control — use noindex or login requirements instead
- Robots.txt controls crawling, not indexing

**Sitemaps Strategy**
- Signal importance and enable crawling of non-textual content
- Especially important for rapidly changing content
- Helpful for pages that might not be discovered through links alone

### Multilingual and International Considerations

- Implement hreflang tags for language variations
- Understand locale-adaptive page behavior
- Follow multi-regional site management guidelines

### Site Migration Protocols

**Single URL Moves**
- Implement 301 redirects for permanent changes
- Use 302 redirects for temporary moves
- Return true 404 errors when pages are removed

**Full Site Migration**
- Implement all 301s and sitemap changes first
- Then tell Google about the move to facilitate proper signal forwarding

### Crawling Best Practices

- Make all links crawlable with proper HTML `<a>` tags
- Apply `rel="nofollow"` to paid, login-required, or untrusted content
- Manage crawl budget for large sites by prioritizing important pages
- Follow JavaScript recommendations for modern websites
- Provide paginated alternatives to infinite scroll
- Block URLs that change site state (comments, purchases, account creation)

### Content Understanding

**Structured Data Implementation**
- Add structured data to help Google parse content types
- Options: hand-coding, Structured Data Markup Helper, Data Highlighter tool

**Content-Specific Guidelines**
- **Videos:** Follow video best practices for discoverability
- **Images:** Implement image metadata; use robots.txt for indexing control when needed
- **News Sites:** Create news sitemaps, use flexible sampling for paywalled content, prevent abuse
- **Child-Directed Content:** Tag appropriately for COPPA compliance

### User Experience Management

**Security and Speed**
- Google recommends HTTPS for improved user and site security
- Page speed significantly impacts rankings
- Fast performance is a ranking signal

**Mobile Optimization**
- Over 60% of internet traffic comes from mobile devices
- Mobile-friendliness is critical for rankings
- Google now uses mobile crawlers as the default

### Search Appearance Control

Optimize how your content appears in search results through:
- Favicon implementation
- Publication dates
- Title link optimization
- Snippet customization using meta tags
- Implementation of rich results for applicable content types

### Monitoring with Search Console

- Track performance metrics
- Monitor indexing status
- Identify crawl errors
- Analyze search traffic patterns
- Measure impact of changes
