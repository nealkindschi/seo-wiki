---
type: concept
tags: [seo, aeo]
updated: 2026-08-13
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

## GEO (LLM chat optimization) vs. AI Overview optimization — distinct disciplines

Per [[wix-generative-engine-optimization]] — this wiki's tactics have so
far mostly concerned Google's AI Overviews and citation behavior inside
generative engines generally, but **optimizing for LLM chat products
(ChatGPT, Gemini, Perplexity, Claude) is a genuinely separate discipline
from optimizing for Google AI Overviews**, with a different user
journey:

| | LLMs for search | AI Overviews in Google Search |
|---|---|---|
| Entry | Users choose to use the LLM | Users happen upon it (doesn't trigger for every query) |
| Interaction | Users interact, ask follow-ups, go deeper | Users passively receive the generated content |
| Control | Users control which LLM/content they engage with | Generated according to system needs, no opt-in |

Treat "get cited in an LLM chat answer" and "get cited in a Google AI
Overview" as separate targets requiring separate tactics, not one
generic "AI search visibility" goal.

### A finer LLM taxonomy (three categories, not just training/indexing/retrieval bots)

Beyond the training/indexing/retrieval crawler taxonomy in
[[how-google-search-works]], LLM *products* themselves split into three
categories relevant to optimization strategy:

1. **Static pre-trained-data LLMs** (Claude 3-3.5, GPT-3, Gemini 1.5,
   NotebookLM, the Copilot app) — answers come from a fixed training
   set; links are often absent. Optimize for **brand mentions, not
   links** — track via bulk brand/entity queries rather than expecting
   referral traffic. Visibility only changes when the training set is
   updated (a model-specific "knowledge cutoff" date gates eligibility
   entirely). User feedback (thumbs up/down on responses) can correct
   brand inaccuracies even between training updates.
2. **Search-augmented LLMs** (Perplexity, Copilot, GPT-4) — a fixed
   training set augmented by live search-engine data; links/citations
   appear and update via web crawling. Optimization here resembles
   optimizing for the *underlying* search engine (e.g. Copilot
   visibility follows Bing rankings, not Google's) — check core queries
   regularly, since visibility fluctuates like search rank.
3. **Reasoning models with search** (DeepSeek R1-R2, Gemini 2.5, OpenAI
   o1-o4) — "mixture of experts" niche-task networks that also crawl
   and cite live web content.

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

## Measurement framework: five weekly GEO metrics

Per [[airops-geo-strategy-playbook]] — GEO needs its own scorecard and
review cadence rather than folding into an existing SEO dashboard,
because "the two disciplines are answering two different questions for
two different judges." Track these five metrics **weekly**, not
quarterly:

1. **Citation rate** — how often a page is used as a cited source.
2. **Mention rate** — brand references without an accompanying link
   (relevant especially for static pre-trained LLMs, per the taxonomy
   above, which rarely surface links at all).
3. **Share of voice** — visibility relative to competitors across
   identical prompts.
4. **Sentiment** — whether brand descriptions read positive, neutral, or
   negative; see [[geo-content-optimization-tactics]]'s sentiment
   monitoring section for the fix workflow.
5. **Source attribution** — where citations actually originate from.

**Origin of this framework**: per [[airops-north-star-metric-ai-search]]
(the same publisher, 2025-07-31, about a year earlier), the original
proposal was a single composite **Brand Visibility Score** — "answers
mentioning your brand ÷ total answers for your category" — built from
just three of the five sub-metrics above (citation rate, sentiment,
share of voice). The later report splits this into five separately-
tracked weekly metrics rather than one blended score. Two concrete
formulas from the earlier report are still useful and not superseded:

- **Sentiment Score** = (Positive mentions + 0.5 × Neutral mentions) ÷
  Total mentions.
- **Brand Visibility Score** = answers mentioning your brand ÷ total
  answers for your category — a reasonable single top-line number if
  you want one composite metric rather than tracking all five
  separately.

"AI doesn't click. It answers." — the earlier report's framing for why
click/pageview/CTR/MQL metrics fail to capture this: pageviews are
inflated by bots and misaligned clicks, traditional rankings don't
guarantee AI-interface surfacing, CTR is largely irrelevant amid
zero-click answers, and leads/MQLs are often vanity metrics without
revenue attribution.

**Why weekly**: visibility is volatile — only 30% of brands stay visible
in AI answers from one run to the next, and just 20% remain visible
across five consecutive identical prompts. A quarterly check can miss an
entire decay-and-recovery cycle. This isn't hypothetical: per
[[seoclarity-chatgpt-citation-decline-analysis]], ChatGPT citation
volume fell 86-94% across five markets between February and April
2026 (tied to two dated OpenAI platform changes), then rebounded to
pre-March levels by May — a quarterly-cadence team would have measured
either the trough or the recovery and drawn the wrong long-term
conclusion either way. See [[ai-citation-landscape]]'s "Citation volume
volatility over time" section for the full data. Run GEO tracking **parallel to** SEO
tracking, not as a replacement for it — analyze visibility at the
**query level**, not brand level, to catch gaps specifically in
comparison/evaluation-stage prompts (where buying decisions actually
happen), rather than only tracking a blended brand-wide number.

## TOFU investment: the 50% visibility test

Per [[siegemedia-tofu-content-geo]] — a decision layer for *which*
topics deserve top-of-funnel content investment at all, distinct from
the weekly citation/mention/sentiment tracking above (which measures
performance once a topic is already chosen):

- **A topic qualifies for continued TOFU investment only if both**: (1)
  the brand achieves 50%+ visibility across multiple LLM platforms for
  that topic's query, and (2) the topic carries enough search volume to
  justify the investment. Topics failing either test should be
  deprioritized.
- **Why 50%**: LLMs increasingly *name specific vendors* when answering
  category-definition questions, not just define the term — e.g.
  HubSpot appears in 83% of Gemini responses to "what is CRM?" TOFU
  content's job has shifted from "rank for the definitional query" to
  "be the vendor named alongside the definition."
- **Qualifying topics**: product-connected/category-defining questions
  where the answer inherently references vendors (e.g. "what is CRM?").
  **Disqualifying topics**: purely definitional/encyclopedic questions
  answerable with no commercial reference (e.g. "what is
  photosynthesis?") — no visibility threshold makes these worth TOFU
  budget.
- **Challengers should target sub-category and problem-framed queries**
  ("CRM for real estate teams," "CRM with best mobile app") where a
  category leader's flagship-term dominance doesn't carry over — these
  are separate visibility opportunities, not just a smaller slice of
  the same competition.
- **Platform variation is large enough to require testing on multiple
  platforms, not one**: HubSpot's 83% Gemini visibility for "what is
  CRM?" doesn't transfer to Google's AI Overview for the identical
  query, where different vendors are named instead.
- **The "re-index method"**: sample TOFU topics across multiple LLMs/
  runs weekly, flag topics at/above the 50% threshold, cross-reference
  against search volume, and prioritize investment accordingly —
  consistent with the weekly (not quarterly) cadence argued for above.

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
- [[wix-generative-engine-optimization]] — the source for the GEO-vs-
  AI-Overview distinction and LLM taxonomy above; also has practical
  tactics in [[geo-content-optimization-tactics]]'s LLM-chat-specific
  section.
- [[ai-traffic-scale-vs-hype]] — a scale check on this whole domain: as
  of early-2026 clickstream data, standalone AI tools remain a tiny
  fraction of overall search/social traffic, so the tactics in this
  page matter most where they overlap with Google's own AI features
  (which inherit Google's dominant search share) rather than in
  isolation. Worth reading alongside [[airops-geo-strategy-playbook]]'s
  94%-of-B2B-buyers-use-AI stat: low aggregate traffic share and high
  purchase-decision influence are not contradictory, since the latter
  measures a considered-buyer subset rather than overall web traffic.
- [[airops-geo-strategy-playbook]] — the source for the five-metric
  weekly measurement framework above, plus buyer-adoption context (94%
  of B2B buyers use generative AI in purchase decisions, 98% of
  enterprise marketers already optimizing or planning to).
- [[airops-north-star-metric-ai-search]] — the earlier (2025-07-31)
  single-metric precursor to the five-metric framework above, source of
  the Sentiment Score and Brand Visibility Score formulas and the
  Content Engineer/Content Strategist/Growth Engineer team-structure
  model (see [[enterprise-seo-strategy]]).
- [[rerankers-and-passage-selection]] — the passage-level model
  mechanism (retrieval → reranking → generation) underneath the
  brand-level citation-rate metric above; explains *why* a page can be
  indexed and ranking yet still lose the citation.
- [[siegemedia-tofu-content-geo]] — the source for the TOFU 50%-
  visibility investment test above.
- [[siegemedia-versus-pages]], [[siegemedia-best-x-pages]],
  [[siegemedia-llm-brand-visibility]] — comparison-content and
  descriptor-consistency tactics in
  [[geo-content-optimization-tactics]]'s "Vendor evaluation readiness"
  and "Sentiment monitoring" sections.

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
