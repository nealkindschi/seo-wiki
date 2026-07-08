---
type: concept
tags: [seo, aeo]
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

## Appearing & measuring performance in Google's AI features

Per [[google-ai-features-appearance-guide]], Google states there are "no
additional requirements to appear in AI Overviews or AI Mode" beyond
standard indexing/snippet eligibility — reinforcing
[[google-ai-optimization-guide]]. Both AI Overviews and AI Mode may use
"query fan-out" (issuing multiple related sub-queries) to build a
response. AI-feature traffic is measurable: it shows up in Search
Console's Performance report under the "Web" search type, and Google
states AI-Overview clicks show higher-quality engagement. Site owners
who want to *limit* rather than maximize inclusion have explicit
controls — see [[controlling-ai-feature-inclusion]].

## Conflicting Evidence

- **Claim**: Traditional SEO is largely obsolete for generative engines,
  and content should be optimized specifically for AI citation/visibility
  using distinct tactics (quotes, stats, citations).
  - Supported by: [[geo-generative-engine-optimization-aggarwal-2023]]
    (2023-11), which found classic SEO tactics like keyword stuffing
    don't transfer and citation-style content tactics do.
  - Contradicted by: [[google-ai-optimization-guide]] (2026-06), Google's
    official guidance, which states SEO fundamentals remain "the
    foundation" for AI Overviews/AI Mode and explicitly advises against
    building special AI-only infrastructure (`llms.txt`, chunking,
    AI-specific rewriting).
- **Current best guess**: these findings describe **different stages of
  the same funnel**, not a true contradiction:
  - **Retrieval eligibility** (will your content even be considered as a
    candidate source?) — governed by classic SEO fundamentals:
    [[how-google-search-works]] (technical crawling/indexing/serving),
    avoiding thin/manipulative content, and [[e-e-a-t-and-page-quality]]
    (Experience, Expertise, Authoritativeness, Trust). This is what
    Google's guidance addresses, and it doesn't test or claim anything
    about citation-style content within an already-retrieved set.
  - **Citation-stage visibility** (given you're one of the sources fed to
    the model, how much does the generated answer actually use/cite
    you?) — this is what the GEO paper measures, and it's silent on
    retrieval eligibility.
  - Google's specific claims (no need for `llms.txt`, no need to chunk
    content, don't rewrite "for AI") are about **infrastructure/format**,
    not about whether citation-friendly content style (quotes, stats,
    sourcing) matters — and those tactics arguably overlap with Google's
    own "helpful, reliable, people-first" framing rather than opposing it.
  - Flagged as unresolved: whether Google's own AI Overviews specifically
    respond to the GEO paper's citation-style tactics the same way the
    third-party generative engines tested in that paper (GPT-3.5-based,
    Perplexity.ai) did is untested as of this wiki's current sources.

## See also

- [[ai-citation-landscape]] — empirical data on what ChatGPT, Claude, and
  Gemini actually cite in practice (media mix, provider differences,
  Wikipedia/Reddit/Axios patterns). Complements the tactics above with
  real-world citation composition data, and partially answers the "does
  this hold for newer/other generative engines" open question below —
  though it studies citation *composition*, not the effect of applying
  GEO *tactics* on ChatGPT/Claude/Gemini specifically.
- [[aio-ctr-impact]] — the economic payoff of citation: being cited in a
  Google AI Overview delivers +120% more clicks than not being cited
  (though still below a no-AIO baseline). This is the real-world traffic
  rationale for why the citation-focused tactics above are worth doing.
- [[e-e-a-t-and-page-quality]] — the retrieval-eligibility foundation
  referenced in Conflicting Evidence above: the actual official framework
  behind "classic SEO fundamentals"/"helpful, people-first content."
- [[how-google-search-works]] — the technical crawl/index/serve pipeline
  underneath "technical crawlability": if a page isn't crawled, indexed,
  or served in the first place, it can never become a candidate source
  for any generative engine either.
- [[search-intent-and-needs-met]] — Google's query-intent taxonomy;
  "Know Simple" queries are directly relevant to structuring
  answer-friendly content.
- [[ai-coding-agent-tool-selection]] — a sibling GEO/AEO domain: the
  same "visibility inside an AI-generated answer" mechanic, but for
  coding agents choosing which *tool/library* to recommend rather than
  chat/search engines choosing which *content* to cite.
- [[agentic-web-optimization]] — a third sibling domain: optimizing a
  site so general-purpose AI agents can *act* on it (browse, fill
  forms, complete purchases), a higher bar than being cited.
- [[ai-traffic-scale-vs-hype]] — a scale check on this whole domain: as
  of early-2026 clickstream data, standalone AI tools remain a tiny
  fraction of overall search/social traffic, so the tactics in this
  page matter most where they overlap with Google's own AI features
  (which inherit Google's dominant search share) rather than in
  isolation.

## Open questions

- The GEO paper's tactics were tested on GPT-3.5-based generative engines
  and Perplexity.ai. Whether those specific tactics (quotes, stats,
  citations) move the needle the same way on ChatGPT, Claude, or Gemini
  specifically is still untested — [[ai-citation-landscape]] shows these
  three providers already behave very differently from each other in
  citation composition, so tactic effectiveness may vary by provider too.
- Whether Google's "don't rewrite specifically for AI" advice is in
  tension with citation-style optimization tactics, or whether those
  tactics are simply a subset of "helpful, people-first" writing, is
  unresolved — see Conflicting Evidence above.
