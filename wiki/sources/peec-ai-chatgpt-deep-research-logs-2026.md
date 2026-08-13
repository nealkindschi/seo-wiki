---
type: source
tags: [seo, aeo]
date_published: 2026-06-22
date_ingested: 2026-08-12
origin: raw/articles/peec-ai-chatgpt-deep-research-logs-2026.md
---

# How ChatGPT Deep Research Reads Your Site: What the Logs Reveal (Peec AI)

**Citation:** Konitzny, David. "How ChatGPT Deep Research reads your
site: What the logs reveal." Peec AI Blog. Published 2026-06-22
(page shows an August 2026 blog-listing date).
https://peec.ai/blog/how-chatgpt-deep-research-reads-your-site-what-the-logs-reveal
(WebSocket-traffic capture across 10+ free-tier accounts, ~20 requests
each, informational + transactional prompts, verified against
plain-text no-JS crawls of the same pages.)

## Key takeaways

- **First mechanistic, log-verified account in this wiki of a specific
  named AI agent's actual browsing behavior** (distinct from the
  general training/indexing/retrieval bot taxonomy in
  [[how-google-search-works]] and the reranker/retrieval pipeline in
  [[rerankers-and-passage-selection]]): Deep Research runs a three-step
  loop — `search` (Bing, `web_with_bing`, no Google fallback, ~285-char
  snippets) → `open` (linearized plaintext, ~5,000-6,000 char capped
  read) → `find` (in-page Ctrl+F, re-opens at matched line numbers). It
  never clicks — JS-interaction-dependent content is fully inaccessible.
- **Navigation link density directly taxes the reading budget**: light
  nav (<20 links) leaves ~78% of the first read for content; heavy nav
  (60+ links) leaves only ~33% — a concrete, measured version of "keep
  navigation slim" advice.
- **Source order, not CSS/visual position, determines what's read** —
  content positioned late in the HTML source can be invisible to the
  first read even if it renders prominently on screen. Verified by
  matching the agent's WebSocket reads against a plain-text no-JS crawl
  word-for-word.
- **`OAI-SearchBot` is the enforced user-agent for Deep Research's
  fetches** (distinct from `GPTBot`), and robots.txt blocks are obeyed
  silently — blocked pages return zero content with no error surfaced
  anywhere in the final report.
- **Alt text is read as real page content**, not just an accessibility
  attribute — meaningful alt text on badges/charts/awards can embed
  facts directly into the generated answer; filename-only or missing
  alt text is skipped as decorative.
- **A measured re-read/abandonment mechanism**: a successful `find`
  triggers re-reading 95% of the time; missing the expected keyword
  causes abandonment, with ~25% of failed finds triggering a fresh Bing
  query rather than continued reading on the same page — direct
  evidence for "use the searcher's exact terminology verbatim."
- **Search depth narrows with confidence**: `topn` (Bing results pulled
  per query) starts at up to 10 on exploratory queries, settles to 3
  as steady-state, and drops to 2 for fact verification — in practice
  only the top 2-3 Bing results per query typically get read at all.
- **Being read is not the same as being cited** — the agent reads much
  more than it cites, and will explicitly fall back to general
  knowledge when a site lacks a specific citable claim. "Read but not
  cited" is a distinct, trackable state.
- **Source-trust vocabulary is narrated live in the agent's own
  reasoning**: positive ("official," "reliable," "trusted," "credible,"
  "reputable," "well-known") vs. negative/hedging ("not an official
  source," "anecdotal," "might not be reliable," "decorative") — a
  real-time, first-person view of E-E-A-T-style trust evaluation.

## Relationship to existing wiki claims

- **Extends** [[how-google-search-works]]'s "AI bot types" subsection
  (training/indexing/retrieval taxonomy from
  [[peec-ai-server-logs-ai-search-2026]]) with a concrete case study of
  one specific bot (`OAI-SearchBot`) and one specific agent (Deep
  Research) in action — confirms the taxonomy's practical stakes
  (silent zero-content on block, no error surfaced) rather than
  contradicting it.
- **Extends** [[rerankers-and-passage-selection]]'s retrieval-stage
  framing with the Bing-specific mechanics of one production text
  agent — this source's "search → open → find" loop is a concrete
  instance of the general "retrieval, wide net" stage described there,
  specific to Deep Research rather than a general reranker model.
- **Extends** [[technical-seo-audit-checklist]]'s existing "AI
  search-specific technical risks" section (JS rendering, third-party
  blocking) with agent-specific detail: the exact character budgets,
  the "Skip to Content" paradox (an accessibility pattern that actively
  wastes read budget for this agent), and the alt-text-as-content
  finding.
- **No conflicts** — this is a narrowly-scoped, methodologically
  transparent observational study of one named feature, and its
  findings (source-order primacy, robots.txt enforcement, JS
  inaccessibility) are consistent with every existing wiki claim about
  AI crawler/agent limitations.
- **Explicit scope limit preserved**: covers Deep Research specifically,
  not ChatGPT's quick Search answers or Agent mode (a real interactive
  browser) — don't generalize these specific character-budget/topn
  numbers to other ChatGPT surfaces.

## What this updated in the wiki

- New playbook page [[chatgpt-deep-research-crawl-mechanics]] created
  to hold the full pipeline/budget/checklist content (agent-specific
  and tactical enough to warrant its own page rather than diluting
  [[geo-content-optimization-tactics]]).
- Cross-referenced from [[how-google-search-works]]'s "AI bot types"
  subsection, [[technical-seo-audit-checklist]]'s §5 AI grounding
  section, and [[geo-content-optimization-tactics]]'s LLM-chat-specific
  tactics section.
