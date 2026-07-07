# Technical SEO Checklist for Search Engines and AI Search

Source: https://www.semrush.com/blog/technical-seo-checklist/
Author: Tushar Pol (Contributors: Faizan Ali, Chris Hanna)
Published: 2026-06-23
Fetched: 2026-07-07

## Overview

Technical SEO now serves dual purposes: traditional search engine
optimization and AI system accessibility. "The fundamentals that help
search engines find and understand your site are the same ones that
determine whether AI systems can access and use your content."

## Section 1: Crawling and Indexing Issues

**Check indexing status**: use Google Search Console (GSC) "Pages"
report to verify indexed vs. excluded pages. Common exclusion reasons:
- Crawled - currently not indexed: low-quality content or duplicate
  pages.
- Blocked by robots.txt: unintentional blocking of important content.
- Excluded by 'noindex' tag: explicit search engine exclusion.
Tools: Google Search Console, Bing Webmaster Tools, IndexNow.

**Duplicate website versions**: identify multiple URL variations
(http/https, with/without www); implement 301 permanent redirects to
the preferred (HTTPS) version.

**Configure robots.txt properly**: verify "Disallow" directives aren't
blocking important content. Location: yourdomain.com/robots.txt. AI
retrieval bots can now be controlled separately from training-data
scrapers.

**Fix redirect chains and loops**: chains (A→B→C) and loops (infinite
circular redirects). Tool: Semrush Site Audit.

**Address broken links**: fix internal broken links (restore page or
301 redirect); replace/update broken external links. Tool: Site Audit.

**Resolve server errors**: search for "5xx" errors in Site Audit;
escalate specific error codes to dev team.

## Section 2: User Experience Optimization

**Mobile-friendliness**: test on smartphones for text too small,
buttons/links too close together, content wider than screen (horizontal
scroll), pop-ups blocking main content.

**Core Web Vitals** (3 metrics):
1. Largest Contentful Paint (LCP) — main content loading time; target
   2.5 seconds.
2. Interaction to Next Paint (INP) — page responsiveness; target under
   200 milliseconds.
3. Cumulative Layout Shift (CLS) — visual stability; target under 0.1.
Tools: GSC Core Web Vitals report, Google PageSpeed Insights.

**Avoid intrusive interstitials**: full-screen pop-ups on arrival,
dismissal-required overlays, ad layouts pushing content below the fold.
Exception: legitimate pop-ups (cookie notices, age verification,
paywalls).

## Section 3: Website Navigation

**Improve site structure**: logical hierarchy (homepage → categories →
subcategories → individual pages); every page accessible within 3-4
clicks of homepage; pyramid shape with clear pathways.

**Internal linking strategy**: descriptive anchor text (avoid "click
here"/"read more"); hub pages linking to related content; "related
posts" sections at article ends.

**Implement breadcrumbs**: display path hierarchy at top of pages;
enable navigation back through sections; help search engines understand
site structure.

**Fix orphan pages**: identify pages with no incoming internal links;
add links from relevant pages. Tool: Semrush Site Audit.

## Section 4: Code and Configuration

**Use HTTPS**: SSL certificate; Google ranking signal since 2014;
protects sensitive info/user trust; modern browsers flag non-HTTPS as
"Not Secure."

**Implement hreflang for international content**: specify
language/regional page versions; place tags in `<head>`; format
`<link rel="alternate" hreflang="en-us" href="..."/>`; include
x-default fallback.

**Add Schema markup**: helps search systems identify content type,
authorship, dates, entities; enables rich results. Common types:
Organization, Product, Article, Event, Recipe, Review. Tools: Schema
Markup Generator, Google Rich Results Test.

## Section 5: AI Grounding and Agent Readiness

**AI crawler access in robots.txt**: verify AI crawlers aren't
accidentally blocked. Common AI bots: GPTBot, ChatGPT-User, Claude-Web.
Check intentionality of any "disallow" directives targeting them. Tool:
Semrush Site Audit AI Search Health report.

**Semantic HTML and accessibility**: use semantic tags instead of
generic divs/spans — `<header>` (top section, logo/nav), `<h1>` (main
heading), `<nav>` (navigation menus), `<main>` (primary content area),
`<h2>` (subheadings), `<footer>` (bottom section).

**Ecommerce-specific AI readiness**:
- Maintain accurate, real-time product schema.
- Test checkout with ChatGPT Shopping or similar agentic-commerce
  tools.
- Keep policy pages (returns, shipping, FAQs) in plain HTML.
- Use standard HTML for form fields and buttons.
- Ensure functionality without JavaScript on critical pages.
- Make cookie/login modals dismissable with standard HTML buttons.
- Avoid dynamic checkout flows; reflect page-state changes in HTML.

## Core Principle

"Get these right, and your site is well-positioned for both search
systems" — traditional search and AI search platforms.
