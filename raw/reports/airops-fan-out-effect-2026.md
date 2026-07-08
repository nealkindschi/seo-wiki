---
title: "The Fan-Out Effect: What Happens Between a Query and a Citation"
author: AirOps Team, in partnership with Kevin Indig (Growth Memo)
publication: AirOps
url: https://www.airops.com/report/the-fan-out-effect-what-happens-between-a-query-and-a-citation
date_published: 2026-04-13
date_fetched: 2026-07-07
---

# The Fan-Out Effect: What Happens Between a Query and a Citation

**Publication Date:** April 13, 2026
**Author:** AirOps Team (in partnership with Kevin Indig, Growth Memo)

## Executive Summary

Examines ChatGPT's internal citation process by analyzing how queries
transform into cited sources. Retrieval position dominates all other
factors in determining whether content gets cited.

## Methodology

**Dataset Scale:**
- 16,851 unique queries across 10 categories
- 50,553 total ChatGPT responses (3 runs per query)
- 353,799 pages analyzed
- 815,484 coverage scoring rows
- 1,511,251 fan-out detail rows

**Process:** Captured ChatGPT's full response pipeline: answer text,
internal fan-out searches, retrieved URLs, cited URLs, and complete page
HTML. Heading similarity computed using BAAI/bge-base-en-v1.5 embeddings
(768 dimensions), cosine similarity thresholds 0.60-0.80.

## Key Findings

### 1. Retrieval Rank is Dominant
Position 1 in ChatGPT's retrieval results: 58.4% citation rate.
Position 10: 14.2%. A 4x gap that overwhelms content-quality signals.
Even pages with strong heading relevance (similarity ≥0.8) drop from
79.6% citation at rank 1 to 21.5% at rank 11+.

### 2. Heading Match Beats Comprehensive Coverage
Pages with headings closely matching the query: 41.0% citation (0.90+
similarity) vs. 29-30.2% for weak matches (<0.50). Critical finding on
breadth: controlling for query relevance, pages covering 26-50% of
fan-out subtopics outperformed those covering 100% (38.2% vs 34.0%).

### 3. Focused Pages Outperform Comprehensive Guides
Exhaustive coverage reduces citations when primary relevance is
constant. Matching 3-4 distinct subheadings reduces citation by 6pp vs.
matching 0-1 subheadings.

### 4. Authority Signals Don't Correlate
Domain authority and backlinks show no positive correlation with AI
citation, slightly inversely correlated. Always-cited pages averaged DA
53 vs. 56 for never-cited pages. High-authority platforms show wildly
disparate results: YouTube (DA 100, 2.4% citation), Wikipedia (DA 95,
59.2%), Reddit (DA 92, 29.9%).

## Content Structure Findings

- **Word count sweet spot:** 500-2,000 words optimal; >5,000 words
  underperforms shorter content (28.6% vs 30.5%).
- **Subheading structure:** 4-10 H2-H4 headings optimal for articles
  (33.2% citation). Product pages perform best with zero headings
  (43.2%).
- **Schema markup:** +6.5pp citation advantage for JSON-LD. Top types:
  MedicalWebPage (47%), BreadcrumbList (46.2%), FAQPage (45.6%).
- **Readability:** College-level (Flesch-Kincaid 16-17) achieves 35.9%
  citation, outperforming simpler and more academic text.

## Site Type Analysis

| Site Type | Citation Rate | Median Rank | Primary Match |
|---|---|---|---|
| Wikipedia | 59.2% | 24.0 | 0.576 |
| Health Publishers | 46.4% | 7.0 | 0.734 |
| Travel Platforms | 42.3% | 8.0 | 0.764 |
| Government | 34.4% | 8.0 | 0.649 |
| Reddit | 29.9% | 11.0 | 0.743 |
| YouTube | 2.4% | 15.0 | 0.714 |

**Wikipedia exception:** highest citation despite worst retrieval rank,
via extreme density (4,383 avg words, 31 lists, 6.6 tables/page).

**Government trust signal:** at high query match (0.8+), government
pages cite at 49.1% vs. 35.2% for non-government.

## Citation Distribution Patterns

Bimodal: 58% of pages never cited, 25% always cited, 17% intermittent.
On-page signals (word count, headings, readability) show virtually no
difference between always-cited and never-cited pages — retrieval rank
is the real separator.

**Answer positioning:** 40.7% of citations appear in first third of
response. Rank 0-2 pages cited at position 2.2 on average; rank 11+
pages at position 6.2.

## Freshness Signal

Optimal age 30-89 days (32.8% citation). Older than 2 years: 27.5%
(-5pp). Less than 30 days: 25.3% (indexing delay). Freshness only
amplifies when content relevance is already strong (+4.2pp); among
weak-match pages, age effects are negligible. By vertical: Finance 15pp
gap, Travel 19pp gap (largest), E-commerce barely matters.

## Memory Citations

6,371 citations appeared without corresponding search results —
ChatGPT referencing training data. Reddit accounts for 11.1% of memory
citations. Memory-cited pages show identical content profiles to
search-cited pages.

## Strategic Implications

1. Retrievability precedes content quality.
2. Query specificity over comprehensiveness.
3. Structure provides marginal gains (2-6pp), cannot overcome poor
   retrieval or weak relevance.
4. Authority metrics are unreliable proxies for AI citation.
5. Wikipedia's playbook is non-replicable at normal-publisher scale.
6. Refresh aging content strategically, especially in dynamic verticals.

## Data Quality Notes

Excludes 806 queries with unfetchable HTML and 35,020 low-content pages
(<100 words). Primary similarity comparisons use H1-H4 headings;
fan-out coverage uses H2-H4 only. Default 0.50 similarity threshold
created ceiling effects, so the report emphasizes 0.70-0.80 thresholds.

(Note: full report fetched and summarized via WebFetch; this raw file
captures the extracted summary, not a full HTML mirror.)
