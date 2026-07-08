---
type: playbook
tags: [seo, aeo]
updated: 2026-07-07
---

# GEO Content Optimization Tactics

**Why/when to use this:** Apply these when writing or revising content
you want cited/quoted by generative engines (AI Overviews, Perplexity,
ChatGPT search, etc.), as opposed to classic keyword-ranking SEO. See
[[generative-engine-optimization]] for the underlying concept. For
classic organic-SERP ranking tactics specifically, see
[[classic-seo-ranking-factors]] instead — the two overlap in places but
are grounded in different correlation studies.

Ranked by measured visibility improvement
([[geo-generative-engine-optimization-aggarwal-2023|source]]), from best
to worst, tested against a no-optimization baseline:

## Tier 1 — High performing (do these)

1. **Quotation Addition** — add credible, quotable quotes from relevant
   sources. Best overall performer: up to +40% on the benchmark, +22%
   validated live on Perplexity.ai.
2. **Statistics Addition** — include quantitative statistics instead of
   qualitative/vague claims wherever possible. +37% validated live on
   Perplexity.ai (Subjective Impression metric).
3. **Cite Sources** — add citations to credible sources for factual
   claims. Especially effective for lower-ranked content (see
   [[generative-engine-optimization]]'s equity finding — up to +115% for
   a rank-5 site).
4. **Fluency Optimization** — improve the fluency/flow of the writing
   itself, no new content required. +15–30%.
5. **Easy-to-Understand** — simplify language/reduce jargon. +15–30%.

**Best combination tested:** Fluency Optimization + Statistics Addition
together outperformed any single tactic by 5.5%+. If you can only pick
one pairing, use this one.

## Publish citation-ready primary research/benchmarks

Per [[growth-memo-why-most-original-data-never-gets-cited]] — this
sharpens Tier 1's "Statistics Addition"/"Cite Sources" tactics: having
original data isn't enough, and most organizations' proprietary data
still fails to get cited because of *how* it's packaged, not because
the numbers themselves are weak. In one 301-page citation dataset,
primary research was rare (2.7% of pages) but earned 3.3x the citation
density of other content — and 75 of 90 primary-research citations came
specifically from **benchmarks** (named items compared head-to-head on
a measurable axis), not data dumps or narrative-buried stats.

- **Frame it as a comparison, not a data drop.** Structure the page
  around "which option is best on X" with a table of named
  competitors/options — this only works in topics that have a natural
  comparison axis (speed, cost, latency, performance); topics without
  one (e.g. category education content) don't see this effect.
- **Lead with the result.** Put the comparison finding in the first 30%
  of the content, not buried after setup/narrative. Per
  [[growth-memo-why-proprietary-data-is-your-most-defensible-asset]],
  this isn't just directional advice — **44.2% of all citations come
  from the first 30% of a page** in that source's dataset, one of the
  more concentrated placement effects measured in this wiki.
  Independently corroborated: [[similarweb-how-to-be-the-brand-ai-recommends-2026]]
  states the same figure ("44% of AI citations come from the first 30%
  of a page") from a separate analysis — two independent sources
  converging on the same number.
- **Owning the data doesn't guarantee the citation.** Per
  [[growth-memo-why-proprietary-data-is-your-most-defensible-asset]], an
  aggregator can repackage someone else's original research into a
  cleaner, more extractable format and capture the citation instead of
  the data's originator — publishing proprietary data is necessary but
  not sufficient; the structural packaging tactics on this list are what
  actually wins the citation.
- **More unique figures correlates with higher originality/information
  gain.** Per the same source (On-Page.ai data), pages with 15+ unique
  figures averaged an information-gain score of 62.1 vs. 40.2 for pages
  with minimal original data — "most pages are middling on originality,"
  so genuine data differentiation (not just more content) is what
  separates the two tiers.
- **Box the methodology visibly**: sample, timeframe, measurement
  approach, and confidence level, as a distinct callout — not folded
  into prose.
- **Use real, labeled first-party data**, not synthetic estimates —
  and say so explicitly.
- **Link raw data/sources** so claims are independently verifiable.
- **Show credibility signals**: dated corrections and acknowledged
  limitations outperform a page that claims no caveats.
- **Structure headings so a question maps directly to an answer** —
  AI-retrievable structure, not just human-readable prose.
- **Keep the URL stable.** In the source dataset, 64 of 365 cited URLs
  were dead or redirected, taking 203 citations offline — don't
  reorganize or relaunch a benchmark page's URL once it's earning
  citations.
- **Don't gate it.** Proprietary data behind a lead-gen form can't be
  crawled/cited — if citation is the goal, publish the benchmark
  itself openly, even if a deeper report stays gated.

## Focus over comprehensiveness (fan-out breadth finding)

Per [[airops-fan-out-effect-2026]] — nuances the Tier 1 tactics above:
being retrieved and relevant is necessary but writing an exhaustively
comprehensive page can actively *hurt* citation odds relative to a
focused one:

- **Don't try to cover every fan-out subtopic.** Controlling for query
  relevance, pages covering 26-50% of a query's fan-out subtopics were
  cited more often (38.2%) than pages covering 100% (34.0%). Matching
  3-4 distinct subheadings reduced citation 6pp versus matching only
  0-1 — write a focused, high-relevance answer rather than a
  comprehensive guide.
- **Heading-query match matters more than depth.** Pages with headings
  closely matching the query's language cited 41.0% of the time (0.90+
  similarity) vs. 29-30.2% for weak matches — write headings that
  mirror likely query phrasing, not generic section titles.
- **Retrieval rank is the real gatekeeper — content quality can't
  compensate for it.** Position 1 in ChatGPT's retrieval results = 58.4%
  citation rate vs. 14.2% at position 10, a gap that overwhelms every
  content-level signal measured. This means classic retrieval-
  eligibility work (technical crawlability, ranking well enough to be a
  retrieval candidate at all — see the Technical crawlability checklist
  below) is a harder prerequisite for AI citation than previously
  documented in this wiki, not just for classic SERP ranking.

## Structural findings (word count, headings, schema, readability)

Per [[airops-fan-out-effect-2026]]:

- **Word count sweet spot: 500-2,000 words.** Pages over 5,000 words
  underperformed shorter content (28.6% vs. 30.5% citation) — don't
  assume longer/more thorough always wins.
- **4-10 H2-H4 headings optimal for articles** (33.2% citation); product
  pages performed best with **zero** headings (43.2%) — structure
  guidance is page-type-specific, not universal.
- **Add JSON-LD schema markup**: +6.5pp citation advantage overall.
  Strongest types: MedicalWebPage (47%), BreadcrumbList (46.2%),
  FAQPage (45.6%).
- **Write at a college reading level** (Flesch-Kincaid 16-17): 35.9%
  citation, outperforming both simpler and more academic writing.

## Freshness by vertical

Per [[airops-fan-out-effect-2026]] — extends the existing "keep content
fresh" guidance with a specific age curve and vertical-level variance:

- **Optimal content age is 30-89 days** (32.8% citation); content over 2
  years old declines (-5pp); content under 30 days old also underperforms
  slightly (25.3%), likely an indexing-delay effect rather than a
  genuine freshness penalty.
- Freshness only meaningfully helps when relevance is already strong
  (+4.2pp advantage) — among weak query-match pages, age effects are
  negligible, so don't expect a refresh alone to fix a fundamentally
  off-topic page.
- **Vertical-specific gaps**: Finance shows a 15pp gap between fresh and
  5+-year-old content, Travel shows the largest gap in the dataset
  (19pp); e-commerce content freshness barely matters — prioritize
  refresh cycles by vertical, not a blanket schedule.

## Authority-building caveat (unresolved conflict)

Per [[airops-fan-out-effect-2026]], domain authority/backlinks showed no
positive (slightly inverse) correlation with which *specific page* gets
cited, once retrieval rank and relevance are accounted for — this is in
tension with the brand-level authority correlations in
[[ai-visibility-correlation-factors]] and
[[growth-memo-topics-matter-for-third-party-authority]] (see that page's
Conflicting Evidence section, unresolved). Practical takeaway until
resolved: don't rely on authority-building alone to win a specific page's
citation — prioritize retrieval rank and query-relevance work first;
treat brand-level authority-building as a separate, longer-horizon
strategy rather than a lever for any one page's citation odds.

## Tier 2 — Modest performers

6. **Authoritative tone** — rewrite to sound more persuasive/authoritative.
   Small or no significant improvement on average — generative engines
   are largely robust to tone alone. Works better in specific domains
   (see table below) than as a general-purpose tactic.
7. **Technical Terms** — add domain-specific technical vocabulary.
   Modest, inconsistent gains.

## Tier 3 — Don't bother (traditional SEO tactics that don't transfer)

8. **Unique Words** — adding rare/unique vocabulary. ~0% improvement.
9. **Keyword Stuffing** — the classic SEO tactic. **~0% or negative** on
   the benchmark, and measured **10% worse than baseline** when validated
   live on Perplexity.ai. Do not use this for AEO/GEO purposes.

## Also don't bother (per Google's official guidance)

Per [[google-ai-optimization-guide]], Google explicitly says these do
**not** help visibility in AI Overviews/AI Mode — don't spend effort on:

- Creating `llms.txt` files or other special AI-only markup/text files —
  Google Search doesn't use them.
- "Chunking" content into unnaturally small pieces for AI to parse.
- Obsessing over structured data specifically for AI purposes (still fine
  to use for general SEO, just not an AI-visibility requirement).
- Pursuing inauthentic mentions or backlinks.
- Rewriting content in a way that's specifically "for AI" rather than for
  people — write for people first (see
  [[generative-engine-optimization]]'s Conflicting Evidence section on
  how this squares with the tactics above).

## Provider-specific tactics

Per [[ai-citation-landscape]], ChatGPT/Claude/Gemini cite from largely
non-overlapping sources — treat them as separate targets, not one
generic "generative engine":

- **Targeting ChatGPT or Claude?** Invest in a solid **Wikipedia**
  presence — it's a top-3 cited domain in 12/17 industries for ChatGPT
  and 8/17 for Claude. Skip this if Gemini is your main target (top-3 in
  only 3/17 industries for Gemini).
- **Targeting Gemini?** Reddit presence matters — it's Gemini's single
  most-cited domain (2.4% of citations) and essentially absent for the
  other two providers. Quora shows up prominently for Gemini too.
- **Targeting Claude specifically?** It cites far less often (55% of
  responses) but much more deeply (13 citations) when it does, and
  favors academic/reference sources like PubMed Central. It never cites
  YouTube — don't rely on video content to reach Claude.
- **Local/"best of" queries (hotels, restaurants, services)**: ChatGPT
  leans heavily on **Google Maps** results, not articles or reviews
  (188 citations per 1,000 such queries) — a current, accurate Google
  Business Profile matters more than written content here. Claude
  essentially doesn't do this.
- **Keep content fresh**: 57% of journalism citations are from the past
  12 months — publishing once and never updating loses ground to
  freshly-dated coverage over time.
- **Consider short-form, cross-topic coverage**: Axios is the one
  outlet that breaks through across most industries in ChatGPT's
  citations, plausibly due to its concise, high-frequency format —
  worth testing as a content-format hypothesis, not just a content-style
  one.

## Measure presence, portability, and concentration separately

Per [[sej-the-consensus-gap]] — don't rely on a single blended "AI
visibility" score, since engines pull from largely disjoint source
pools (only 2.35-2.45% of cited URLs appear across ChatGPT, Perplexity,
and Google AI Overviews for the same prompt; 91% appear in only one):

- Track **presence** (do you appear in any engine at all),
  **portability** (do the same cited URLs survive across engines), and
  **concentration** (what share of your citations comes from one
  engine) as three separate numbers, not one composite score.
- Don't assume ranking well in one engine predicts ranking in another —
  treat each engine as a genuinely separate optimization target (this
  reinforces the [[ai-citation-landscape]] provider-specific guidance
  above, now with direct URL-level overlap data rather than just
  domain-mix differences).
- **Prioritize explanatory content** (guides/tutorials) over
  brand-centric or transactional pages if cross-engine portability is
  your goal — guides/tutorials showed the highest (still low, 2.3%)
  portability, vs. 1.1% for homepages. Ask "does this page directly
  answer the query well" (utility) rather than "does this page
  represent our brand well" (brand centrality) — the source's framing
  is that engines favor the former.
- Pick a priority engine deliberately rather than chasing generic
  cross-engine visibility — given how low universal portability is
  (even Wikipedia is only 1.3% universal), spreading effort thin across
  all engines may be less effective than committing to the 1-2 engines
  that matter most for your actual audience/business.

## The three-layer source strategy (works across all engines at once)

Per [[brightedge-ai-search-same-brands-different-sources]] — despite the
low source-level portability above, *brand*-level recommendations
converge much more across engines (36-55% brand overlap vs. 16-59%
source overlap). This means one unified strategy, weighted per engine,
can beat five separate playbooks:

- Build presence across all three layers every engine draws from, just
  weighted differently per engine:
  1. **Authority** — trade associations, analyst firms, standards
     bodies, vertical-specific experts. Treat "authority" as
     **category-relative**, not a fixed .gov/.edu checklist — identify
     which authoritative sources actually dominate citations in *your*
     specific category.
  2. **Commercial & Editorial** — PR, trade press, review-site
     visibility, comparison content. This is the single widest lever:
     37-51% of citations across *every* engine studied, the largest
     layer everywhere.
  3. **UGC** — video, forums, community/creator coverage. Low overall
     share for most engines, but **non-negotiable specifically for
     Google AI Overviews** (~18% of its citations, with a single video
     platform alone at 10.6%) — understand which specific videos/forum
     threads it cites and earn authority within those conversations,
     rather than producing generic short-form video.
- Weight engine investment by where your actual buyers are: B2B/SaaS
  audiences skewing ChatGPT/Perplexity → emphasize authority +
  commercial/editorial, UGC supplemental. Consumer audiences skewing
  Google AI Overviews → emphasize UGC + commercial/editorial, authority
  reinforcing.
- Track Google's own surfaces separately rather than as one "Google AI"
  bucket — AI Mode and AI Overviews share 59% source overlap with each
  other (a win on one plausibly transfers), but Gemini overlaps *more*
  with ChatGPT (39%) than with either Google surface (27-34%) — Gemini
  needs its own strategy, not a "just optimize for Google" shortcut.

## Five-component intent framework and AI-reuse formatting

Per [[similarweb-how-to-win-the-race-for-gen-ai-search-2026]] — a more
granular way to align content with what an AI retriever selects than
matching a query's keywords alone. Break each target prompt into five
intent components and make sure content satisfies all five:

1. **Task intent** — what the user wants to accomplish (compare,
   choose, define, troubleshoot, plan, evaluate, configure, summarize).
2. **Format intent** — how the answer should be structured (steps,
   bullet list, comparison table, definition, checklist, pros/cons).
3. **Entity intent** — which specific brands/tools/concepts must be
   named.
4. **Depth intent** — how detailed the answer should be (high-level
   overview vs. expert deep-dive vs. beginner explanation).
5. **Constraint intent** — requirements the answer must respect (budget,
   speed, region, year, difficulty level, niche audience). The more
   granular the constraint match, the better the citation odds.

**AI-reuse formatting checklist** (make selected content easy to extract
and cite):
- [ ] Concise TL;DR (40-80 words) at the top of the page
- [ ] A "Short answer" block using bullets or numbered steps
- [ ] Clear H2/H3 headings that mirror likely user phrasing
- [ ] Short, atomic paragraphs — one idea per block
- [ ] Predictable templates the model recognizes (definitions,
      comparisons, FAQs, steps)
- [ ] Schema markup where relevant (FAQPage, HowTo, Article)
- [ ] Explicit, consistent entity naming throughout

## Measuring AI visibility as sustained topical authority

Per [[similarweb-how-to-be-the-brand-ai-recommends-2026]] (quoting
Aleyda Solis) — a concrete visibility-measurement target that sharpens
the wiki's general "track presence per topic" guidance:

- Don't chase perfection on any single prompt. Build structured prompt
  sets reflecting real buyer journeys — representative prompts across
  key topical hubs, product categories, and funnel stages (early
  research through final transaction).
- Ask "are we consistently visible across this intent category?" rather
  than "are we showing up for this one query?"
- **Target being cited/mentioned in roughly 70-80% of relevant,
  high-intent prompts within a topic cluster** as the bar for "won" — a
  concrete, quotable target where the wiki previously only had
  qualitative "track presence per topic" guidance.

## Third-party authority building (topic-specific)

Per [[growth-memo-topics-matter-for-third-party-authority]] — extends the
three-layer source strategy above with tactics specifically for earning
third-party citations/mentions:

- **Map trusted sources per topic, not per category.** Trusted-source mix
  can shift sharply even within one category depending on the specific
  query topic (competitor domains: 33.5% of citations for invoicing
  queries vs. 7% for business-startup queries) — build a source map for
  each topic you're targeting rather than assuming one map covers a
  whole category.
- **Concentrate in fewer, higher-authority placements rather than
  spreading thin.** Authority gains are tiered, not linear — three
  placements in a top-decile-authority source outperformed a dozen
  placements across low-authority sites in the source's 1,000-domain
  analysis. Prioritize getting into the top 1-2 outlets AI already cites
  for your topic over broad low-authority PR/guest-post campaigns.
- **Use named, credentialed authors instead of brand-account bylines.**
  Fresh, expert-authored, clearly time-stamped content earned faster
  visibility than faceless brand-account publishing (per LinkedIn's
  analysis, cited in the source).
- **Prioritize targets with a two-factor score.** Per
  [[similarweb-how-to-win-the-race-for-gen-ai-search-2026]], once you've
  identified the domains and specific cited URLs AI relies on for a
  topic, rank outreach targets by **Influence score** (how authoritative
  the domain is within that specific topic) × **Prompt frequency** (how
  often that URL is cited across user prompts) — the higher the combined
  score, the more citation impact a mention there is likely to have.
- **Action checklist**:
  - [ ] Identify 2-3 credible subject-matter experts to author/be quoted
        in third-party content.
  - [ ] Map which sources AI already cites for your specific topics
        (not just your category).
  - [ ] Concentrate outreach/PR effort on the highest-authority
        publications in that map.
  - [ ] Pursue nofollow placements too — citation value doesn't require
        a dofollow link.
  - [ ] Create embeddable data assets (charts/widgets other sites can
        embed, carrying a link back).
  - [ ] Publish on LinkedIn for faster indexing/visibility alongside
        primary publication.

## Brand-level visibility factors (correlational, not causally tested)

Per [[ai-visibility-correlation-factors]] — unlike the Tier 1-3 tactics
above, which were causally tested via controlled experiment, these are
**correlations only** (explicitly not causation per the source):

- **Build a YouTube presence.** Of all factors studied, YouTube mentions
  correlated strongest with AI-mention visibility (~0.737) — stronger
  than branded web mentions, backlinks, or Domain Rating.
- **Earn genuine mentions rather than manufacturing content volume.**
  Content volume showed almost no correlation with AI visibility —
  publishing more, by itself, isn't associated with more visibility.
- **If you're a smaller/challenger brand without established authority,
  target ChatGPT specifically.** It shows the weakest correlation with
  pre-existing brand-authority metrics of the three platforms studied —
  AI Mode in particular behaves like a "consensus engine" favoring
  already-known brands, so it's a harder surface to break into without
  existing authority.
- Backlinks and Domain Rating still correlate, but are the *weakest*
  correlates measured (0.19–0.33) — don't expect classic link-building
  alone to move AI visibility much.

## Sentiment monitoring and correction

Per [[similarweb-how-to-win-the-race-for-gen-ai-search-2026]] — a
distinct GEO workstream from citation/visibility: being cited isn't
enough if the AI's answer frames the brand negatively, inaccurately, or
as a "budget"/"lower-tier" option, since that shapes user perception
before any click happens. AI answers reflect the tone of the sources
they trust, not an invented judgment.

- **Track sentiment per topic, not just brand-wide** — a brand can read
  positively overall while one specific topic (e.g., a product line or
  use case) carries disproportionately negative framing.
- **Find the root cause before fixing anything**: are review sites
  describing the product inaccurately? Are outdated articles still
  ranking/getting cited? Are competitor comparisons framing the brand
  poorly? Is the brand's own content unclear or missing key information?
- **Fix via two levers, not one**:
  - *On-page*: clarify misunderstood features, correct outdated
    information, directly address the weaknesses users are asking
    about, add explicit positive entity descriptions, include
    structured facts the model can easily reuse.
  - *Off-page*: strengthen or correct the external sources AI relies on
    — fresh expert reviews, updated product comparisons, data-backed
    press mentions, new directory listings, improved UGC, corrected
    Wikipedia/G2/niche-directory entries.
- **Recheck after updates, on a delay.** Sentiment shifts slowly — re-run
  sentiment analysis after content updates, PR improvements, or new
  citations land, rather than expecting an immediate change.

## Query-format AIO risk (which pages to prioritize/audit)

Per [[aio-ctr-impact]], AI Overview trigger rate varies enormously by
query format — prioritize AEO/GEO work on pages targeting these formats,
since they're the most likely to have an AIO inserted above them:

| Query format | AIO trigger rate |
|---|---|
| Comparison ("X vs Y") | 95.4% |
| Review queries | 86.3% |
| Question-format | 85.9% |
| Price/cost/buy queries | 83.4% |
| "Best of" queries | 81.3% |
| "Near me" queries | 76.9% |
| Single-word queries | 27.3% (don't assume short queries are safe) |

Being cited within the AIO on these pages is worth **+120% more clicks**
than not being cited (though still below a no-AIO baseline) — see
[[aio-ctr-impact]] for the full economics.

## Measurement checklist: don't panic on CTR alone

Per [[aio-ctr-impact]], a falling CTR on AIO-cited queries can be a
measurement artifact rather than a real problem:

- [ ] Before reacting to a CTR drop, check impressions and clicks
      separately — did clicks actually fall, or did impressions surge
      (meaning you're earning *more* citations, not losing existing ones)?
- [ ] Track organic and paid CTR separately — they respond to AIOs very
      differently and one can look fine while the other looks alarming.
- [ ] Treat single-brand/single-account CTR anomalies with suspicion —
      aggregate benchmarks can be skewed by one outlier account.

## Technical crawlability (retrieval-eligibility prerequisite)

Per [[how-google-search-works]], none of the tactics above matter if a
page is never crawled, indexed, or served in the first place — this is
the layer beneath E-E-A-T:

- [ ] Is the page accessible to Googlebot — not accidentally blocked by
      `robots.txt`, and not requiring a login to view?
- [ ] If content is rendered via JavaScript, does it still appear when
      rendered with a headless/recent Chrome (i.e., does Google actually
      see it after rendering, not just in the raw HTML)?
- [ ] Is the page linked from somewhere Google can discover (internal
      links, a submitted sitemap), not an orphan page?
- [ ] Is there a clear canonical version if similar/duplicate content
      exists elsewhere, so Google doesn't pick the wrong page as
      canonical or split signals across duplicates?
- [ ] If a page is indexed but never appears in results, check whether
      it's a relevance/quality issue (see E-E-A-T checklist below) or a
      `robots` meta rule blocking serving specifically — these are
      different problems with different fixes.

## E-E-A-T signal-building (retrieval-eligibility foundation)

Per [[e-e-a-t-and-page-quality]], these don't move citation-stage
visibility metrics directly, but they're the retrieval-eligibility
foundation everything above depends on — Trust is the most important
factor, and low-E-E-A-T content risks not being surfaced as a candidate
source at all:

- [ ] Does the page or its author have a real, verifiable "About"/bio
      with genuine credentials or experience for the topic?
- [ ] For YMYL topics (health, finance, government/civics/safety), is
      the content expert-sourced and accurate, not just well-written?
- [ ] Is there independent evidence of trustworthiness (reviews, press,
      citations from others) beyond what the site says about itself?
- [ ] Are there conflicts of interest undisclosed (e.g., a manufacturer's
      own "review" of its product)? Disclose them or avoid the format.

**Critical warning — Scaled Content Abuse**: per
[[e-e-a-t-and-page-quality]], Google explicitly rates pages **Lowest
quality** when generative AI (or any automation) is used to produce many
low-effort, low-value pages — "no matter how it's created," and even
under mere suspicion of the pattern. This isn't just "content volume
doesn't help" (per [[ai-visibility-correlation-factors]]) — scaled,
low-effort AI content is an explicit penalty target. If using AI to help
draft content, ensure each page has genuine added value, editing, and
originality; don't publish AI output at scale with little to no human
curation.

## Know-Simple answer structuring

Per [[search-intent-and-needs-met]], "Know Simple" queries (short,
factual, one-right-answer) get pulled into concise direct-answer
treatments. For any page targeting this kind of query:

- [ ] Is there one clear, complete, correctly-stated 1-2 sentence answer
      to the specific factual question, not buried in a longer narrative?
- [ ] Does that answer appear early/prominently rather than only at the
      end of a long article?

## Domain-specific guidance

Tactic effectiveness varies by content domain/query type — pick the
tactic that matches your content's domain rather than defaulting to the
Tier 1 list blindly:

| Tactic | Works best for |
|---|---|
| Authoritative | Debate-style content, History, Science |
| Fluency Optimization | Business, Science, Health |
| Cite Sources | Factual/statement content, Law & Government |
| Quotation Addition | People & Society, Explanation, History |
| Statistics Addition | Law & Government, Debate, Opinion |

## Checklist for a page you want cited by AI answer engines

- [ ] Does every non-trivial claim have a citation to a credible source?
- [ ] Are there direct quotes from authoritative sources, not just
      paraphrase?
- [ ] Are quantitative stats included instead of vague qualitative claims
      where possible?
- [ ] Is the writing fluent and easy to understand, not just
      keyword-dense?
- [ ] Have you avoided keyword stuffing and unnatural repetition?
- [ ] Does the tone/tactic match the content's domain (see table above)?
