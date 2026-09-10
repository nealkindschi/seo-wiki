---
type: concept
tags: [seo, aeo]
updated: 2026-09-10
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

## Commercial vs. transactional AIO divergence and CPC clustering

Per [[semrush-ai-overviews-commercial-search-2026]] (600,000+ keywords,
Nov 2025-Apr 2026, same Semrush research team as
[[semrush-ai-overviews-study-2025]]) — a later time window than that
study's full-2025 dataset, showing a notable shift within the intent
mix:

- **Commercial-intent AIOs grew 71%** over this window; **transactional-
  intent AIOs *decreased* 5%** — a divergence from the earlier study's
  2025 data (where both commercial and transactional prevalence grew
  through the year). Read together, this looks like a continuation of
  that earlier study's "prevalence peaked in July 2025 then settled
  lower by November" pattern, now showing up specifically within
  transactional intent on a lag, while commercial intent is still
  climbing. Flagged as a genuine trend shift to monitor, not a data
  contradiction — different time windows, same methodology/team.
- Finance led commercial-intent AIO growth (+231%), followed by
  Computers & Electronics (+107.62%) and Games (+76.66%).
- **AIOs now cluster on the highest-CPC keywords** in nearly every
  industry — Jobs & Education sees AIOs on >60% of its most expensive
  keywords; average CPC with-AIO vs. without: Jobs & Education $5.02 vs.
  $1.51, Finance $4.84 vs. $2.14. This sharpens this page's existing
  Google Ads co-occurrence finding (<1%→25% through 2025): it's not just
  that more ads appear near AIOs generally, but that AIOs concentrate
  specifically on the *most commercially valuable* keywords.
- **Google Ads + AIO coexistence on the same SERP is now ~2x more
  frequent** than a year prior — AIOs have moved well beyond low-intent
  informational queries into ad-adjacent commercial territory.
- Largest commercial-vs-transactional AIO gaps: Internet & Telecom,
  Finance, Travel (longer research-phase categories, consistent with
  this page's existing query-format-risk data on comparison/review
  queries). Food & Drink is inverted (16% transactional vs. 14%
  commercial) — quick-decision categories show less AIO integration.
- **Strategic framing**: marketers now compete across four SERP
  positions simultaneously — within the AI Overview summary, among its
  citation sources, in organic rankings, and in paid placements.

## AI recommendation → downstream visit impact

Per [[similarweb-downstream-impact-of-ai-visibility-2026]] (opted-in US
desktop panel, July-December 2025, Finance/Travel/Beauty verticals) —
the first source in this wiki to trace an AI *mention/recommendation*
(as distinct from a citation link) through to measured downstream site
visits, not just click-through on a citation:

- **Brands recommended by ChatGPT are 2.5x more likely to receive a
  visit within 7 days** than a non-recommended direct competitor,
  consistent across all three verticals studied (e.g. American Express
  7.2% vs. Capital One 3.1%; Skyscanner 9.5% vs. Kayak 7.6%; Sephora
  7.9% vs. Ulta 3.3%).
- **AI-influenced visitors engage roughly 2x harder**: 12.0 pages / 11.8
  minutes per session vs. 6.5 pages / 5.6 minutes for non-AI-influenced
  visitors — an independent, differently-measured data point pointing
  the same direction as this page's existing "AI visitor worth 4.4x more
  in conversion value" stat.

**Important measurement caveat — AI's traffic influence is likely
undercounted**: 55.9% of this AI-influenced traffic arrived via *search*
(user gets a recommendation, then searches the brand name), not as a
direct ChatGPT referral, and only 19.9% arrived as direct traffic.
Standard analytics records the search-driven visits as ordinary branded
organic search, invisibly absorbing AI's actual causal role. This means
referral-based measurements of "how much traffic AI drives" —
including [[ai-traffic-scale-vs-hype]]'s clickstream-based finding that
AI tools are a small fraction of overall traffic — likely understate
AI's true influence, even though AI tools remain small as a *direct*
traffic channel. The two findings aren't in conflict; this one adds an
attribution caveat to how the other's traffic-scale data should be
read.

**Caveats on this source itself** (stated by Similarweb): US desktop
only, excludes mobile/international; three verticals/named brand pairs,
not a whole-web sample; explicitly correlational, not proven causal.

## What triggers an AIO: question form and query length

Per [[arxiv-measuring-google-ai-overviews-2026]], an academic audit of
55,393 **trending** queries (Mar–Apr 2026) — a different query
population from the brand/commercial corpora behind the prevalence
numbers above, so read the contrasts rather than the absolute rate:

- **Question-form queries activate AIOs at 64.7% vs. 9.5% for
  non-question queries — 6.8x.** Open-ended explanatory interrogatives
  are strongest (`how` 84.3%, `why` 73.4%); closed-form lookups weakest
  (`who` 47.9%, `did` 39.8%) but still 4–5x non-question queries.
- **Query length amplifies activation independently of phrasing.**
  Restricting to non-question queries only, activation climbs from
  **9.9% at one word to 38.7% at six or more words** — length is not
  merely a proxy for asking a question.
- Category spread is 13x: Beauty & Fashion 3.5%, Travel & Transport
  8.7%, Sports 9.8%, Entertainment 16.3%, Business & Finance 26.2%,
  Health 26.6%, Science 39.9%, Hobbies & Leisure 46.1%.
- **Sensitive-topic suppression is selective, not blanket**: Politics
  (7.5%) and Law & Government (9.6%) run below average, but Health
  (26.6%) runs well above it.
- AIO activation spikes around major public events (Oscars, NCAA
  tournament, Artemis II launch drove 1.3–2.2x mean query volume) —
  exposure concentrates exactly when information demand peaks.

Directionally this corroborates the query-format data from
[[seerinteractive-aio-ctr-impact-2026-update]] above (question-format
85.9%, single-word 27.3%) at lower absolute levels, consistent with a
trending-query corpus that is 51.4% Sports. The ordering — questions
≫ non-questions, long ≫ short — replicates across both.

## Supply side: who is paying for AIO content, and who keeps the ads

[[arxiv-measuring-google-ai-overviews-2026]] measures the economics
from the publisher side rather than the click side:

- **50.63% of AIO-cited pages (30,994 of 61,212) display visible ads**
  — more than half the pages whose content makes AIO synthesis
  possible run ad-supported models that depend on the page views AIOs
  intercept. A conservative floor: the 14.2% of references pointing to
  social/video platforms were not crawled and are counted as ad-free,
  and affiliate/subscription/lead-gen monetization is invisible to the
  method entirely.
- By category: Hobbies & Leisure 63.14%, Sports 60.19%, Entertainment
  55.50%, Science 41.85%, Business & Finance 39.97%, Law & Government
  29.47%, Health 27.77%.
- **Only 2.16% of AIO-bearing SERPs display Google sponsored ads, and
  just 0.51% place them above the AIO.** The authors' conclusion:
  "AIOs restructure the page in a way that preserves Google's ad
  capture while reducing click-throughs to publishers."

This is the supply-side complement to the demand-side CTR data above:
the click compression documented by
[[seerinteractive-aio-ctr-impact-2026-update]] lands on a citation
pool where the majority of pages are monetized per-pageview, while
Google's own paid inventory on those SERPs is largely undisturbed.

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
- [[ai-overview-grounding-and-fidelity]] — whether AIO claims are
  actually supported by the pages they cite (~11% are not), the
  accuracy counterpart to this page's economics.
- [[optimizing-for-the-agentic-web]] — the source of the AI-referred-
  visitor conversion-value stat above, plus a fuller measurement
  framework for AI-driven traffic and conversions.
- [[semrush-ai-overviews-study-2025]] — the 10M+-keyword prevalence
  trajectory, industry saturation, and SERP co-occurrence data in the
  section above.
- [[semrush-ai-overviews-commercial-search-2026]] — the later-window
  commercial-vs-transactional divergence and CPC-clustering data above.
- [[ai-traffic-scale-vs-hype]] — a scale check on how much traffic AI
  surfaces (including AI Overviews) actually represent relative to
  search and social overall; read alongside the attribution-
  undercounting caveat above.
- [[similarweb-downstream-impact-of-ai-visibility-2026]] — the
  AI-recommendation-to-visit study in the section above.
