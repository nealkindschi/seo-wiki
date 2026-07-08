---
type: concept
tags: [seo, aeo]
updated: 2026-07-07
---

# AI Citation Landscape

Empirical patterns in what generative AI answer engines actually cite in
practice, as distinct from [[generative-engine-optimization]] (which
covers *tactics* for increasing citation-stage visibility). Based on
[[muckrack-generative-pulse-ai-reading-may-2026]], an analysis of 25M+
citation links across ChatGPT, Claude, and Gemini; [[sej-the-consensus-gap]]
(3.7M URL citations, ChatGPT/Perplexity/Google AI Overviews); and
[[brightedge-ai-search-same-brands-different-sources]] (ChatGPT,
Perplexity, Gemini, Google AI Mode, Google AI Overviews).

## Non-paid, earned media dominates

~99% of citations come from non-paid sources; paid/advertorial content is
just 0.3% of all citations. Journalism accounts for 27% of citations
overall; earned media broadly (journalism, academic/research, government/
NGO, encyclopedic, social, third-party corporate content) accounts for
~84%, with owned + paid content making up the remaining ~16%.

## Providers are three separate information environments

ChatGPT, Claude, and Gemini cite very differently, both in *how often*
and *how much*, and pull from largely non-overlapping sources:

- **ChatGPT**: cites in 96% of responses, ~5 citations each — a
  near-universal but concise citer.
- **Gemini**: cites in 82% of responses, ~8 citations each.
- **Claude**: cites in only 55% of responses (leans on training
  knowledge more), but averages **13** citations when it does go to the
  web — more than twice ChatGPT's depth.

Cross-provider overlap in top cited domains is minimal — Wikipedia is
the only domain that appears near the top for all three. Among
journalism outlets specifically, only Forbes appears in more than one
provider's top 5. Practical implication: optimizing for "generative
engines" as a monolith is misleading — tactics may need to be
provider-specific.

This is independently corroborated at much larger scale by
[[sej-the-consensus-gap]] (3.7M URL citations, ChatGPT/Perplexity/
Google AI Overviews): only **2.35-2.45%** of cited URLs for the same
prompt appear in all three engines, and **91%** appear in only one —
stable across four samples spanning a full year (Q3 2025–Q1 2026). Even
Wikipedia (16,073 citations) is universal in only 1.3% of cases; Reddit
(14,267 citations) in 0.1%; Reuters (1,202 citations) in 0.0%. That
source calls this **"the consensus gap"**: engines draw from largely
disjoint source pools rather than ranking a shared pool differently.

## Measure presence, portability, and concentration separately

Per [[sej-the-consensus-gap]], a single blended "AI visibility" score
hides the finding that matters — that engines barely share source
pools. Three separate metrics are more useful:

- **Presence** — % of tracked prompts where you appear in *any* engine
  (does visibility exist at all).
- **Portability** — % of your cited URLs that appear in *all* engines
  (does visibility survive across platforms, or is it one engine's
  idiosyncratic pick).
- **Concentration** — % of your citations coming from a single engine
  (which platform your visibility dashboard actually depends on).

Content type affects portability more than expected but stays low in
absolute terms: guides/tutorials portability 2.3% (highest) > blogs
1.8% > category pages 1.6% > product pages 1.2% > homepages 1.1%.
Explanatory, utility-driven content travels best; brand-centric and
transactional pages travel worst.

## Engines have distinct sourcing "personalities" (authority vs. UGC mix)

[[brightedge-ai-search-same-brands-different-sources]] classifies every
citation by source type (authority, commercial/editorial, UGC) across a
5-engine set (ChatGPT, Perplexity, Gemini, Google AI Mode, Google AI
Overviews) and finds sharply different authority-vs-UGC mixes:

- **Gemini** — "formal institutional recommender": 26% authority
  (gov/academic/institutional), only 0.2% UGC (130:1 ratio), highest
  .gov (13%) and .org (23%) share.
- **Perplexity** — "research librarian": 22% authority, 1.5% UGC,
  concentrates on institutional medical/government/encyclopedic
  sources (30% combined), highest .edu (3.2%) and international ccTLD
  (4.4%) share, and names brands earliest of any engine — 86% land by
  position 5.
- **ChatGPT** — "long-tail editorial engine": 18% authority, only 0.5%
  UGC, flattest source distribution of all five (top 10 domains = only
  18.5% of citations).
- **Google AI Mode** — "broad commercial aggregator": 14% authority, 7%
  UGC, widest unique domain catalog, most even distribution across
  source types.
- **Google AI Overviews** — "UGC-first engine": only 10% authority but
  ~17.5-18% UGC (35x ChatGPT's UGC share) — a single video platform
  alone accounts for 10.6% of its citations, a single forum for 2.9%.

Pairwise source overlap (top-100 lists, Jaccard similarity) ranges
16%-59% across engine pairs — wide and inconsistent. Notably, "Google
AI" is not one thing: AI Mode and AI Overviews (both search-embedded)
share 59% overlap with each other, but Gemini overlaps *more* with
ChatGPT (39%) than with either Google surface (27-34%).

Brand sentiment is overwhelmingly positive across all five engines
(78-96% positive, ≤2.1% negative) regardless of these sourcing
differences.

## Same source-type layers everywhere, different weighting

Despite the sourcing-personality differences above,
[[brightedge-ai-search-same-brands-different-sources]] finds all five
engines draw from the same three layers, just weighted differently:

1. **Authority** — government, academic, major industry institutions,
   trade associations, analyst firms, standards bodies.
2. **Commercial & Editorial** — review sites, comparison content, trade
   press, news media, finance data, retailer listings. The largest
   layer everywhere: **37-51%** of citations across all five engines.
3. **UGC** — video platforms, forums, community sites, social networks,
   creator coverage.

Practical implication: "authority" should be treated as
category-relative (which trade associations/analyst firms/vertical
experts actually get cited in *your* category), not a fixed domain
list like .gov/.edu.

## Wikipedia, Reddit, and YouTube diverge sharply by provider

- **Wikipedia** is a top-3 cited domain in 12/17 industries for ChatGPT,
  8/17 for Claude, but only 3/17 for Gemini. Investment in Wikipedia
  presence benefits ChatGPT and Claude visibility much more than Gemini.
- **Reddit** is Gemini's single most-cited domain (2.4% of all its
  citations) but essentially absent from ChatGPT (~0.003%) and Claude
  (0%).
- **YouTube**: Claude never cites it (0%); it's ~2% of citations for
  both ChatGPT and Gemini.

## The Axios anomaly

Journalism citations are spread across 20,000+ distinct outlets with no
single dominant publication — except Axios, which appears in ChatGPT's
top-3 cited domains across 13 of 17 industries, a level of cross-sector
breakthrough no other outlet or provider combination matches. By
contrast, Reuters and The New York Times don't appear in the top 3 for
any industry, for any provider, and Claude's top journalism outlet
(CNBC) only cracks the top 3 in a single industry. This is consistent
with Axios's short-form, cross-topic coverage model.

## Recency matters

Among journalism citations with a known publish date, 57% were published
within the past 12 months, accelerating from 50%/11 months measured in
Muck Rack's December 2025 report. Citation volume peaks sharply in the
first month after publication and decays quickly through month six,
though a long tail past three years still accounts for a meaningful
share.

## Query type and sector shape citation mix

"Industry Trend" queries cite journalism at 46% — more than twice the
rate of How-To or Comparative queries (~18-19%) — and drive nearly all
press-release citations (1.16% of Industry Trend responses vs. 0.09% for
How To). Journalism citation rate also varies by sector: highest in
Media/Entertainment (36%) and Finance/Insurance (32%), lowest in
Education and Industrial/Manufacturing (~19% each).

## Topic-specific source trust

Per [[growth-memo-topics-matter-for-third-party-authority]], trusted-source
mix varies sharply not just by *engine* (see "personalities" above) but by
*topic within the same engine*: competitor domains account for 33.5% of
citations on invoicing queries but only 7% on business-startup queries.
This sharpens the "authority is category-relative, not a fixed domain
list" finding above — it isn't just industry-relative, it can shift
topic-by-topic within one category, so a source map has to be built per
topic, not assumed to carry over from an adjacent one.

## Local queries lean on Google Maps, not articles

For "best of" local queries (best hotels, restaurants, services),
ChatGPT systematically cites Google Maps search results — 188 citations
per 1,000 such queries, averaging ~7 map pins per response — rather than
reviews or editorial content. Claude cited Google Maps only once in the
entire study.

## Citations change what the model actually says

Not just a visibility/attribution mechanism: enabling web citations can
change the substantive correctness of an answer, not just add sources to
an otherwise-fixed response. Example from the source: asked for the
worst MLB team ever, a model without citations answered with an outdated
fact (1962 Mets), while with citations enabled it correctly cited a more
recent record-holder (2024 White Sox). This reinforces
[[google-ai-optimization-guide]]'s framing of generative answers as
grounded in retrieval (RAG), not a static trained "understanding."

## Conflicting Evidence — resolved

- **Claim**: The three major AI answer surfaces operate as largely
  independent, non-overlapping information environments (per "Providers
  are three separate information environments" above).
  - Supported by: this page's own domain-level citation-overlap findings
    from [[muckrack-generative-pulse-ai-reading-may-2026]] (covering
    ChatGPT/Claude/Gemini), independently corroborated by
    [[sej-the-consensus-gap]] (covering ChatGPT/Perplexity/Google AI
    Overviews, 3.7M citations, four samples over a full year).
  - Apparently contradicted by: [[ahrefs-ai-brand-visibility-correlations]]
    (covering ChatGPT/AI Mode/AI Overviews), which found high
    correlation (0.75–0.82) in *which brands* get mentioned across all
    three.
  - **Resolved (2026-07-07)** by
    [[brightedge-ai-search-same-brands-different-sources]], which tests
    both halves directly on the same 5-engine dataset: pairwise
    *source*-overlap (16-59%) is measurably wider/more inconsistent than
    pairwise *brand*-overlap (36-55%) across every engine pair studied.
    Different engines really do cite different specific sources
    (confirming the Muck Rack/SEJ side) while still converging on
    largely the same brands (confirming the Ahrefs side) — not a
    contradiction, but two true findings at different units of
    analysis, now empirically linked rather than just plausibly
    inferred. See [[ai-visibility-correlation-factors]] for the full
    writeup, including a residual methodology caveat (BrightEdge's
    aggregate top-100-list overlap numbers read higher than SEJ's
    per-prompt exact-URL overlap — a granularity difference, not a
    contradiction).

## See also

- [[growth-memo-topics-matter-for-third-party-authority]] — the
  topic-vs-competitor-domain-share data point cited above, plus tiered
  authority-accumulation and named-author findings covered in
  [[geo-content-optimization-tactics]].
- [[sej-the-consensus-gap]] — the independent, large-scale confirmation
  of citation-level cross-engine fragmentation cited throughout this
  page, plus the presence/portability/concentration measurement
  framework.
- [[brightedge-ai-search-same-brands-different-sources]] — the 5-engine
  source-vs-brand overlap comparison that resolves the Conflicting
  Evidence above, plus the engine personality profiles and three-layer
  source framework.
- [[generative-engine-optimization]] — tactics for increasing citation
  visibility once retrieved.
- [[ai-visibility-correlation-factors]] — which brand/SEO metrics
  correlate with AI-mention visibility, and the full reconciliation of
  the Conflicting Evidence above.
- [[geo-content-optimization-tactics]] — actionable playbook, now
  including provider-specific guidance drawn from this landscape data.
