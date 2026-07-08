---
type: concept
tags: [seo, aeo]
updated: 2026-07-08
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

## Citations vs. brand mentions

Per [[similarweb-how-to-be-the-brand-ai-recommends-2026]] — a
conceptual distinction not previously made explicit in this wiki. A
**mention** is the AI saying a brand's name; a **citation** is the AI
pointing to a brand's content as a retrieved source (the brand's
website "gets the footnote"). This maps onto two different underlying
data sources AI draws from:

| | Training data | Live retrieval |
|---|---|---|
| What it is | Frozen snapshot baked in at training time | Real-time web retrieval |
| Update cycle | Months to years | Real time |
| Brand discovery | Only brands present before the training cutoff | Any brand with a crawlable presence |
| Confidence | High — deep, consistent signal | Lower — thinner profile |

**Citations only come from retrieval.** **Mentions** can come from
*either* training data (the model learned to associate a brand with a
topic over time) *or* live retrieval. This reframes
[[airops-fan-out-effect-2026]]'s "memory citations" finding (6,371
citations with no corresponding search result) as, in this framing, a
training-data-sourced mention rather than a true retrieval citation.

**Practical stakes**: citations drive traffic (per
[[aio-ctr-impact]]'s citation-premium data); mentions build presence
even when the user never clicks — relevant given most AI interactions
end without a click (see [[ai-traffic-scale-vs-hype]]). This "mentions
build presence" claim now has direct measured backing: per
[[similarweb-downstream-impact-of-ai-visibility-2026]], brands
recommended (mentioned) by ChatGPT are 2.5x more likely to receive a
site visit within 7 days than a non-recommended competitor — even
though 55.9% of that resulting traffic arrives via a subsequent branded
search rather than a direct AI referral link, meaning a mention's
downstream effect is largely invisible to referral-based traffic
attribution. See [[aio-ctr-impact]] for the full writeup.

**Different signals drive each**:
- **Recommendation/mention signals**: frequent co-occurrence with the
  brand's category, high branded search volume (humans searching for a
  brand teaches AI it matters), presence in core knowledge sources
  (Wikipedia, Wikidata, major publications), consistent positive
  co-mentions with the category across the web.
- **Citation signals**: unique data points not found elsewhere
  (information gain, not repetition), content freshness (recency is a
  major retrieval weight in RAG systems), clear extractable structure
  (headers, bullets, schema), and co-citation (multiple independent
  sources pointing to the same brand as the answer).

## Retrieval rank as the primary citation gatekeeper

Per [[airops-fan-out-effect-2026]] (16,851 queries, 353,799 pages
analyzed, ChatGPT) — a mechanism not previously covered anywhere in this
wiki: **where a page lands in ChatGPT's internal retrieval results
dominates whether it gets cited at all**, ahead of any content-quality
signal. Position 1 in retrieval = 58.4% citation rate vs. 14.2% at
position 10 — a 4x gap. Even pages with strong heading-query relevance
(≥0.8 similarity) drop from 79.6% citation at rank 1 to 21.5% at rank
11+. This reframes "citation-worthy content" as a two-stage problem:
first get retrieved/ranked highly by the underlying search step, *then*
compete on content signals — content quality cannot compensate for a
poor retrieval rank.

Citation distribution is **bimodal**, not a smooth curve: 58% of pages
in the dataset were never cited, 25% always cited, only 17%
intermittently cited — and on-page signals (word count, headings,
readability) show almost no difference between the always-cited and
never-cited groups, reinforcing that retrieval rank, not content
quality, is the real separator between the two populations.

Within retrieved pages, **heading-query match is the strongest content
signal measured**: 41.0% citation at 0.90+ heading-similarity vs.
29-30.2% for weak matches (<0.50). Counterintuitively, **comprehensive
topic coverage underperforms focused coverage** when relevance is held
constant — pages covering 26-50% of a query's fan-out subtopics cited
more often (38.2%) than pages covering 100% (34.0%), and matching 3-4
distinct subheadings reduced citation 6pp versus matching only 0-1.

**"Memory citations"** — 6,371 citations in the dataset had no
corresponding search result at all, meaning ChatGPT cited from training
data directly rather than live retrieval. These memory-cited pages had
content profiles statistically identical to search-cited pages,
suggesting no separate quality bar for training-data citation.

## Citation rate by source type and semantic relevance (ChatGPT)

Per [[ahrefs-why-chatgpt-cites-pages-2026]] (1.4M ChatGPT prompts,
Feb 2025, cosine-similarity semantic analysis) — a more granular
breakdown of ChatGPT's citation behavior than previously in this wiki,
segmented by reference type rather than treated as one aggregate pool:

- **Citation rate varies enormously by source type**: Search 88.46%,
  News 12.01%, Reddit 1.93%, YouTube 0.51%, Academia 0.40%. About 88%
  of all ChatGPT citations come from the search-index reference type
  specifically — ranking in the search index is close to a
  prerequisite for citation.
- **Reddit is retrieved heavily but almost never cited**: 67.8% of all
  non-cited URLs are Reddit — ChatGPT uses it extensively as
  background context/consensus-gauging but rarely attributes to it
  directly.
- **Semantic relevance (cosine similarity) is the strongest measured
  differentiator within a retrieval set**: cited pages score 0.602 on
  prompt-title similarity vs. 0.484 for non-cited pages, and score
  even higher (0.656) against ChatGPT's internal fanout sub-queries —
  direct evidence supporting
  [[peec-ai-chatgpt-query-fanouts-2026]]'s claim that content should
  target the engine's hidden fanout sub-questions, not just the
  surface-level prompt.
- **Natural-language URL slugs correlate with higher citation**:
  89.78% vs. 81.11% for non-natural-language URLs.

## Query fanout mechanics

Per [[peec-ai-chatgpt-query-fanouts-2026]] (5M query fanouts across
ChatGPT/Perplexity/Grok, April 2026) — explains the mechanism behind
the "query fan-out" term used elsewhere in this wiki
([[generative-engine-optimization]]), distinct from
[[airops-fan-out-effect-2026]]'s finding about *content* subtopic
coverage: this is about what the *engine itself* injects into hidden
sub-queries before retrieval happens.

- **Fanout volume varies sharply by engine**: Perplexity 1.4
  subqueries/query (minimal expansion), ChatGPT 2.1/query (adds
  brands, comparisons, review keywords), Grok 6.8/query — over 3x
  ChatGPT's rate, treating the prompt as a research brief and
  progressively narrowing by year/brand/trusted domain.
- **ChatGPT's most-injected words**: "best" (into 24.3% of
  advice-style questions, even when the user never used the word),
  "top," "comparison," "reviews" (3rd most common — pulls in
  unrequested review-platform content from Glassdoor/G2/Sitejabber
  and similar), "tools," "software," "features."
- **Ranking mechanism**: ChatGPT combines fanout subquery results via
  Reciprocal Rank Fusion (RRF) — content surfacing across multiple
  fanout subqueries outranks content matching only one, adding a
  concrete mechanism beneath the general "get retrieved across
  multiple angles" intuition.
- **Freshness signal**: a current-year token is injected into 5.44%
  of prompts.
- **Grok explicitly targets trusted domains** via site-operator
  searches in 18.3% of chats; Reddit appears in 10.5% of chats (~90%
  deliberately site-directed, not organic); Wirecutter and Consumer
  Reports are injected by Grok at a 100% rate regardless of whether
  the user asked for them.

**Practical implication**: listicle ("best of"/comparison/review)
framing structurally matches the dominant fanout injection pattern —
offered as a mechanism explaining why listicle content dominates AI
answer results (see also the "Listicle rank effect" below, a related
but distinct finding about rank *within* listicles once included).

## Self-promotional listicles still get cited

Per [[peec-ai-self-promotional-listicles-2026]] (13,000 listicles,
232,000 citations, 12 weeks Dec 2025-Feb 2026, software sector, 6
platforms) — a caution alongside the listicle-focused findings above:
current AI retrieval filtering does not reliably screen out
self-promotional listicles (a company's own domain listing its own
product).

- Roughly **1 in 10 citations (~11%)** in the studied sector originate
  from self-promotional listicles, with **no algorithmic correction**
  observed over the 12-week window — rates held stable rather than
  declining.
- **Sharp platform divergence**: ChatGPT ~3.6-4% (lowest, ~3x better
  than the worst offenders) vs. Google AI Mode ~10.3% and Perplexity
  ~10.4%. ChatGPT's lower rate is attributed to more diverse sourcing
  overall, heavier reliance on educational/training sites, and much
  lower reliance on one specific self-promoting domain (Zapier, ~1% of
  its citations vs. ~8% for other platforms).
- Framed as a current-state gap in retrieval filtering, not a stable
  loophole to exploit — see [[e-e-a-t-and-page-quality]] for why
  self-promotional/undisclosed-conflict-of-interest content remains
  advised against regardless (reputational risk, and filtering could
  tighten).

## Citation-without-recommendation in self-promotional listicles

Per [[sej-why-calling-yourself-the-best-2026]] (323 tracked citation
instances, 100 B2B queries) — sharpens both the "Citations vs. brand
mentions" distinction above and the self-promotional-listicle finding
below: citation and recommendation are decoupling specifically for
self-promotional "best of" listicles in Google AI Overviews.

- A brand's own self-ranked listicle can still get **cited** as a
  source while the AI's actual **recommendation** goes to a competitor
  named within that same listicle — a 69% failure rate (224/323
  tracked instances), present in ~74% of the B2B queries analyzed.
  Effectively, the self-promoter's own content ends up promoting
  rivals.
- **Authority moderates the effect**: already-established, high-DR
  brands are sometimes exempted from this pattern; lesser-known
  companies bear the penalty disproportionately, even when ranking
  organically.
- **Reported countermeasures**: organic ranking demotion for domains
  with a pattern of excessive self-promotional content, new AI
  Overview disclaimer language around "self-proclaimed expert"
  sources, and a citation-source shift toward third-party review
  platforms (Reddit, Forbes Advisor, YouTube) for "best of" queries —
  with affected sites' organic visibility declining from January 2026,
  accelerating through May 2026.
- **Citation alone has limited direct value**: cites Pew Research's
  ~1% click-through rate on AI-summary citations — reinforcing that
  *recommendation*, not citation, is the metric that actually drives
  business outcomes from AI search.

This coexists with, rather than contradicts,
[[peec-ai-self-promotional-listicles-2026]]'s finding of a stable
~11% self-promotional citation *rate* with no correction observed in
Dec 2025-Feb 2026: that source measured whether self-promotional
listicles keep getting cited at all; this source measures a narrower,
newer failure mode layered on top — whether citation converts to an
actual recommendation, plus organic-visibility-level countermeasures a
citation-rate metric wouldn't capture.

## Listicle rank effect

Per [[peec-ai-listicle-rank-effect-2026]] (~200,000 AI responses, 5.7M+
data points, 8 engines, Sept 2025-Mar 2026) — a third-party-listicle-
specific sharpening of [[airops-fan-out-effect-2026]]'s retrieval-rank
finding above: rank *position* within a frequently-cited listicle
measurably moves visibility, answer placement, and mention count, not
just whether a brand is included at all.

- Rank #1 visibility lift varies by market maturity: +16.5pp (B2B
  SaaS), +13.4pp (Emerging MarTech, steepest dropoff at lower ranks),
  and a large-but-less-rank-ordered effect in US Finance (smaller
  listicle pool, trusted-source dynamic).
- Rank #1 also shifts answer position earlier (0.82-1.80 positions,
  consistent direction across all three markets) and mention count
  (+0.43 to +0.67, though not statistically significant in US
  Finance).
- Diminishing returns: a few placements in frequently-retrieved
  listicles outperform many placements in rarely-retrieved ones.
- Tight-retrieval engines (ChatGPT, GPT-5 Search, Microsoft Copilot)
  show larger per-listicle lifts than broad-retrieval engines (Google
  AI Overview, AI Mode) — consistent with those engines' narrower
  source pools generally (see sourcing-personality data above).

## AI Overview citation composition and the citation-without-ranking gap

Per [[ahrefs-b2b-seo-statistics-2025]] — a small set of B2B-context
stats that add useful texture to the citation-composition findings
above:

- **76% of AI Overview citations pull from Google's own top-10 organic
  results** — reinforcing [[airops-fan-out-effect-2026]]'s
  retrieval-rank-as-gatekeeper finding specifically within Google's
  own AIO surface, alongside the ChatGPT-specific "~88% of citations
  come from the search-index reference type" finding in
  [[ahrefs-why-chatgpt-cites-pages-2026]] above — a consistent pattern
  across both Google's and OpenAI's systems that ranking well in
  classic search remains close to a prerequisite for AI citation.
- **28.9% of AI Overview citations concentrate on just the top 50
  brands** in a category, and **26% of brands get zero AI Overview
  mentions at all** — a visibility-concentration pattern consistent
  with this page's "presence/portability/concentration" framing above.
- **Citation doesn't require organic visibility**: 28% of ChatGPT's
  most-cited pages have **zero Google organic visibility** — a genuine
  nuance on the "ranking is close to a prerequisite" finding above.
  Plausible reconciliation (not directly tested by either source):
  this likely reflects the non-search reference types
  ([[ahrefs-why-chatgpt-cites-pages-2026]]'s News/Reddit/Academia
  categories) or memory-citation behavior
  (see the "Retrieval rank as the primary citation gatekeeper" section
  above), which don't require the cited page to rank organically at
  all. Not logged as a formal conflict since it's a minority-share
  nuance on an already-probabilistic claim, not a direct contradiction.

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

## Conflicting Evidence

- **Claim**: optimal content age for AI citation.
  - Supported by: [[airops-fan-out-effect-2026]] (via
    [[geo-content-optimization-tactics]]'s "Freshness by vertical"
    section) — optimal content age is 30-89 days, with citation
    declining for content over 2 years old.
  - Contradicted by: [[ahrefs-why-chatgpt-cites-pages-2026]], which
    finds that within search-result retrieval sets specifically,
    older/established content (median ~500 days, some pages 2,700+
    days old) is cited *more* than fresher content — the opposite
    direction. The same source's news-vertical data (fresher articles,
    ~200 vs. ~300 days, cited more) is at least directionally
    consistent with AirOps's freshness preference, but only within
    that one source type.
- **Current best guess**: likely a reference-type/segmentation
  difference rather than a true contradiction — AirOps's dataset isn't
  broken out by source type the way Ahrefs's is, so its "30-89 days
  optimal" finding may be an average across a source mix (including
  news, where freshness does help) that masks a different pattern in
  pure search-result citations (where relevance/authority of an
  established page can outweigh recency). Flagged as **unresolved**
  since neither source directly tests the other's segmentation; until
  resolved, treat freshness guidance as vertical/source-type-dependent
  rather than a single universal age curve.

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
- [[airops-fan-out-effect-2026]] — the retrieval-rank-as-gatekeeper
  mechanism above, plus the authority-correlation Conflicting Evidence
  writeup in [[ai-visibility-correlation-factors]].
- [[similarweb-how-to-be-the-brand-ai-recommends-2026]] — the
  citations-vs-mentions distinction and two-data-source framing above,
  plus corroborating data in [[geo-content-optimization-tactics]] and
  [[aio-ctr-impact]].
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
- [[peec-ai-listicle-rank-effect-2026]] — the listicle rank-effect
  study cited above, plus market-maturity and engine-retrieval-strategy
  breakdowns.
- [[peec-ai-chatgpt-query-fanouts-2026]] — the query-fanout injection
  mechanics above (engine-side hidden subquery behavior), distinct
  from and complementary to [[airops-fan-out-effect-2026]]'s
  content-coverage finding.
- [[peec-ai-self-promotional-listicles-2026]] — the self-promotional-
  listicle citation-rate data above, including the platform divergence
  and educational/training-site sourcing explanation for ChatGPT's
  lower rate.
- [[ahrefs-why-chatgpt-cites-pages-2026]] — the source-type citation-
  rate breakdown, semantic-relevance data, and unresolved content-age
  Conflicting Evidence above.
- [[ahrefs-b2b-seo-statistics-2025]] — the AI Overview citation-
  composition and citation-without-organic-visibility data above.
- [[sej-why-calling-yourself-the-best-2026]] — the citation-vs-
  recommendation decoupling data and Google countermeasure reporting
  above.
