---
type: concept
tags: [seo, aeo]
updated: 2026-07-07
---

# AIO Impact on Google CTR

The traffic/click-through-rate economics of Google AI Overviews (AIOs) —
distinct from [[ai-citation-landscape]] (what gets cited) and
[[ai-visibility-correlation-factors]] (what correlates with being
mentioned). This page covers *what citation is actually worth in
clicks*. Based on
[[seerinteractive-aio-ctr-impact-2026-update]], the third installment of
an ongoing large-scale study (53 brands, 5.47M queries, 2.43B
impressions, Jan 2025–Feb 2026).

## The citation premium — and its ceiling

Being cited inside an AI Overview delivers **+120% more organic clicks
per impression** than not being cited — a substantial, consistent
advantage (2–5x CTR across every month studied in 2025). But even cited
traffic still runs **-38% below** what the same query would generate
with no AI Overview at all. Per 1 million informational impressions:

| AIO status | Organic clicks (approx.) |
|---|---|
| No AIO | ~33,500 |
| Brand cited in AIO | ~20,743 |
| AIO present, brand not cited | ~9,445 |

Practical framing: citation tactics (see
[[geo-content-optimization-tactics]]) meaningfully recover traffic
relative to not being cited, but they don't fully restore what a query
would earn without an AI Overview present at all. This is the economic
"why" behind [[generative-engine-optimization]]'s citation-focused
tactics.

## 2025 decline, then a 2026 reversal nobody predicted

After ~18 months of steady organic CTR compression on AIO-affected
queries through 2025, cited-brand organic CTR unexpectedly climbed from
1.3% (December 2025) to 2.4% (February 2026) — beating every forecasting
model's projection, in some cases by more than 2.5 percentage points.
The researchers frame this as a possible leveling-off / "new normal"
rather than a full recovery to pre-AIO baselines. Non-AIO queries
improved over the same period too (2.8% → 3.8% organic CTR, Jan 2025 to
Feb 2026), suggesting broader dynamics beyond just AIO-specific recovery.

## A critical measurement lesson: separate impressions from clicks

A dramatic -52.1% single-month CTR drop for cited brands (October 2025)
looked alarming, but investigation showed clicks stayed essentially flat
(398,798 → 400,271) while impressions more than doubled (15.8M → 33.1M).
The brand earned citations on many more queries — it didn't lose
existing conversions. **A falling CTR on cited queries is not
automatically bad news** if it's driven by an impressions surge rather
than a clicks decline. Always look at impressions and clicks separately
before drawing conclusions from a CTR number alone.

## AIO prevalence depends heavily on query intent and format

- By intent: informational queries show AIOs 36% of the time,
  commercial 8%, transactional only 5% — a 7x gap between informational
  and transactional.
- By format (from 49,353 distinct queries analyzed): comparison queries
  ("X vs Y") trigger AIOs **95.4%** of the time, review queries 86.3%,
  question-format queries 85.9%, price/buy queries 83.4%, "best of"
  queries 81.3%, and — surprisingly for local intent — "near me" queries
  76.9%. Even single-word queries trigger AIOs 27.3% of the time across
  25M impressions: **don't assume short queries are safe from AIO
  exposure.**

## Paid search behaves very differently from organic

Paid CTR on AIO-present queries held stable in a 13.99–17.95% range all
of 2025 with no meaningful decline, and forecasting models predicted it
accurately (missed by only 0.09 percentage points). Organic CTR, by
contrast, was volatile and hard to model (missed by 0.6–2.6 percentage
points across every segment). Whatever AI Overviews are doing to organic
click behavior, they are not doing the same thing to paid ads.

## AI-referred visitors convert at a premium too

A separate, related data point from [[semrush-optimize-for-agentic-web]]
(cited there, not independently verified in this wiki): "the average AI
search visitor is worth 4.4 times more than a traditional organic
visitor in conversion value." This is a different measurement from the
citation-premium/CTR data above — it's about the value of a session
once an AI tool *does* refer traffic to you, rather than the CTR effect
of being cited vs. not. Consistent in direction (AI-sourced traffic is
worth more) but not the same metric, and worth tracking as a distinct
number rather than conflating the two.

## AIO prevalence trajectory and industry saturation (2025)

Per [[semrush-ai-overviews-study-2025]] (10M+ keywords, Semrush/Datos) —
a much larger-scale prevalence dataset than the query-format breakdown
above, covering the full 2025 calendar year:

- **Prevalence rose sharply then pulled back**: 6.49% of queries (start
  of 2025) → peaked 24.61% (July) → settled at 15.69% (November) — 155%
  Q1-to-Q4 growth, with a mid-year peak-then-retreat shape rather than
  steady monotonic growth.
- **AIOs expanded well beyond informational intent** over the year:
  commercial queries 8.15%→18.57%, transactional 1.98%→13.94%,
  navigational 0.84%→10.33%. Note this is a *different snapshot* than
  this page's own intent-based prevalence figures above (informational
  36%, commercial 8%, transactional 5%, from Seer's dataset) — the two
  studies use different methodologies/time windows, so treat these as
  complementary data points rather than reconciled figures.
- **Zero-click rate actually decreased** (33.75%→31.53%) on keywords
  tracked before/after AIO introduction. This is a *different metric*
  than this page's organic-CTR data above (which still shows AIO
  presence suppressing organic clicks 38% below a no-AIO baseline, even
  for cited brands) — not a contradiction: more queries generating *some*
  click (fewer zero-click sessions) is compatible with the *rate* of
  clicks-per-impression on AIO-present queries still running below
  non-AIO queries.
- **Industry saturation**: Science most AIO-saturated (25.96%),
  Computers & Electronics (17.92%), People & Society (17.29%); Food &
  Drink grew fastest (+7.25% since March); Real Estate, Shopping, and
  Arts & Entertainment least impacted (<3%).
- **AIO-triggering keywords skew long-tail**: ~60% have ≤100 monthly
  searches, 60% fall in the 21-60 keyword-difficulty range — useful for
  prioritizing which pages to audit for AIO risk beyond just query
  format (see [[geo-content-optimization-tactics]]'s query-format-risk
  table).
- **SERP feature co-occurrence shifted** alongside AIOs: featured
  snippets, image carousels, and organic reviews co-occur less; Related
  Searches (95.32%) and People Also Ask (90.03%) are now nearly
  guaranteed alongside an AIO; Google Ads co-occurrence jumped from <1%
  (March) to 25% (November) — AIO pages are increasingly ad-adjacent.

## AI-visit growth is outpacing AI-referral growth

Per [[similarweb-how-to-be-the-brand-ai-recommends-2026]] — a narrower,
corroborating data point (not the same metric as the citation-premium
data above): Similarweb clickstream data shows visits to AI tools
(ChatGPT, Gemini, Claude) growing much faster than referral traffic
*from* those tools to other sites, with the gap widening through
2025-2026. Directionally consistent with this page's zero-click framing
and [[ai-traffic-scale-vs-hype]]'s "most AI interactions end without a
click" theme — AI usage is growing, but the fraction of that usage that
sends a click elsewhere is not growing at the same rate. Reinforces why
[[ai-citation-landscape]]'s citations-vs-mentions distinction matters:
mentions (which don't require a click) may be a more representative
growth metric than referral traffic alone.

## Caveats

The authors are explicit that: this is correlational, not causal
(higher-authority brands are simply more likely to be cited in the first
place, confounding the citation-premium numbers); AIO status labels are
static snapshots rather than real-time; one account skews the "AIO
present, brand not cited" segment significantly (47% of impressions at a
0.20% CTR — excluding it raises the segment average from 0.94% to
~1.61%); and forecasts past February 2026 should be read as directional
floors, not predictions.

## See also

- [[generative-engine-optimization]] — the content tactics this page
  provides economic justification for.
- [[ai-citation-landscape]] — what actually gets cited, complementing
  this page's data on what citation is worth once it happens.
- [[geo-content-optimization-tactics]] — actionable query-format risk
  guidance and the impressions-vs-clicks measurement checklist drawn
  from this source.
- [[optimizing-for-the-agentic-web]] — the source of the AI-referred-
  visitor conversion-value stat above, plus a fuller measurement
  framework for AI-driven traffic and conversions.
- [[semrush-ai-overviews-study-2025]] — the 10M+-keyword prevalence
  trajectory, industry saturation, and SERP co-occurrence data in the
  section above.
- [[ai-traffic-scale-vs-hype]] — a scale check on how much traffic AI
  surfaces (including AI Overviews) actually represent relative to
  search and social overall.
