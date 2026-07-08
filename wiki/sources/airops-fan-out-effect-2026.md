---
type: source
tags: [seo, aeo]
date_published: 2026-04-13
date_ingested: 2026-07-07
origin: raw/reports/airops-fan-out-effect-2026.md
---

# The Fan-Out Effect: What Happens Between a Query and a Citation (AirOps)

**Citation:** AirOps Team, in partnership with Kevin Indig (Growth
Memo). "The Fan-Out Effect: What Happens Between a Query and a
Citation." AirOps. Published 2026-04-13.
https://www.airops.com/report/the-fan-out-effect-what-happens-between-a-query-and-a-citation
(16,851 queries, 50,553 ChatGPT responses, 353,799 pages analyzed,
815,484 coverage-scoring rows, 1,511,251 fan-out detail rows —
BAAI/bge-base-en-v1.5 embedding-based heading-similarity scoring.)

## Key takeaways

- **Retrieval rank dominates citation**: position 1 in ChatGPT's
  retrieval = 58.4% citation rate vs. 14.2% at position 10 (4x gap) —
  overwhelms content-quality signals. Even strong heading relevance
  (≥0.8 similarity) drops from 79.6% at rank 1 to 21.5% at rank 11+.
- **Heading-query match is the strongest content signal**: 41.0%
  citation at 0.90+ similarity vs. 29-30.2% for weak matches.
- **Comprehensiveness backfires when relevance is constant**: pages
  covering 26-50% of fan-out subtopics outperform 100%-coverage pages
  (38.2% vs. 34.0%); matching 3-4 subheadings reduces citation 6pp vs.
  matching 0-1.
- **Authority signals show no positive correlation with citation** —
  slightly *inverse*. Always-cited pages averaged DA 53 vs. 56 for
  never-cited pages. High-DA platforms diverge wildly: YouTube (DA 100,
  2.4% citation) vs. Wikipedia (DA 95, 59.2%) vs. Reddit (DA 92, 29.9%).
- **Structural findings**: 500-2,000 word sweet spot (>5,000 words
  underperforms); 4-10 H2-H4 headings optimal for articles, zero
  headings best for product pages; schema markup +6.5pp (MedicalWebPage/
  BreadcrumbList/FAQPage strongest); college-level readability
  (Flesch-Kincaid 16-17) peaks at 35.9%.
- **Wikipedia is a non-replicable outlier**: highest citation (59.2%)
  despite the *worst* median retrieval rank (24.0), apparently via
  extreme density (4,383 avg words, 31 lists, 6.6 tables/page) rather
  than good positioning.
- **Government pages show a trust premium** at high query match (0.8+):
  49.1% citation vs. 35.2% for non-government.
- **Citation distribution is bimodal**: 58% of pages never cited, 25%
  always cited, only 17% intermittent — and on-page signals barely
  differ between always/never groups, reinforcing retrieval rank as the
  real separator, not content quality.
- **Freshness**: 30-89 days optimal (32.8%), decays past 2 years (-5pp);
  amplifies only when relevance is already strong (+4.2pp); varies
  hugely by vertical (Finance 15pp gap, Travel 19pp gap, e-commerce
  barely affected).
- **"Memory citations"**: 6,371 citations had no corresponding search
  result — ChatGPT citing from training data directly, with content
  profiles identical to search-cited pages.

## Relationship to existing wiki claims

- **Net-new mechanism**: retrieval-rank-as-gatekeeper is not currently
  covered anywhere in the wiki. [[ai-citation-landscape]] and
  [[geo-generative-engine-optimization-aggarwal-2023]] cover citation
  *composition* and content-level *tactics*, but nothing on the
  retrieval-ranking step that happens before a page is even a citation
  candidate. This adds a new, foundational layer.
- **Extends** [[geo-content-optimization-tactics]]'s domain-specific
  guidance table with a nuance: comprehensive coverage can *reduce*
  citation odds relative to focused, high-relevance content when
  fan-out subtopic coverage exceeds ~50%. This complicates (does not
  outright contradict) the existing Tier 1 "Cite Sources"/"Statistics
  Addition" guidance, which is about *how* to write a passage, not how
  broadly a page should cover a topic.
- **Conflicts with** [[ai-visibility-correlation-factors]] and
  [[growth-memo-topics-matter-for-third-party-authority]] on the
  authority-correlation question — see Conflicting Evidence section
  added to [[ai-visibility-correlation-factors]].

## What this updated in the wiki

- New "Retrieval rank as the primary citation gatekeeper" section added
  to [[ai-citation-landscape]].
- New "Fan-out breadth vs. focus" and "Structural findings" additions to
  [[geo-content-optimization-tactics]], plus a freshness-by-vertical
  note.
- Added a Conflicting Evidence section to
  [[ai-visibility-correlation-factors]] reconciling (partially) this
  source's "authority doesn't correlate with citation" finding against
  the existing Ahrefs Domain Rating correlation and the Growth Memo
  Authority Score correlation.
