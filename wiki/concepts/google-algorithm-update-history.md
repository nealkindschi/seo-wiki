---
type: concept
tags: [seo]
updated: 2026-11-10
---

# Google Algorithm Update History

A taxonomy and timeline of Google's named search ranking updates and
incidents, based on
[[google-search-status-dashboard-history]] (a live Google status page,
snapshotted 2026-07-07 covering July 2021–June 2026, refreshed
2026-11-10 through the start of the November 2026 core update). Full chronological
list lives in `wiki/timeline.md`; this page synthesizes the patterns.

## Update types

- **Core update**: broad changes to Google's overall ranking systems,
  not targeted at a specific issue. The most frequent update type,
  recurring roughly every 2-4 months throughout the whole period covered.
- **Spam update / link spam update**: targets spam and manipulation
  tactics specifically (e.g., link schemes), separate from general core
  ranking changes.
- **Helpful content update**: a distinct named update type that appeared
  three times — August 2022, December 2022, September 2023 — and never
  again afterward in this dashboard's history.
- **Product reviews update / reviews update**: a distinct named update
  type appearing seven times from December 2021 through November 2023,
  renamed partway through from "product reviews update" to just "reviews
  update," and never appearing again afterward.
- **Page experience update**: appeared once (desktop, February 2022) in
  this dashboard's coverage window.
- **Discover update**: appeared once (February 2026) in this dashboard's
  coverage window.
- **Ranking ongoing issue**: an incident/bug report rather than an
  intentional named update — appeared twice (October 2023, August 2024).

## Helpful Content and Reviews systems appear to have merged into Core

Two update types that were shipped as their own separate, named
releases early in the dashboard's history — Helpful Content Updates and
Product Reviews/Reviews Updates — stop appearing as distinct entries
after September 2023 and November 2023 respectively, even though core
updates continue on their regular cadence afterward. This pattern is
consistent with Google folding both systems into its core ranking
systems rather than continuing to ship them as separately-named,
separately-announced updates. This wiki has not yet ingested a source
that explicitly confirms this as Google's stated reasoning — flagged as
an inference from the update-naming pattern, not a directly-sourced
claim.

## 2026 cadence

- **Core updates**: March 27, May 21, and November 10 (in progress as
  of 2026-11-10). The May-to-November gap is close to six months, longer
  than the usual 2–4.
- **Spam updates**: March 24, June 24, August 18, September 24. Four in
  one year is the most the dashboard has recorded. Durations swing
  widely: under a day in March, nearly 14 days in September.
- **Discover update**: February 5, the only one on the dashboard.
- Practical read: in 2026, spam updates were more frequent than core
  updates. When diagnosing a mid-year traffic drop, rule out a spam
  update before assuming a core one.

## Practical relevance

- **Timing content/SEO work around update cadence**: core updates land
  roughly every 2-4 months; expect ranking volatility in the weeks
  following each one (durations in the source range from under a day to
  over 40 days).
- **"Helpful content" and "product reviews" as evaluation criteria
  still matter**, even though they're no longer shipped as separately
  named updates — they're presumably now embedded in the standing core
  ranking systems, consistent with [[e-e-a-t-and-page-quality]]'s
  framing of "helpful, people-first content" as an ongoing quality
  standard rather than a one-time update to react to.
- Check `wiki/timeline.md` directly for the full dated list, and
  re-ingest this source periodically since it's a live page that grows
  over time.

## See also

- [[e-e-a-t-and-page-quality]] — the quality framework these updates
  are presumably built on.
- `wiki/timeline.md` — the full chronological event list this concept
  synthesizes.
- [[classic-seo-ranking-factors]] — the tactic-level playbook these
  updates repeatedly rewarded or penalized; useful for reading any
  given update against what it actually changed in practice.
- [[content-pruning-playbook]] — the standard remediation after a core
  update hits a site with a large low-quality content footprint.
