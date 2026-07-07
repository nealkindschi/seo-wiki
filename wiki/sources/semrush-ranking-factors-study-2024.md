---
type: source
tags: [seo]
date_published: 2024-01-03
date_ingested: 2026-07-07
origin: raw/reports/semrush-ranking-factors-study-2024.pdf
---

# Ranking Factors Study 2024 (Semrush)

**Citation:** Semrush. "Ranking Factors Study 2024." Published ~January
2024. https://www.semrush.com (report PDF).

## Methodology

Analyzed 16,298 English-language US keywords (100+ monthly searches,
non-navigational, non-branded, non-adult), collecting mobile SERPs for
each. Analyzed the top 20 positions per SERP (excluding Wikipedia/YouTube
to avoid skew), for a total of 300,000 organic positions. Calculated
three metrics per factor: **Factor Influence** (Spearman correlation
between position and factor value — same statistical method as
[[ahrefs-ai-brand-visibility-correlations]]), **Factor Strength**
(percentage difference in factor value between top-3 and bottom-5
positions), and **Benchmarks** (average/median values). Explicitly
excludes Search Generative Experience (SGE)/AI features — this is a
classic organic-SERP study, not an AI-answer study.

## Key takeaways

- **Text relevance is the top-ranking factor** (90.6% avg / 93.9% median
  correlation for top-10) — topical coverage of the query and related
  subtopics, not literal keyword matching.
- **Keyword-in-title/meta-description correlates minimally.** Semantic
  similarity (BERT/embeddings) between title and topic correlates
  better than exact keyword presence — "including exact match keywords
  in the title or the meta description does not seem to play a role."
  Parallels [[geo-generative-engine-optimization-aggarwal-2023]]'s
  keyword-stuffing-doesn't-work finding, but for classic SERPs.
- **Backlinks/authority still matter**: Domain Authority Score and Page
  Authority Score correlate at 0.21 and 0.19 respectively. "Gary Illyes
  saying they're no longer among the top 3 ranking factors at Pubcon
  resonates — yet, they're still important." Acknowledged
  chicken-or-egg: higher ranking can itself generate more backlinks.
- **Content length shows no correlation; content quality does.**
  "Ignore talks around content length or word count." Reinforces
  [[e-e-a-t-and-page-quality]]'s Scaled Content Abuse framing and
  [[ai-visibility-correlation-factors]]'s content-volume-doesn't-help
  finding — now confirmed independently for classic SERP ranking too.
- **Schema markup correlates very little** — "don't go overboard with
  Schema... it can bring on a penalty if you're seen as using it to
  manipulate rankings."
- **Reviews/star ratings correlate meaningfully with rankings**, and the
  study explicitly ties this to E-E-A-T: "For Google, trust is the
  central piece in E-E-A-T, so it's super important to strengthen trust
  for your website at all times" — direct, independent empirical
  confirmation of [[e-e-a-t-and-page-quality]]'s framework, citing the
  Search Quality Evaluator Guidelines by name.
- **Author trust signals correlate weakly on their own**, but the study
  notes authorship/experience/expertise are explicitly named in the
  Search Quality Evaluator Guidelines as rating factors regardless.
- **User signals** (direct traffic share ~31%, branded search traffic
  share ~24%, time on site ~9:42, bounce rate ~60.5%) support a
  "build your brand" takeaway — parallels
  [[ai-visibility-correlation-factors]]'s branded-search-volume
  correlation for AI-mention visibility.
- **Technical/UX factors (Core Web Vitals, HTTPS) correlate weakly** —
  framed as a likely tie-breaker rather than a primary ranking lever,
  though still relevant to overall user experience.
- URLs ranking #1 for one term tend to rank for ~4x as many other terms
  as position-20 pages — breadth/depth of topical coverage compounds.

## What this updated in the wiki

- Created [[traditional-seo-ranking-factors]] (concept): the classic
  organic-SERP correlation data, contrasted with AI-citation correlation
  factors.
- Created new playbook [[classic-seo-ranking-factors]] (actionable
  tactics for classic SERP ranking, distinct from AEO-specific tactics).
- Cross-linked from [[ai-visibility-correlation-factors]] and
  [[e-e-a-t-and-page-quality]] as independent empirical confirmation.
- No conflicts — reinforces existing findings from an independent,
  larger-scale, classic-SERP-focused data source.
