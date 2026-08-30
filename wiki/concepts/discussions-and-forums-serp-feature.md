---
type: concept
tags: [seo]
updated: 2026-08-30
---

# Discussions and Forums SERP Feature

Google's dedicated "Discussions and forums" SERP box surfaces
user-generated-content threads (Reddit posts, Quora questions, Facebook
Group posts, forum threads) as a distinct feature block on the results
page, separate from standard blue-link organic results. Based on
[[ahrefs-discussions-and-forums-serps-2026]], a 145M-SERP US-market
analysis (16.93M feature appearances, 11.7% prevalence) with
supplementary international sampling.

This is a *classic-SERP UGC-surfacing feature*, distinct from — but
related to — how generative AI answer engines cite Reddit and forum
content, which is covered in [[ai-citation-landscape]].

## Reddit's near-monopoly

Reddit appears in 83.9% of worldwide Discussions and Forums results
(87.8% in the US) and is the dominant platform in 34 countries. Along
with Facebook and Quora, the three platforms account for 76.75% of all
discussion links; the top 10 domains represent 84.87% of appearances,
and the top 1,000 domains cover 96.81% of the total. This is an even
more extreme concentration than typical organic SERP diversity — a
small number of UGC platforms have effectively captured this feature
globally.

## Facebook overtook Quora in January 2026

Facebook now appears in 38.3% of feature results, having passed Quora
for the #2 spot in January 2026 — driven entirely by public Facebook
Groups (a format that has existed since October 2010, suggesting a
recent change in Google's crawling/surfacing of that content rather
than new Facebook functionality).

## Ranking signals: authority and backlinks matter less than expected

- **Domain authority is only moderately correlated** with prominence in
  this feature (Spearman ρ=0.38 between Domain Rating and appearance
  volume). The average prominent domain is 21 years 8 months old, but
  the youngest prominent domain (XDAforums.com) is only 3 years 11
  months old — new, focused forum sites can break in.
- **No correlation was found between backlinks to a specific thread and
  that thread's appearance/ranking** — Google appears to be ranking
  individual discussion threads on topical relevance and
  community-engagement signals (post/comment activity, recency,
  relevance to the query), not traditional link equity.
- This echoes a pattern already documented for AI citation behavior in
  [[ai-citation-landscape]] and [[ahrefs-anchor-text-2020]]/
  [[traditional-seo-ranking-factors]] context: backlink signals are
  weak-to-absent for UGC/thread-level ranking specifically, even where
  they matter more for standard organic ranking.

## Query intent and length

98.7% of feature appearances are on informational-intent queries (see
[[search-intent-and-needs-met]]). The feature is also strongly
correlated with query length: it's rare at 1-word queries (0.3%
appearance rate) and roughly 3x more frequent at 8-word queries —
consistent with the feature being triggered by specific,
conversational, "someone else's experience" type questions rather than
broad head terms.

## Concentration risk at the URL level

A meaningful share of domains depend on a small number of viral threads
for their presence: 27 domains rely on a single URL for 10%+ of their
total appearances, and 768 of the top 1,000 domains depend on one URL
for at least 1% of their presence. This means the feature's apparent
domain-level diversity partly masks a much smaller set of individual
threads carrying disproportionate SERP weight.

## Practical implication

Because backlinks and domain authority are weak predictors at the
thread level, the actionable lever for appearing in this feature is
**authentic participation and topical relevance within
Reddit/Quora/Facebook Groups/niche forums themselves**, not backlink
acquisition or domain-authority building aimed at the feature. This
differs from most other SERP features and from AI-citation tactics
covered in [[geo-content-optimization-tactics]].

## See also

- [[ai-citation-landscape]] — how AI answer engines (as opposed to this
  classic Google SERP feature) cite Reddit and forum content; note
  Reddit is heavily *retrieved* but rarely *cited* by ChatGPT (67.8% of
  non-cited URLs are Reddit) — a different dynamic from this feature's
  Reddit dominance.
- [[traditional-seo-ranking-factors]] — general classic-SERP ranking
  correlation data, for comparison against this feature's
  weak-authority/no-backlink pattern.
