# Log

Append-only chronological record of wiki activity. Each entry starts with
a consistent prefix so the file stays greppable, e.g.
`grep "^## \[" wiki/log.md | tail -5`.

Format:
```
## [YYYY-MM-DD] ingest | <source title>
## [YYYY-MM-DD] query | "<question>"
## [YYYY-MM-DD] lint | <summary of findings>
## [YYYY-MM-DD] conflict | <topic> — <one-line description>
```

---

## [2026-07-07] ingest | GEO: Generative Engine Optimization (Aggarwal et al., 2023/2024)

First source ingested. Created [[generative-engine-optimization]] (concept)
and [[geo-content-optimization-tactics]] (playbook). No prior wiki content
existed, so no conflicts to reconcile.

## [2026-07-07] ingest | Google's Guide to Optimizing for Generative AI Features on Google Search

Updated [[generative-engine-optimization]] and
[[geo-content-optimization-tactics]] with Google's official AI-optimization
guidance.

## [2026-07-07] conflict | GEO/AEO tactics vs. Google's official guidance — retrieval-stage vs. citation-stage framing

[[generative-engine-optimization]]: reconciled as addressing different
funnel stages (see Conflicting Evidence section on that page); flagged as
not fully resolved whether Google's AI Overviews respond to GEO's
citation-style tactics the same way third-party generative engines do.

## [2026-07-07] ingest | AI Features and Your Website (Google Search Central)

Extended [[generative-engine-optimization]] with a measurement section
(Search Console "Web" reporting) and created new playbook
[[controlling-ai-feature-inclusion]] for opt-out/control mechanisms.
Agrees with and extends [[google-ai-optimization-guide]]; no conflicts.

## [2026-07-07] ingest | Generative Pulse: What Is AI Reading? (Muck Rack, May 2026)

Created new concept [[ai-citation-landscape]] for empirical citation
patterns across ChatGPT/Claude/Gemini. Added a provider-specific tactics
section to [[geo-content-optimization-tactics]] and cross-linked from
[[generative-engine-optimization]]. Landscape/empirical data, complements
rather than conflicts with existing sources.

## [2026-07-07] ingest | Top Brand Visibility Factors in ChatGPT, AI Mode, and AI Overviews (Ahrefs)

Created new concept [[ai-visibility-correlation-factors]] for the
75k-brand correlation study. Added brand-level correlational guidance to
[[geo-content-optimization-tactics]] (YouTube presence, earned mentions,
ChatGPT-targeting for smaller brands).

## [2026-07-07] conflict | Cross-provider domain-level divergence vs. brand-level mention overlap

[[ai-citation-landscape]] and [[ai-visibility-correlation-factors]]:
reconciled as different units of analysis (which source domains get
cited, vs. whether a brand gets mentioned at all) — see Conflicting
Evidence sections on both pages; flagged as unresolved since no source
has directly tested both at once.

## [2026-07-07] ingest | AIO Impact on Google CTR: 2026 Update (Seer Interactive)

Created new concept [[aio-ctr-impact]] for the citation-premium and CTR
economics data. Added query-format AIO-risk table and an
impressions-vs-clicks measurement checklist to
[[geo-content-optimization-tactics]]; cross-linked from
[[generative-engine-optimization]] as the economic rationale for
citation tactics. No conflicts.

## [2026-07-07] ingest | Google Search Quality Rater Guidelines (Sept 2025 edition)

Created two new concepts: [[e-e-a-t-and-page-quality]] (YMYL, E-E-A-T,
Page Quality tiers, and the three AI-era abuse patterns) and
[[search-intent-and-needs-met]] (query intent taxonomy, Needs Met
scale). Added E-E-A-T signal-building and Know-Simple answer-structuring
guidance to [[geo-content-optimization-tactics]], including an explicit
warning against Scaled Content Abuse. Cross-linked from
[[generative-engine-optimization]] (retrieval-eligibility foundation)
and [[ai-visibility-correlation-factors]] (official policy explanation
for the content-volume finding). No conflicts — this source provides
the official policy foundation several prior sources' findings were
implicitly describing.

## [2026-07-07] ingest | Google Search Status Dashboard — History

Backfilled ~34 dated ranking updates/incidents (July 2021–June 2026)
into `wiki/timeline.md`, extending its earliest entry back from
2023-11-16 to 2021-07-26. Created new concept
[[google-algorithm-update-history]] describing the update-type taxonomy
and the pattern of helpful-content/reviews updates merging into core
updates after 2023. This is a live page — re-ingest periodically for new
entries. No conflicts.

## [2026-07-07] ingest | How Google Search Works

Created new concept [[how-google-search-works]] (crawl/index/serve
pipeline) — the technical foundation underneath "retrieval eligibility"
and "technical crawlability," previously referenced but never defined.
Added a technical crawlability checklist to
[[geo-content-optimization-tactics]]. Cross-linked from
[[generative-engine-optimization]] and [[e-e-a-t-and-page-quality]]. No
conflicts.

## [2026-07-07] ingest | Ranking Factors Study 2024 (Semrush)

Created new concept [[traditional-seo-ranking-factors]] (classic
organic-SERP correlation data) and new playbook
[[classic-seo-ranking-factors]] (kept separate from
[[geo-content-optimization-tactics]] given the latter's growing size and
AEO-specific focus). Cross-linked from [[ai-visibility-correlation-factors]]
(direct classic-vs-AI comparison table) and [[e-e-a-t-and-page-quality]]
(independent empirical confirmation via reviews/star-rating correlation).
No conflicts — reinforces existing findings from an independent,
larger-scale, classic-SERP-focused dataset.

## [2026-07-07] ingest | Make links crawlable (Google Search Central)

Created new source [[google-links-crawlable]] and new playbook
[[link-and-anchor-text-best-practices]] (crawlable `<a href>` markup
requirements, anchor text writing rules, internal/external linking
guidance, `rel` attribute usage). Cross-linked from
[[how-google-search-works]] (links feed the crawling stage's URL
discovery) and [[classic-seo-ranking-factors]] (backlink-building
tactic now points to the link-mechanics playbook). No conflicts —
net-new technical guidance with no prior wiki coverage of link markup
or anchor text.

## [2026-07-07] ingest | Internal Links for SEO: An Actionable Guide (Ahrefs)

Created new source [[ahrefs-internal-links-for-seo]]. Substantially
expanded [[link-and-anchor-text-best-practices]]'s internal-linking
section: pyramid site structure/3-click rule, siloing + topic clusters,
reasonable-surfer link placement, power-page/content-refresh linking,
pagination markup, dofollow/crawler accessibility, and a broken-link/
orphan-page audit workflow.

## [2026-07-07] conflict | ideal number of internal links per page

[[ahrefs-internal-links-for-seo]] recommends 3-5 contextual links per
article as an "optimal" density (PageRank-dilution argument); Google's
own [[google-links-crawlable]] explicitly declines to give a number
("no magical ideal number of links... if you think it's too much, then
it probably is"). Logged as unresolved Conflicting Evidence on
[[link-and-anchor-text-best-practices]] — current best guess: treat
3-5 as a starting heuristic for typical posts, not a hard rule, since
Google is the primary ranking-authoritative source and deliberately
avoids a numeric target.

## [2026-07-07] conflict | ideal number of internal links per page — resolved

User directive: trust Google over Ahrefs on this — no numeric cap on
internal links per page. Updated [[link-and-anchor-text-best-practices]]'s
Conflicting Evidence entry and §4 "Link count" bullet to drop the "3-5"
heuristic and defer entirely to Google's "if you think it's too much,
then it probably is" guidance. Ahrefs' claim remains recorded in the
Conflicting Evidence section for reference, marked superseded rather
than deleted.

## [2026-07-07] ingest | Internal linking for SEO: why and how (Yoast)

Created new source [[yoast-internal-linking-for-seo]]. Added
cornerstone-content two-way linking, taxonomy/tag-page linking hubs, and
related/popular-posts modules to [[link-and-anchor-text-best-practices]]
§4. Cross-linked to [[generative-engine-optimization]] for the source's
GEO/AI-context framing. Noted (not applied) a minor tension: this
source recommends exact-match anchor text "when possible," which leans
more keyword-forward than Google's "avoid keyword stuffing" guidance
already in the playbook — per the user's standing preference to trust
Google over third-party SEO blogs on divergence, kept the playbook's
existing natural/varied anchor-text guidance unchanged. No numeric
link-count claim from this source — consistent with the wiki's current
Google-aligned no-cap position.

## [2026-07-07] ingest | What Claude Code Actually Chooses (Amplifying, Feb 2026)

New topic area: optimizing for coding-agent tool recommendations, not
just chat/search content citation. Created new concept
[[ai-coding-agent-tool-selection]] and new playbook
[[optimizing-for-coding-agent-recommendations]] from
[[amplifying-claude-code-picks-2026]] (2,430-prompt study of Claude
Code's tool picks across 20 categories/4 repos/3 models). Cross-linked
as a sibling domain from [[generative-engine-optimization]] — same
"visibility inside an AI-generated answer" mechanic, different engine
type (coding agent vs. chat/search) and audience (tool vendors vs.
content publishers). No conflicts — first source on this topic.

## [2026-07-07] ingest | Codex vs Claude Code: AI Agent Tool Selection Study (Amplifying, Mar 2026)

Created new source [[amplifying-codex-vs-claude-code-picks-2026]].
Extended [[ai-coding-agent-tool-selection]] with cross-agent findings:
7/12 category agreement (mostly Custom/DIY), parent-company acquisition
bias (Codex/Statsig, Claude/Bun), Cloudflare-vs-Vercel platform
lock-in, and "conversion differs more than awareness." Extended
[[optimizing-for-coding-agent-recommendations]] with a new tactic
(§7): measure and optimize per-agent, since top picks diverge sharply
between Codex and Claude Code outside standardized categories. No
conflicts — complementary follow-up to
[[amplifying-claude-code-picks-2026]], reinforcing its build-over-buy
finding on a second agent and adding acquisition/platform-affinity
data.

## [2026-07-07] ingest | The Consensus Gap (Search Engine Journal, Kevin Indig)

Created new source [[sej-the-consensus-gap]] (3.7M-URL-citation study,
ChatGPT/Perplexity/Google AI Overviews). Added the presence/
portability/concentration measurement framework, the ~2.35-2.45%
universal-overlap finding, and content-type portability ranking to
[[ai-citation-landscape]]. Added a cross-reference note to
[[ai-visibility-correlation-factors]]'s Conflicting Evidence section —
this source independently corroborates the citation-fragmentation
side of that unresolved reconciliation (different engine set,
different methodology, same conclusion) but doesn't resolve the
brand-vs-URL tension since it also measures URL-level, not
brand-level, overlap. Added measurement/prioritization tactics to
[[geo-content-optimization-tactics]]. No new conflicts — strengthens
an existing wiki finding.

## [2026-07-07] ingest | Why AI Engines Cite Different Sources but Recommend the Same Brands (BrightEdge)

Created new source
[[brightedge-ai-search-same-brands-different-sources]] (5-engine
citation study: ChatGPT, Perplexity, Gemini, Google AI Mode, Google AI
Overviews). Added engine sourcing-personality profiles, the
Google-surfaces-aren't-monolithic finding, sentiment data, and the
three-layer source framework to [[ai-citation-landscape]]. Added the
three-layer strategy, category-relative-authority guidance, and
buyer-reliance engine-weighting to [[geo-content-optimization-tactics]].

## [2026-07-07] conflict | citation-source fragmentation vs. brand-mention convergence — resolved

This source directly tests both sides of the previously-unresolved
conflict (flagged 2026-07-07, earlier today) on the same 5-engine
dataset: pairwise source overlap (16-59%) is measurably wider/more
inconsistent than pairwise brand overlap (36-55%) across every engine
pair studied. Updated the Conflicting Evidence sections on
[[ai-citation-landscape]] and [[ai-visibility-correlation-factors]]
from "unresolved, plausible inference" to "resolved, directly tested" —
old claims kept and marked superseded-with-reasoning, not deleted, per
the wiki's conflict-handling convention. One residual methodology
caveat noted (not a contradiction): BrightEdge's aggregate top-100-list
overlap numbers read higher than [[sej-the-consensus-gap]]'s per-prompt
exact-URL overlap, which is a granularity difference between the two
measurement approaches.

## [2026-07-07] ingest | Why Most Original Data Never Gets Cited (Growth Memo)

Created new source
[[growth-memo-why-most-original-data-never-gets-cited]] (analysis of
Gauge's 301-page/1,075-citation dataset). Added a new "Publish
citation-ready primary research/benchmarks" section to
[[geo-content-optimization-tactics]], extending Tier 1's existing
Statistics-Addition/Cite-Sources tactics with the structural finding
that primary research only earns outsized citation density (3.3x) when
packaged as a named-item benchmark comparison, not raw data — plus a
7-characteristic checklist and URL-stability warning (64/365 cited
URLs in the dataset were dead/redirected). No conflicts — first source
on benchmark/primary-research content structure specifically.

## [2026-07-07] ingest | Technical SEO Checklist for Search Engines and AI Search (Semrush)

Created new source [[semrush-technical-seo-checklist]] and new playbook
[[technical-seo-audit-checklist]] (crawling/indexing, UX/Core Web
Vitals, navigation, code/config, and AI grounding/agent readiness
including new ecommerce/agentic-commerce checkout guidance). Navigation
section cross-links to [[link-and-anchor-text-best-practices]] rather
than duplicating it (site-structure/breadcrumbs/orphan-page content
already covered there). Cross-linked from [[how-google-search-works]]
and [[controlling-ai-feature-inclusion]] (opposite goal: ensuring AI
crawlers aren't accidentally blocked, vs. deliberately excluding them).
No conflicts.

## [2026-07-07] ingest | How to Optimize for the Agentic Web (Semrush)

Created new source [[semrush-optimize-for-agentic-web]], new concept
[[agentic-web-optimization]] (the agentic-web definition, five-layer
optimization stack, four emerging protocol standards — MCP/WebMCP/ACP/
UCP), and new playbook [[optimizing-for-the-agentic-web]] (actionable
layers 2-5, cross-linked to [[technical-seo-audit-checklist]] for
layer 1, plus a visibility+action measurement framework). This is a
third sibling domain alongside [[generative-engine-optimization]]
(citation-focused) and [[ai-coding-agent-tool-selection]]
(coding-agent tool picks) — cross-linked from both. Added the "AI
visitor worth 4.4x more in conversion value" stat to [[aio-ctr-impact]]
as a related-but-distinct data point (session conversion value, not
citation-premium CTR). No conflicts — all layers either net-new or
consistent with/complementary to existing wiki content.

## [2026-07-07] ingest | Topics Matter for Third-Party Authority Signals (Growth Memo)
Ingested Kevin Indig/Amanda Johnson's Growth Memo piece on topic-specific
AI source trust. Extended [[ai-citation-landscape]] (topic-level source
trust variance: 33.5% vs. 7% competitor-domain citation share by topic),
[[ai-visibility-correlation-factors]] (Authority Score's 0.65 Pearson
correlation, flagged with a metric-comparability caveat vs. this page's
existing Domain Rating figures), and [[geo-content-optimization-tactics]]
(new "Third-party authority building" section: tiered authority
accumulation, named-author-over-brand-account bylines, and a 6-item
action checklist). No conflicts — all additions extend existing claims.

## [2026-07-07] ingest | Why proprietary data is your most defensible AI citation asset (Growth Memo)
Ingested Kevin Indig/Amanda Johnson's companion piece (2026-06-29, published
~1 week before [[growth-memo-why-most-original-data-never-gets-cited]], on
a different dataset — On-Page.ai information-gain research). Extended
[[geo-content-optimization-tactics]]'s "Publish citation-ready primary
research/benchmarks" section with a quantified placement stat (44.2% of
citations from a page's first 30%), an "ownership doesn't guarantee
citation" note, and information-gain-by-figure-count correlation data
(62.1 vs. 40.2). Cross-linked as a companion source with
[[growth-memo-why-most-original-data-never-gets-cited]] — independent
datasets converging on the same core claim, no conflicts.

## [2026-07-07] ingest | Semrush AI Overviews Study (2025 full-year data)
Ingested Semrush's 10M+-keyword AI Overview study. Extended
[[aio-ctr-impact]] with a full-2025 AIO prevalence trajectory
(6.49%→24.61% peak→15.69%), intent-based expansion, a zero-click-rate
decrease (33.75%→31.53%), industry saturation data, AIO-keyword
characteristics, and SERP feature co-occurrence shifts. Flagged two soft
tensions (not contradictions) against the existing Seer-based intent
prevalence figures and CTR data — different studies/snapshots/metrics,
noted inline rather than resolved as a formal conflict.

## [2026-07-07] ingest | Influence Happens Everywhere (SparkToro, Rand Fishkin)
Ingested SparkToro's clickstream study of the top 5,000 most-visited
sites. Created new concept page [[ai-traffic-scale-vs-hype]]: search+social
≈ half of all visits, Google ~73% of search and bigger than the next 13
sites combined, AI tools ~1/1,000th their press coverage in actual
traffic, influence-precedes-search, attribution bias toward search, and
the case that Google-embedded AI (not standalone AI tools) is the bigger
competitive stake. Cross-linked from [[generative-engine-optimization]]
and [[aio-ctr-impact]] as a scale caveat. No conflicts — this measures a
dimension (overall channel scale) not previously covered in the wiki.
