---
type: playbook
tags: [seo, aeo]
updated: 2026-08-12
---

# ChatGPT Deep Research Crawl Mechanics

**Why/when to use this:** Apply this when optimizing specifically for
ChatGPT's **Deep Research** feature (the long-running, multi-step
research agent), as distinct from ChatGPT's quick Search answers or
Agent mode (a real interactive browser) — different pipelines apply to
each, and these specific mechanics/checklist items are Deep-Research-
specific. Based on
[[peec-ai-chatgpt-deep-research-logs-2026]] (log-verified via captured
WebSocket traffic, June 2026 snapshot).

## The three-command reading loop

Deep Research uses exactly three commands and never clicks — anything
requiring a JavaScript interaction is invisible to it:

1. **`search`** — via Bing only (`web_with_bing`, no Google fallback).
   Returns ranked results with title, URL, and a snippet capped at
   ~285 characters. The snippet content determines whether a page even
   earns an initial open.
2. **`open`** — returns the page as linearized plaintext, numbered
   line-by-line, capped at roughly 5,000-6,000 characters per read.
   Links render inline as `【n†anchor text†url】` markers.
3. **`find`** — an in-page Ctrl+F for specific terms; returns exact
   matching line numbers and re-opens the page positioned there. A
   missed search returns only ~49 characters ("not found").

## Checklist: preserving the read budget

- [ ] **Keep navigation slim.** Light navigation (<20 links) leaves
      ~78% of the ~5-6k character first-read budget for actual content;
      heavy navigation (60+ links) leaves only ~33% — nearly two-thirds
      of the budget is consumed by menus before content ever appears.
- [ ] **Front-load the answer.** Put plain-language answer text near
      the top of the page, ahead of navigation/boilerplate in **source
      order** — CSS positioning is irrelevant to this agent; only HTML
      source order determines what's read first. Content buried behind
      navigation blocks in source may never appear in the first read
      even if it's visually prominent on screen.
- [ ] **Don't rely on "Skip to Content" links to fix this.** They
      require a click to function for a human/screen-reader, but Deep
      Research reads them as plain inline text and then continues
      linearly through the navigation menu anyway — the paradox is that
      an accessibility affordance actively wastes this agent's read
      budget rather than saving it.
- [ ] **Move all critical information into plain text.** Avoid content
      gated behind clicks, filters, tabs, or client-side rendering —
      none of it is reachable.

## Checklist: triggering re-reads instead of abandonment

- [ ] **Use the searcher's exact terminology verbatim** in headings and
      copy. A successful `find` triggers a re-read 95% of the time,
      surfacing the matched passage directly; missing the expected
      keyword causes fast abandonment — ~25% of failed `find` attempts
      trigger a fresh Bing query instead of continued reading on the
      same page.
- [ ] **Write descriptive internal links with clear anchor text and
      visible destination URLs.** The agent selectively follows
      internal/external links based on relevance assessed from the
      anchor text and the URL shown in the link marker — clear links to
      pricing, specs, or comparison pages are direct pathways into
      deeper content that a vague "learn more" link isn't.
- [ ] **Add substantive alt text to meaningful images.** Alt text is
      rendered directly into the page text and treated as real content
      — rich alt text on badges, charts, or award graphics can embed
      facts directly into the generated answer. Filename-only or
      missing alt text (e.g. "awardwinning-360x140.svg") is recognized
      as decorative and skipped entirely.

## Checklist: don't get silently blocked

- [ ] **Unblock `OAI-SearchBot` in robots.txt and at the CDN/WAF
      level.** This is the enforced user-agent for Deep Research's
      fetches (distinct from `GPTBot`) — blocked pages return zero
      content, and no error is ever surfaced in the final report. A
      silently blocked page just never shows up in an answer, with no
      diagnostic signal pointing back to the block.
- [ ] **Don't assume a login wall or defensive server config is
      neutral.** Social-platform login walls leave only the Bing
      snippet accessible; some large marketplaces refuse fetches
      entirely; slow/defensive servers get dropped from consideration
      on timeout — audit these the same way you'd audit a robots.txt
      block.

## Bing as a distinct optimization surface

Only the top 2-3 Bing results per query typically enter Deep Research's
read set — search depth (`topn`) narrows as the agent gains confidence:
up to 10 results on opening/exploratory queries, settling to 3 as the
steady-state default, and down to 2 for verifying a specific fact.

- [ ] Treat Bing ranking as its own optimization target, not an
      afterthought to Google SEO.
- [ ] Optimize the ~285-character Bing snippet to directly answer the
      likely query, not just carry brand messaging — the snippet
      itself gates whether a page is opened at all.

## Building citable trust, not just readable content

Being read is necessary but not sufficient for citation — the agent
reads far more than it ever cites, and will explicitly fall back to
general knowledge when a page lacks a specific claim worth citing. The
logs show the agent narrating its own E-E-A-T-style trust judgment in
real time:

- **Positive-trust vocabulary**: "official," "reliable," "trusted,"
  "credible," "reputable," "well-known" — recognized rating/reference
  sites and official sources get prioritized.
- **Negative/hedging vocabulary**: "not an official source,"
  "anecdotal," "might not be reliable," "decorative" — UGC/forum
  content gets relegated to background context only.

- [ ] Build official-source positioning deliberately: citations, named
      authors, third-party validation — the same E-E-A-T signals as
      [[e-e-a-t-and-page-quality]], now confirmed as literally the
      vocabulary this agent uses to decide what to trust.
- [ ] **Measure "read but not cited" as its own state**, not just
      citation rate — a page can be consistently read by Deep Research
      sessions while never earning a citation, which is a different
      problem (missing a specific citable claim) than not being read at
      all (an access/discovery problem).

## Caveats — what's durable vs. what will drift

- **Durable (structural)**: Bing-only retrieval, the three-command
  interface, no click capability, capped per-open reads,
  robots.txt/`OAI-SearchBot` enforcement, alt-text-as-content, and
  selective relevance-based link-following.
- **Will drift (June 2026 snapshot)**: the exact ~5,000-6,000 character
  read window, ~285-character snippet cap, 95% re-read rate, and the
  specific `topn` thresholds (10/3/2) — treat these as directional
  targets, not permanent constants, and re-verify periodically.
- This is an observational study (WebSocket capture + plain-text-crawl
  verification) of one specific feature, not a controlled experiment —
  findings reflect consistent patterns across ~10 accounts/~20 requests
  each, not a guaranteed universal mechanism.

## See also

- [[how-google-search-works]] — the general training/indexing/
  retrieval AI-bot taxonomy this page's `OAI-SearchBot` finding sits
  within.
- [[rerankers-and-passage-selection]] — the general retrieval/reranking
  pipeline model; this page is a concrete, log-verified instance of the
  "retrieval, wide net" stage for one specific agent.
- [[technical-seo-audit-checklist]] — §5's AI grounding/agent-readiness
  checklist, which this page's robots.txt and JS-rendering findings
  extend with agent-specific detail.
- [[geo-content-optimization-tactics]] — the LLM-chat-specific tactics
  section (crawler user agents, brand-mention tracking) this page adds
  Deep-Research-specific mechanics to.
- [[e-e-a-t-and-page-quality]] — the trust framework this page's
  observed agent vocabulary directly instantiates.
- [[peec-ai-server-logs-ai-search-2026]] — the server-log diagnostic
  method (crawl frequency vs. citation rate) this page's "read but not
  cited" distinction complements from the site-owner's log-analysis
  side rather than the agent-behavior side.
