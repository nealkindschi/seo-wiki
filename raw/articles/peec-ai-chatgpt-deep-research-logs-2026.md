---
title: "How ChatGPT Deep Research reads your site: What the logs reveal"
author: David Konitzny
publication: Peec AI Blog
url: https://peec.ai/blog/how-chatgpt-deep-research-reads-your-site-what-the-logs-reveal
date_published: 2026-06-22
date_fetched: 2026-08-12
---

# How ChatGPT Deep Research reads your site: What the logs reveal

**Publication Date:** June 22, 2026 (republished/updated on Peec AI's
blog August 12, 2026)
**Author:** David Konitzny, GEO Researcher (Peec AI)

## Executive Summary

Reverse-engineers ChatGPT's Deep Research feature by capturing
WebSocket traffic during live agent sessions, revealing exactly how its
text-based browser reads websites, what content it can and can't
access, and why some pages get read but never cited. Covers 10+
free-tier accounts, ~20 requests each, across informational and
transactional queries.

## Three-step reading pipeline

1. **Search via Bing** — retrieves ranked results (title, URL, snippet)
   using `"source":"web_with_bing"` exclusively, no Google fallback.
   Bing snippets are capped at ~285 characters; snippet content
   determines whether a page earns the initial open.
2. **Open and skim** — returns plaintext, numbered line-by-line, capped
   at roughly 5,000-6,000 characters per read. The agent evaluates
   whether deeper reading is worthwhile. Links render inline as markers:
   `【n†anchor text†url】`.
3. **Find (Ctrl+F)** — searches within an already-open page for specific
   terms, returns exact matching line numbers, and re-opens the page
   positioned at those lines. A missed search returns only ~49
   characters ("not found").

**Critical constraint**: the agent uses exactly three commands —
`search`, `open`, `find` — and never clicks. Content requiring
JavaScript interaction is inaccessible.

## Reading-window budget and navigation cost

Navigation link density eats directly into the ~5-6k character read
budget before any main content is seen:

| Navigation level | Content % of first read | Implication |
|---|---|---|
| Light (<20 links) | ~78% | Minimal impact |
| Medium (20-59 links) | ~55% | Nearly half the budget consumed |
| Heavy (60+ links) | ~33% | Two-thirds consumed before content |

**The "Skip to Content" paradox**: accessibility "Skip to main content"
links require a click to function for a human/screen-reader, but Deep
Research reads them as plain inline text, then continues linearly
through the navigation menu before ever reaching real content.

## Re-read triggers

- **Keyword-driven (primary)**: a successful `find` triggers a re-read
  95% of the time, with the matched passage in the retrieved window.
- **Continuation (~20%)**: the agent reads the next chunk without any
  keyword trigger.
- **Abandonment**: pages missing expected keywords are abandoned
  quickly — ~25% of failed `find` attempts prompt a fresh Bing query
  instead of continued reading.

## Search depth (`topn` parameter)

The number of Bing results pulled per query (`topn`) narrows as the
agent gains confidence: up to 10 results on opening/exploratory
queries, `topn=3` as the steady-state default, `topn=2` for
verification of specific facts. In practice, only the top 2-3 Bing
results per query typically enter the read set.

## Image and alt-text handling

Alt text is rendered directly into page text and treated as real
content. Images without meaningful alt text are marked `Image` and
skipped; filenames alone (e.g. "awardwinning-360x140.svg") are
recognized as decorative and ignored. Rich alt text on badges, charts,
or award graphics can embed facts directly into the final answer.

## Link-following behavior

The agent selectively follows internal/external links based on a
relevance assessment using anchor text and the visible destination URL
in the link marker. Script-driven menus remain unreachable. Clear
internal links to pricing, specs, and comparison pages provide direct
pathways into deeper content.

## Reading vs. citing gap

The agent reads far more than it ever cites. One observed internal
reasoning trace (paraphrased): "The site doesn't have specific content
to cite for closures, so I'll rely on general knowledge." Being read is
necessary but not sufficient for citation — the agent must identify
specific claims that genuinely require sourcing.

## Source trust evaluation (E-E-A-T narrated live)

The logs surface the agent's credibility vocabulary directly:
- **Positive**: "official," "reliable," "trusted," "credible,"
  "reputable," "well-known" — recognized rating/reference sites treated
  as authoritative, official sources prioritized.
- **Negative/hedging**: "not an official source," "anecdotal," "might
  not be reliable," "decorative" — UGC/forum content relegated to
  background context, unofficial aggregators kept only as general
  reference.

This is E-E-A-T (expertise, experience, authoritativeness,
trustworthiness) being narrated in real time through the agent's own
reasoning rather than inferred after the fact.

## Content rendering and source order

Deep Research receives pages as linearized HTML text, top-to-bottom,
with `<head>` stripped:
- **CSS positioning is irrelevant — source order determines
  visibility.** Navigation appearing late in the HTML source costs
  nothing even if it's visually prominent on the rendered page; main
  content buried behind navigation blocks *in source order* may never
  appear in the first read.
- PDFs render cleanly with no chrome, starting directly at content.
- Verification: the researcher's own plain-text (no-JS) HTML crawl
  matched the agent's WebSocket reads word-for-word.

## Content blockage and unreadable formats

- **robots.txt blocks**: user-agent `OAI-SearchBot` (distinct from
  `GPTBot`) is checked and obeyed; blocked pages return 0 content.
- **Login walls**: social-platform content is blocked; only the Bing
  snippet remains accessible.
- **Large marketplaces**: some commercial sites refuse fetches
  entirely.
- **Timeouts**: slow or defensive servers get dropped from
  consideration.
- **Images without alt text**: rendered as empty markers, skipped.

No errors are flagged in the final report — blocked/unreadable content
simply doesn't appear in the answer, with no visible signal to the user
that it was excluded.

## Methodology

**Capture method**: DevTools opened before Deep Research launch,
filtered to WebSocket (WS) traffic; raw frames downloaded and analyzed
offline. Timing-sensitive — listening must start before the agent
begins, or opening searches are missed.

**Sample**: 10+ separate free-tier accounts, ~20 requests per account,
mixed informational (research/planning) and transactional
(product/provider comparison) prompts. Findings validated only when
repeated across accounts and prompt types.

**Faithfulness verification**: the researcher ran identical plain-text
(no-JavaScript) crawls of the same pages and compared them to the
agent's WebSocket reads — they matched word-for-word, with no dropped
elements and no JS-rendered content appearing in the agent's reads.
Source order was confirmed deterministic and verifiable.

## Recommendations

**Priority one (immediate)**:
1. Unblock `OAI-SearchBot` in robots.txt and at the CDN/WAF level —
   blocked content is invisible, with no fallback.
2. Front-load answer text near the top of the page in plain language;
   keep navigation slim to preserve the ~5-6k character first-read
   budget.
3. Use exact search terminology verbatim in headings and copy —
   matching keywords trigger `find` re-reads; missing terms cause
   abandonment.

**Priority two (extended)**:
1. Treat Bing as a distinct marketing channel in its own right — only
   the top 2-3 results per query get read.
2. Optimize the Bing snippet (~285 characters) to directly answer
   likely queries, not just carry brand messaging.
3. Move all critical information into plain text; avoid clicks,
   filters, tabs, or client-side-rendering-dependent content.
4. Write descriptive internal links with clear anchor text to guide the
   agent toward deeper pages.
5. Add substantive alt text to all meaningful images — critical for
   embedding facts (badges, charts, awards) into the final answer.
6. Build official-source positioning through citations, named authors,
   and third-party validation — the vocabulary the agent uses to decide
   trust.
7. Measure influence beyond citation counts — the agent reads far more
   content than it ever cites, so "read but not cited" is a real,
   trackable middle state.

## Limitations and caveats

- Observational study of a moving target — OpenAI iterates constantly.
- Structural findings (Bing retrieval, three-command interface, no
  clicks, capped reads, robots.txt enforcement, alt-text-as-content,
  selective link-following) are treated as durable.
- Exact measurements (5-6k window, 285-char snippet, 95% re-read rate,
  `topn` thresholds) are a June 2026 snapshot, subject to drift.
- Reasoning quotes reflect the agent's stated logic in the trace, not a
  guaranteed underlying mechanism.
- No controlled experiments — findings are based on consistent patterns
  across the sample, not isolated instances.

## Scope

Covers **Deep Research specifically** — the long-running text-browser
agent. Does **not** cover ChatGPT's quick Search answers or Agent mode
(which drives a real, interactive browser) — different pipelines apply
to each.
