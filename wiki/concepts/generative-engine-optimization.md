---
type: concept
tags: [aeo]
updated: 2026-07-07
---

# Generative Engine Optimization (GEO / AEO)

**Generative Engines (GEs)** are systems — BingChat, Google's SGE,
Perplexity.ai, and by extension ChatGPT/Claude-style answer engines —
that satisfy a query by retrieving sources and generating a single
synthesized, cited answer, rather than returning a ranked list of links.
**Generative Engine Optimization (GEO)** is the practice of optimizing
content to increase its visibility (how much it's used and cited) inside
those generated answers.

This wiki treats **GEO and AEO as the same underlying idea** — GEO is the
term coined by the founding academic paper on the topic
([[geo-generative-engine-optimization-aggarwal-2023|source]]); AEO
("Answer Engine Optimization") is the term that stuck in industry usage.
Pages in this wiki may use either term depending on the source being
cited.

## Why traditional SEO doesn't transfer

Traditional search engines rank by keyword matching plus authority
signals (backlinks, domain age). Generative engines instead have an LLM
read the actual retrieved content and decide what to cite and how much
to quote — so tactics built for keyword-matching rank algorithms largely
don't work:

- **Keyword Stuffing** and **Unique Words** (classic on-page SEO moves)
  showed ~0% or even negative improvement in citation visibility, and
  Keyword Stuffing measured **10% worse than baseline** when validated
  live on Perplexity.ai.
- What *does* work is qualitatively different: making content more
  citable, quotable, and evidence-backed — see
  [[geo-content-optimization-tactics]] for the ranked tactics.

## Visibility is measured differently than SEO ranking

Because a generated answer embeds multiple citations at different
lengths and positions in one block (rather than a linear list),
"visibility" needs its own metrics:

- **Word count** of the sentences attributed to a source.
- **Position-adjusted word count** — same, but weighted down for
  citations that appear later in the answer (earlier = more likely to be
  read).
- **Subjective Impression** — a 7-facet LLM-judged score: relevance,
  influence (how much the answer actually relies on this citation),
  uniqueness of the material, perceived prominence of position, perceived
  amount of content used, likelihood the user clicks through, and
  diversity of material presented.

## GEO disproportionately helps lower-ranked content

A striking finding: content that ranks poorly in traditional search can
gain the most from GEO. In one experiment, a site ranked **#5** in Google
search results gained **+115%** visibility in the generated answer after
adding citations, while the **#1**-ranked site's visibility for the same
treatment *dropped 30%*. Because the generative engine reads content
directly rather than relying on backlink/domain-authority signals, small
or under-ranked creators have a more level playing field inside AI
answers than they do in classic SERPs.

## Effectiveness is domain-specific

No single tactic wins everywhere — see
[[geo-content-optimization-tactics]] for which tactics work best in which
domains, and why combining tactics outperforms using any one alone.

## Open questions

- This is based on a single 2023/2024 academic study using GPT-3.5-based
  generative engines and Perplexity.ai. Whether these findings hold for
  newer generative engines (e.g. Google AI Overviews, ChatGPT search,
  Claude) is untested as of this wiki's current sources.
