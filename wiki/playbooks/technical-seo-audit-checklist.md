---
type: playbook
tags: [seo, aeo]
updated: 2026-07-07
---

# Technical SEO Audit Checklist

**Why/when to use this:** run through this when auditing a site's
technical foundation — the fundamentals that determine whether a page
can be crawled, indexed, and rendered correctly at all, which is a
prerequisite for both classic search ranking and AI-generated-answer
citation (see [[how-google-search-works]] and
[[generative-engine-optimization]]'s "retrieval eligibility"). Based on
[[semrush-technical-seo-checklist]].

## 1. Crawling and indexing

- **Check indexing status** in Google Search Console's "Pages" report.
  Common exclusion reasons to investigate: *Crawled - currently not
  indexed* (usually low-quality or duplicate content), *Blocked by
  robots.txt* (often unintentional), *Excluded by 'noindex' tag*
  (confirm it's deliberate).
- **Consolidate duplicate URL versions** (http/https, with/without
  www) with 301 redirects to a single preferred (HTTPS) version.
- **Audit robots.txt** for unintended "Disallow" rules blocking
  important content.
- **Fix redirect chains** (A→B→C) **and loops** (circular redirects).
- **Fix broken links** — restore or 301-redirect broken internal links;
  update or remove broken external links.
- **Resolve server errors** — audit for 5xx errors and escalate
  specific codes to engineering.

Tools: Google Search Console, Bing Webmaster Tools, IndexNow, a
site-crawl tool (e.g. Semrush Site Audit) for chains/broken
links/5xx/orphan-page detection at scale.

## 2. User experience

- **Mobile-friendliness**: check for text too small to read without
  zooming, tap targets too close together, content wider than the
  viewport (horizontal scroll), and pop-ups blocking main content on
  load.
- **Core Web Vitals** — three thresholds:
  - **LCP** (Largest Contentful Paint): ≤ 2.5 seconds.
  - **INP** (Interaction to Next Paint): < 200 milliseconds.
  - **CLS** (Cumulative Layout Shift): < 0.1.
  Tools: GSC's Core Web Vitals report, Google PageSpeed Insights.
- **Avoid intrusive interstitials**: full-screen pop-ups on arrival,
  overlays requiring dismissal before content is visible, ad layouts
  pushing main content below the fold. Legitimate exceptions: cookie
  notices, age verification, paywalls.

## 3. Navigation and internal linking

See [[link-and-anchor-text-best-practices]] for the full internal-
linking playbook (site structure, anchor text, cornerstone content,
audit workflow). Quick-reference for this audit:

- [ ] Pyramid site structure, every important page within ~3-4 clicks
      of the homepage.
- [ ] Breadcrumbs present and accurate.
- [ ] No orphan pages (zero inbound internal links).
- [ ] Descriptive anchor text, not "click here"/"read more."

## 4. Code and configuration

- **HTTPS** — SSL/TLS on every page; a confirmed Google ranking signal
  since 2014, and modern browsers flag non-HTTPS pages as "Not Secure."
- **hreflang for international content** — specify language/regional
  page variants in `<head>`:
  `<link rel="alternate" hreflang="en-us" href="..."/>`, with an
  `x-default` fallback tag for unmatched locales.
- **Schema markup** — helps both search engines and AI systems
  identify content type, authorship, dates, and entities, and enables
  rich results. Common types: Organization, Product, Article, Event,
  Recipe, Review. Tools: a schema generator, Google's Rich Results
  Test.

## 5. AI grounding and agent readiness

- **Check AI crawler access in robots.txt separately from regular
  search bots** — named AI bots include GPTBot, ChatGPT-User, and
  Claude-Web. Confirm any "disallow" targeting them is intentional; see
  [[controlling-ai-feature-inclusion]] if you *do* want to deliberately
  exclude content from AI features specifically (a different, opposite
  goal from this checklist item).
- **Use semantic HTML**, not generic divs/spans, so crawlers and AI
  agents can map structure to meaning: `<header>` (logo/nav),
  `<h1>` (main heading), `<nav>` (navigation), `<main>` (primary
  content), `<h2>` (subheadings), `<footer>`.
- **Ecommerce/agentic-commerce readiness** — relevant if AI shopping
  agents may transact on your site, not just cite it:
  - Keep product Schema accurate and real-time (price, availability).
  - Test your checkout flow with an agentic shopping tool (e.g. ChatGPT
    Shopping) to confirm an agent can actually complete a purchase.
  - Keep policy pages (returns, shipping, FAQs) in plain HTML, not
    behind JS-only rendering or PDFs.
  - Use standard HTML form fields and buttons — avoid custom
    JS-only input components an agent can't reliably operate.
  - Ensure critical-path functionality (forms, checkout, modals) works
    without JavaScript, or fails gracefully if it doesn't.
  - Make cookie/login modals dismissable via standard HTML buttons, not
    JS-only interaction patterns.
  - Avoid dynamic checkout flows that don't reflect state changes in
    the HTML/DOM itself — an agent needs the page's HTML to be a
    truthful record of current state, not just visually correct after
    client-side JS runs.

## See also

- [[how-google-search-works]] — the crawl/index/serve pipeline this
  checklist's crawling/indexing section is auditing against.
- [[link-and-anchor-text-best-practices]] — full internal-linking
  playbook referenced in §3.
- [[controlling-ai-feature-inclusion]] — the opposite goal: deliberately
  excluding content from AI features, rather than ensuring AI crawlers
  can access it.
- [[generative-engine-optimization]] — technical crawlability as the
  "retrieval eligibility" prerequisite for AI-citation visibility.
- [[optimizing-for-coding-agent-recommendations]] — a sibling
  "agent readiness" domain, but for coding agents choosing tools rather
  than shopping/browsing agents acting on a page.
