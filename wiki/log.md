# Log

Append-only chronological record of wiki activity. Each entry starts with
a consistent prefix so the file stays greppable, e.g.
`grep "^## \[" wiki/log.md | tail -5`.

Format:
```
## [YYYY-MM-DD] ingest | <source title>
## [YYYY-MM-DD] query | "<question>"
## [YYYY-MM-DD] lint | <summary of findings>
## [YYYY-MM-DD] conflict | <topic> — <one-line description>
```

---

## [2026-07-07] ingest | GEO: Generative Engine Optimization (Aggarwal et al., 2023/2024)

First source ingested. Created [[generative-engine-optimization]] (concept)
and [[geo-content-optimization-tactics]] (playbook). No prior wiki content
existed, so no conflicts to reconcile.

## [2026-07-07] ingest | Google's Guide to Optimizing for Generative AI Features on Google Search

Updated [[generative-engine-optimization]] and
[[geo-content-optimization-tactics]] with Google's official AI-optimization
guidance.

## [2026-07-07] conflict | GEO/AEO tactics vs. Google's official guidance — retrieval-stage vs. citation-stage framing

[[generative-engine-optimization]]: reconciled as addressing different
funnel stages (see Conflicting Evidence section on that page); flagged as
not fully resolved whether Google's AI Overviews respond to GEO's
citation-style tactics the same way third-party generative engines do.

## [2026-07-07] ingest | AI Features and Your Website (Google Search Central)

Extended [[generative-engine-optimization]] with a measurement section
(Search Console "Web" reporting) and created new playbook
[[controlling-ai-feature-inclusion]] for opt-out/control mechanisms.
Agrees with and extends [[google-ai-optimization-guide]]; no conflicts.

## [2026-07-07] ingest | Generative Pulse: What Is AI Reading? (Muck Rack, May 2026)

Created new concept [[ai-citation-landscape]] for empirical citation
patterns across ChatGPT/Claude/Gemini. Added a provider-specific tactics
section to [[geo-content-optimization-tactics]] and cross-linked from
[[generative-engine-optimization]]. Landscape/empirical data, complements
rather than conflicts with existing sources.

## [2026-07-07] ingest | Top Brand Visibility Factors in ChatGPT, AI Mode, and AI Overviews (Ahrefs)

Created new concept [[ai-visibility-correlation-factors]] for the
75k-brand correlation study. Added brand-level correlational guidance to
[[geo-content-optimization-tactics]] (YouTube presence, earned mentions,
ChatGPT-targeting for smaller brands).

## [2026-07-07] conflict | Cross-provider domain-level divergence vs. brand-level mention overlap

[[ai-citation-landscape]] and [[ai-visibility-correlation-factors]]:
reconciled as different units of analysis (which source domains get
cited, vs. whether a brand gets mentioned at all) — see Conflicting
Evidence sections on both pages; flagged as unresolved since no source
has directly tested both at once.

## [2026-07-07] ingest | AIO Impact on Google CTR: 2026 Update (Seer Interactive)

Created new concept [[aio-ctr-impact]] for the citation-premium and CTR
economics data. Added query-format AIO-risk table and an
impressions-vs-clicks measurement checklist to
[[geo-content-optimization-tactics]]; cross-linked from
[[generative-engine-optimization]] as the economic rationale for
citation tactics. No conflicts.

## [2026-07-07] ingest | Google Search Quality Rater Guidelines (Sept 2025 edition)

Created two new concepts: [[e-e-a-t-and-page-quality]] (YMYL, E-E-A-T,
Page Quality tiers, and the three AI-era abuse patterns) and
[[search-intent-and-needs-met]] (query intent taxonomy, Needs Met
scale). Added E-E-A-T signal-building and Know-Simple answer-structuring
guidance to [[geo-content-optimization-tactics]], including an explicit
warning against Scaled Content Abuse. Cross-linked from
[[generative-engine-optimization]] (retrieval-eligibility foundation)
and [[ai-visibility-correlation-factors]] (official policy explanation
for the content-volume finding). No conflicts — this source provides
the official policy foundation several prior sources' findings were
implicitly describing.
