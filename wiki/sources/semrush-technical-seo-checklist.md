---
type: source
tags: [seo, aeo]
date_published: 2026-06-23
date_ingested: 2026-07-07
origin: raw/articles/semrush-technical-seo-checklist.md
---

# Technical SEO Checklist for Search Engines and AI Search (Semrush)

**Citation:** Pol, Tushar (contributors: Faizan Ali, Chris Hanna).
"Technical SEO Checklist for Search Engines and AI Search." Semrush
Blog. Published 2026-06-23.
https://www.semrush.com/blog/technical-seo-checklist/

## Key takeaways

- Broad practitioner checklist across 5 areas: crawling/indexing
  (GSC status, duplicate URL versions, robots.txt, redirect chains,
  broken links, 5xx errors), UX (mobile-friendliness, Core Web Vitals
  thresholds, intrusive interstitials), navigation (site structure,
  internal linking, breadcrumbs, orphan pages), code/config (HTTPS,
  hreflang, Schema markup), and — the genuinely new material for this
  wiki — **AI grounding and agent readiness**.
- **Core Web Vitals thresholds**: LCP ≤2.5s, INP <200ms, CLS <0.1.
- **AI crawlers are controllable separately from training-data
  scrapers** in robots.txt — named bots: GPTBot, ChatGPT-User,
  Claude-Web. Check that "disallow" directives targeting them are
  intentional, not accidental.
- **Semantic HTML for AI parsing**: use `<header>`, `<h1>`, `<nav>`,
  `<main>`, `<h2>`, `<footer>` instead of generic divs/spans, so both
  crawlers and AI agents can map structure to meaning.
- **Ecommerce/agentic-commerce readiness** (new territory for this
  wiki): keep real-time-accurate product Schema; test checkout flows
  with agentic shopping tools (e.g. ChatGPT Shopping); keep policy
  pages (returns/shipping/FAQ) in plain HTML; ensure critical-path
  functionality (forms, buttons, modals) works without JavaScript and
  with standard HTML elements; avoid dynamic checkout flows that don't
  reflect state changes in the HTML itself — an agent acting on a
  page needs the DOM to be a truthful, gradually-updating record of
  page state, not just visually correct after JS execution.

## Relationship to existing wiki claims

- **Site structure/navigation** (pyramid hierarchy, "3-4 clicks from
  homepage," descriptive anchor text, breadcrumbs, orphan-page fixing)
  substantially overlaps with material already in
  [[link-and-anchor-text-best-practices]] (from the Ahrefs/Yoast
  ingests). No new conflict — Semrush's "3-4 clicks" is consistent
  with the existing "~3 clicks" pyramid guidance (a minor phrasing
  difference, not a substantive one). Not re-duplicated in the wiki;
  the new playbook below cross-links instead.
- **robots.txt/AI-feature control** overlaps in mechanism with
  [[controlling-ai-feature-inclusion]], but serves the *opposite* goal
  — that playbook is about deliberately excluding content from AI
  features; this source is about making sure AI crawlers *aren't
  accidentally* excluded. Complementary, not conflicting.
- **Crawling/indexing fundamentals** (robots.txt, redirects, broken
  links, server errors) extend [[how-google-search-works]] with
  concrete audit steps/tooling rather than new theory.
- Everything else (Core Web Vitals, HTTPS, hreflang, Schema, semantic
  HTML, ecommerce/agentic-commerce readiness) is new to the wiki.

## What this updated in the wiki

- Created new playbook [[technical-seo-audit-checklist]]: a
  consolidated, checklist-format technical SEO audit covering
  crawling/indexing, UX/Core Web Vitals, navigation (cross-linked to
  [[link-and-anchor-text-best-practices]] rather than duplicated),
  code/config, and AI/agent readiness (including the new
  ecommerce/agentic-commerce section).
- Cross-linked from [[how-google-search-works]] and
  [[controlling-ai-feature-inclusion]].
- No conflicts.
