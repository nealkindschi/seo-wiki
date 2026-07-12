---
type: source
tags: [seo, aeo]
date_published: 2026-07-07
date_ingested: 2026-07-11
origin: raw/articles/wix-generative-engine-optimization.md
---

Crystal Carter, "Generative Engine Optimization: LLM Optimization Strategies" (Wix Studio AI Search Lab).

## Key takeaways

- **GEO ≠ AI Overview optimization** — a distinction this wiki hadn't
  made explicit before. LLM chat products (ChatGPT, Gemini, Perplexity)
  are opted into by users who interact, give feedback, and go deeper;
  AI Overviews are a passive, non-opt-in SERP feature. Treat them as
  genuinely separate optimization targets, not two names for the same
  discipline — [[geo-content-optimization-tactics]] and
  [[aio-ctr-impact]] mostly document AI-Overview-and-Overview-adjacent
  behavior; this source is the wiki's first dedicated LLM-chat-specific
  playbook.
- **Three-way LLM taxonomy** (finer than the wiki's existing
  training/indexing/retrieval bot taxonomy in
  [[how-google-search-works]]): static pre-trained (Claude 3-3.5, GPT-3,
  Gemini 1.5, NotebookLM), search-augmented (Perplexity, Copilot, GPT-4),
  and reasoning-with-search (DeepSeek R1-R2, Gemini 2.5, o1-o4). Static
  models rarely show links; search-augmented and reasoning models do.
- **Optimize for brand mentions, not links, on static models** — a
  distinct KPI shift from the citation/click framing that dominates the
  rest of this wiki's GEO content (which mostly concerns search-
  augmented/AI-Overview contexts where links are the point).
- **Feedback loop as a visibility lever**: static LLMs still update
  brand accuracy from user thumbs-up/down feedback even between
  training runs — the author's own Gemini example (incorrect →
  thumbs-down with correction → later correct) demonstrates this
  concretely. A tactic with no equivalent elsewhere in this wiki.
- **Search-augmented internal-linking tactic**: prioritize linking
  *from* pages the LLM already cites *to* pages you want it to newly
  cite — extends the wiki's existing internal-linking guidance
  ([[link-and-anchor-text-best-practices]]) with an LLM-citation-
  specific version of "link from your strongest pages."
- **Per-LLM crawler user-agent table** (OAI-SearchBot/ChatGPT-User/
  GPTBot, BingBot, Google-Extended, ClaudeBot, PerplexityBot) — adds
  concrete bot names to the wiki's existing generic training/indexing/
  retrieval bot taxonomy in [[how-google-search-works]] and the
  robots.txt guidance in [[robots-txt-strategy]]/[[robots-txt-audit-checklist]].
- **Wikipedia/entity-management reinforcement**: both LLM types train
  on Wikipedia's 65M+ pages, feeding the same knowledge-graph/semantic-
  web infrastructure this wiki already covers in
  [[entity-oriented-search-fundamentals]] and
  [[ai-citation-landscape]]'s Wikipedia-presence finding for
  ChatGPT/Claude — consistent, not new, but a clean worked example
  (Barbie → Mattel/dolls/toy-industry entity linkage).
- **Direct-platform-engagement tactics** (publisher partnerships,
  custom GPTs, Perplexity Pages) — a new category not previously in
  the wiki: getting *into* the platform's ecosystem directly rather than
  only optimizing content to be retrieved by it.
- Traffic-scale stats (ChatGPT 5.5B monthly visits/79% LLM-chat market
  share, ~7B combined LLM visits, May 2025 SimilarWeb) sit alongside
  [[ai-traffic-scale-vs-hype]]'s much smaller relative-to-search
  framing — worth reading together: this source's numbers describe
  LLM-vs-LLM share and are consistent with, not contradicting,
  [[ai-traffic-scale-vs-hype]]'s point that even 7B LLM visits are
  small next to search+social's overall scale.

## Updated

- [[generative-engine-optimization]] — added a "GEO vs. AI Overview
  optimization" distinction section and the static/search-augmented/
  reasoning LLM taxonomy.
- [[geo-content-optimization-tactics]] — added an "LLM-chat-specific
  tactics" section: brand-mention-not-links framing, the feedback-loop
  tactic, citation-based internal linking, and direct-platform-
  engagement tactics.
