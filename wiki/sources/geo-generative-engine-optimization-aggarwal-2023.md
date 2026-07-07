---
type: source
tags: [aeo]
date_published: 2023-11-16
date_ingested: 2026-07-07
origin: raw/studies/geo-generative-engine-optimization-aggarwal-2023.pdf
---

# GEO: Generative Engine Optimization (Aggarwal et al., 2023/2024)

**Citation:** Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin
Kalyan, Karthik Narasimhan, Ameet Deshpande. "GEO: Generative Engine
Optimization." Proceedings of KDD '24 (August 25–29, 2024, Barcelona,
Spain). arXiv:2311.09735 (v1: 2023-11-16, v3: 2024-06-28).
https://arxiv.org/abs/2311.09735

## Key takeaways

- Formalizes "Generative Engines" (GEs) — systems like BingChat, Google
  SGE, Perplexity.ai that retrieve sources and generate a single cited,
  synthesized answer rather than a ranked list of links.
- Coins **Generative Engine Optimization (GEO)** — a black-box framework
  for optimizing content visibility inside GE-generated answers, distinct
  from traditional SEO. This wiki treats GEO as synonymous with what it
  otherwise calls AEO.
- Defines visibility/"impression" metrics for a citation inside a
  generated answer: raw word count, position-adjusted word count, and a
  7-facet "Subjective Impression" score (relevance, influence, uniqueness,
  position, count, click-likelihood, diversity) — necessary because
  "rank #1 of 10 blue links" no longer applies.
- Releases **GEO-bench**, a 10K-query benchmark across 9 source datasets
  and 25 domains, used to test 9 content-optimization tactics.
- Core finding: **traditional SEO tactics largely fail** in generative
  engines (Keyword Stuffing, Unique Words showed ~0% or negative
  improvement; Keyword Stuffing was 10% *worse* than baseline on live
  Perplexity.ai), while **Quotation Addition, Statistics Addition, and
  Cite Sources** boosted visibility up to +40% on the benchmark and
  +22–37% validated live on Perplexity.ai.
- Tactic effectiveness is **domain-specific** (e.g., Authoritative tone
  works for Debate/History; Statistics Addition for Law & Government/
  Opinion; Quotation Addition for People & Society/History) and
  **combining tactics beats any single one** (Fluency + Statistics was the
  best-performing pair).
- Notable equity finding: GEO disproportionately helps **lower-ranked**
  sites. A site ranked #5 in Google search results got a **+115%**
  visibility boost in the generated answer from adding citations, while
  the #1-ranked site's visibility *dropped 30%* under the same treatment
  — traditional ranking signals (backlinks, domain authority) matter much
  less once an LLM reads the raw content directly.

## What this updated in the wiki

- Created [[generative-engine-optimization]] (concept)
- Created [[geo-content-optimization-tactics]] (playbook)
