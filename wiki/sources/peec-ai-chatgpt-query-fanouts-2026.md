---
type: source
tags: [aeo]
date_published: 2026-07-07
date_ingested: 2026-07-08
origin: raw/studies/peec-ai-chatgpt-query-fanouts-2026.md
---

# Patterns We See in ChatGPT Query Fanouts (Peec AI)

**Citation:** Rudzki, Tomek. "Patterns we see in ChatGPT query
fanouts." Peec AI Blog. Published 2026-07-07 (research collected
2026-04-01 to 2026-04-21).
https://peec.ai/blog/patterns-we-see-in-chatgpt-query-fanouts
(Methodology: 5M query fanouts across ChatGPT, Perplexity, and Grok,
three-week window in April 2026, weighted toward ChatGPT.)

## Key takeaways

- Defines and mechanically explains **query fanout**: the hidden
  sub-queries an AI engine issues behind a single user prompt before
  synthesizing an answer — a term the wiki previously only used in
  passing (Google's own "query fan-out" usage in
  [[generative-engine-optimization]]) without data or mechanism.
- **Engine fanout volume differs sharply**: Perplexity 1.4/query
  (minimal expansion), ChatGPT 2.1/query (adds brands/comparisons/
  review keywords), Grok 6.8/query (treats the query as a research
  brief, progressively narrowing by year/brand/trusted domain).
- **Injected-word data for ChatGPT**: "best" injected into 24.3% of
  advice-style questions never phrased that way by the user; "reviews"
  is the third most-injected word, pulling in review-platform content
  (Glassdoor, G2, Sitejabber) unprompted.
- ChatGPT combines fanout subquery results via **Reciprocal Rank
  Fusion (RRF)** — content surfacing across multiple fanout subqueries
  outranks content matching only one.
- Freshness signal: a current-year token is injected into 5.44% of
  prompts.
- Grok explicitly site-targets trusted domains in 18.3% of chats;
  Reddit appears in 10.5% of chats (~90% deliberately site-directed);
  Wirecutter and Consumer Reports are injected by Grok at a 100% rate,
  never user-requested.
- Strategic framing: listicle ("best of") content structurally matches
  the dominant fanout injection pattern (best/top/comparison/reviews),
  offered as a mechanism explaining why listicles dominate AI answers.

## Relationship to existing wiki content

Distinct from, and complementary to, [[airops-fan-out-effect-2026]],
which studies a different angle of "fan-out": how much of a query's
fanout *subtopic space* a given page's content covers (finding that
partial coverage often out-cites full coverage). This source instead
studies what the *engine itself* injects into its hidden subqueries
before retrieval even happens — upstream of AirOps's retrieval-rank
mechanism. No conflict between the two; together they cover the full
fanout pipeline (what the engine searches for → what gets retrieved →
what gets cited).

## What this updated

- [[ai-citation-landscape]] — added a "Query fanout mechanics" section
  distinguishing this engine-side injection behavior from AirOps's
  content-coverage fan-out finding.
- [[geo-content-optimization-tactics]] — added a tactic on targeting
  common fanout injection angles (comparison/review/best-of framing)
  rather than only the literal target query.

No conflicts.
