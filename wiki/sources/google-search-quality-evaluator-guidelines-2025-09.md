---
type: source
tags: [seo, aeo]
date_published: 2025-09-11
date_ingested: 2026-07-07
origin: raw/reports/google-search-quality-evaluator-guidelines-2025-09.pdf
---

# Google Search Quality Rater Guidelines (September 11, 2025 edition)

**Citation:** Google. "General Guidelines" (Search Quality Rater
Guidelines). September 11, 2025 edition.
https://static.googleusercontent.com/media/guidelines.raterhub.com/en//searchqualityevaluatorguidelines.pdf

The official, ~182-page document Google gives to the human quality
raters who benchmark its search ranking systems. Not a ranking algorithm
itself, but the canonical source for concepts (E-E-A-T, YMYL, Page
Quality) that Google's own guidance and the SEO industry treat as
ranking-relevant. This wiki extracted and summarized the sections most
relevant to SEO/AEO rather than reproducing the full document (see the
PDF in `raw/` for complete text).

## Key takeaways

- **E-E-A-T** (Experience, Expertise, Authoritativeness, Trust) —
  **Trust is explicitly "the most important member of the family."** A
  page with abundant Experience/Expertise/Authoritativeness can still be
  rated low if untrustworthy: "a financial scam is untrustworthy, even if
  the content creator is a highly experienced and expert scammer." E, E,
  and A all exist to support the Trust assessment, not as independent
  scoring dimensions.
- **YMYL ("Your Money or Your Life")** topics — health, financial
  security, government/civics/society, and other topics where inaccurate
  content could cause real harm — get the highest scrutiny for accuracy
  and trust. YMYL-ness is explicitly a spectrum, not binary.
- **Page Quality has five tiers**: Lowest, Low, Medium, High, Highest —
  each defined by MC (Main Content) quality/effort, reputation, E-E-A-T,
  and (for Lowest) explicit harm/deception/spam screening that happens
  *before* other quality considerations.
- **Three abuse patterns most relevant to AI-era content:**
  - **Scaled Content Abuse**: "Using automated tools (generative AI or
    otherwise) as a low-effort way to produce many pages that add
    little-to-no value... no matter how it's created" should be rated
    **Lowest**. This is Google's explicit policy reasoning behind why
    content *volume* alone doesn't help (see
    [[ai-visibility-correlation-factors]]'s near-zero content-volume
    correlation finding) — it isn't just that volume doesn't help, it's
    that low-effort scaled volume is an explicit penalty target.
  - **Site Reputation Abuse**: third-party content hosted on an
    established site mainly to exploit that site's ranking signals
    (excludes wire services, syndicated news, user-generated forums,
    genuine editorial/advertorial content, and properly-handled affiliate
    links).
  - **Expired Domain Abuse**: buying an expired, previously-trusted
    domain (e.g. a school or government site) and repurposing it for
    unrelated, often monetized content.
- **Query intent taxonomy**: Know (incl. **Know Simple** — short,
  factual, single-answer queries like "how tall is Barack Obama"), Do,
  Website, and Visit-in-person queries. Know Simple queries are exactly
  the kind that get pulled into short, direct answer treatments —
  directly relevant to structuring AEO-friendly content.
- **Needs Met scale**: Fully Meets → Highly Meets → Moderately Meets →
  Slightly Meets → Fails to Meet — how raters judge whether a result
  actually satisfies the query's underlying intent.

## What this updated in the wiki

- Created [[e-e-a-t-and-page-quality]] (concept): YMYL, E-E-A-T, Page
  Quality tiers, and the three abuse types.
- Created [[search-intent-and-needs-met]] (concept): query intent
  taxonomy and the Needs Met scale.
- Updated [[geo-content-optimization-tactics]] with an E-E-A-T
  signal-building checklist, an explicit warning against scaled
  low-effort AI content, and Know-Simple query-structuring guidance.
- Cross-linked from [[generative-engine-optimization]],
  [[google-ai-optimization-guide]]'s "helpful, people-first" framing, and
  [[ai-visibility-correlation-factors]]'s content-volume finding.
- No conflicts — this source provides the official policy foundation
  that several prior sources' empirical findings were implicitly
  describing.
