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
