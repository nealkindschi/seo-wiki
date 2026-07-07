---
type: playbook
tags: [seo]
updated: 2026-07-07
---

# Link and Anchor Text Best Practices

Why/when to use this: apply during content authoring, template/CMS
audits, and technical SEO reviews — link markup and anchor text quality
directly affect whether Google can discover a page at all (see
[[how-google-search-works]]'s crawling stage) and how it interprets what
the linked page is about. Based on [[google-links-crawlable]] and
[[ahrefs-internal-links-for-seo]].

## 1. Make links crawlable

Google only reliably crawls a link if it is a real `<a>` HTML element
with an `href` attribute containing a resolvable URL.

**Use:**
- `<a href="https://example.com/stuff">`
- `<a href="/products">` or `<a href="./products/category/shoes">`
- `<a href="/products.php?id=123">`
- JS-inserted links are fine *if* they render as real `<a href>` markup
  — verify with the URL Inspection Tool.

**Avoid:**
- `<span href="...">` or other non-anchor elements styled as links.
- Framework-specific routing attributes alone, e.g. `<a routerLink="...">`
  with no `href`.
- `onclick`-only navigation with no `href`.
- `javascript:` pseudo-URLs (`href="javascript:goTo('products')"`).

## 2. Write good anchor text

- **Test**: read the anchor text alone, out of context — it should still
  make sense and describe the destination.
- Be descriptive, reasonably concise, and relevant to both the page it's
  on and the page it links to.
- **Avoid** generic text: "click here," "read more," "website,"
  "article."
- **Avoid** keyword stuffing — write naturally; ask whether the reader
  actually needs each keyword to understand the next page.
- **Vary anchor text** across multiple links to the same page using
  natural phrasing variations (e.g. "email marketing strategies,"
  "building subscriber lists," "effective email campaigns" all pointing
  to the same guide) rather than repeating one exact phrase.
- **Avoid** excessive length — trim to the specific, load-bearing part
  of the sentence.
- **Avoid** chaining multiple adjacent links with no separating context
  (readers can't tell them apart, and each loses its own descriptive
  text).

## 3. Anchor text fallbacks

- Empty link text → Google falls back to the `title` attribute if
  present.
- Image links → Google uses the image's `alt` attribute as anchor text.
  Always write descriptive `alt` text on linked images, not `alt=""`.

## 4. Internal linking

- Every page you care about should have a link from at least one other
  page on the site — orphan pages are a discovery risk (see
  [[how-google-search-works]]'s URL-discovery step) and get no PageRank
  distribution.
- Link contextually: point to resources on the site that actually help
  the reader understand the current page. Gael Breton: "as long as it
  contextually makes sense to link to another page of your site, you
  should do it."
- **Site structure**: use a top-down pyramid hierarchy — homepage → main
  category → subcategory → individual page — keeping every page within
  ~3 clicks of the homepage. John Mueller: this "helps us a lot more to
  understand the context of individual pages within the site." Reinforce
  with breadcrumbs (Google treats breadcrumbs as normal links for
  PageRank purposes).
- **Siloing + topic clusters, combined**: use clean folder-based URL
  structure (silos) but don't let it block contextual cross-topic
  linking — strict silos that forbid inter-topic links sacrifice
  authority distribution and relevance. Layer topic clusters (pillar
  pages reciprocally linked to subtopic pages) on top.
- **Link placement ("reasonable surfer" model)**: link value correlates
  with click likelihood, so place priority links accordingly —
  in-content/editorial links (highest) > navigation/breadcrumbs
  (medium, structurally useful but algorithmically discounted) >
  footer/deep sidebar links (lowest). Put your most important links
  early in the content, above-the-fold when possible.
- **Prioritize high-value pages**: identify pages that represent core
  business value (key products, cornerstone content) and link to them
  prominently and often.
- **Link count**: no numeric target — follow Google's guidance (see
  "Conflicting Evidence" below) and link as much as genuinely serves the
  reader. Don't cap at an arbitrary count like Ahrefs' "3-5."
- **During content refreshes**: add links from newly published content
  back to (and from) relevant older pages; use high-authority "power
  pages" to pass authority to newer or underperforming pages; build
  topic clusters retroactively by establishing a pillar page with
  reciprocal links once enough content exists on a subject.
- **Pagination**: use real `<a href>` elements, never JS-only buttons or
  `onclick` handlers (crawlers struggle to execute JS reliably — see
  §1). Each paginated page should canonicalize to itself, never to page
  1, since paginated pages contain different content.
- **Crawler accessibility**: keep internal links dofollow by default.
  Reasonable exceptions: login pages, admin sections, and filter/facet
  URLs that would otherwise create duplicate-content URL bloat. Audit
  for accidental nofollow on internal links.

### Internal link auditing workflow

1. **Fix broken internal links**: find 4XX pages with internal
   references (site-crawl tooling); 301-redirect if the page has
   external backlinks, otherwise just remove/repoint the link.
2. **Find orphan pages**: pages with zero inbound internal links —
   prioritize fixing ones that already get organic traffic (via
   sitemap/external links) since internal linking can amplify existing
   performance.
3. **Find new internal-link opportunities**: keyword/topic-overlap
   analysis between existing pages can surface non-obvious, contextually
   relevant linking opportunities to important pages.

## 5. External linking

- Don't avoid linking out — external links to good sources (citations)
  help establish trustworthiness.
- `rel` attribute usage:
  - `nofollow` — for sources you don't trust or don't want to vouch for.
    Not meant to be applied blanket to every external link.
  - `sponsored` — for any paid/compensated link.
  - `ugc` — for user-generated content links (forum posts, comments,
    Q&A answers).

## Checklist

- [ ] All important links render as real `<a href="...">` markup (check
      rendered DOM for JS-inserted links).
- [ ] No links depend solely on `onclick` or `javascript:` hrefs.
- [ ] Anchor text is descriptive and makes sense out of context — no
      "click here" / "read more."
- [ ] No keyword-stuffed or excessively long anchor text; varied phrasing
      across multiple links to the same page.
- [ ] No unbroken chains of adjacent links.
- [ ] Linked images have descriptive `alt` text.
- [ ] Every important page has at least one internal inbound link (no
      orphan pages).
- [ ] Site structure keeps important pages within ~3 clicks of the
      homepage; breadcrumbs present.
- [ ] Priority links placed early/in-content, not buried in footer/deep
      sidebar.
- [ ] Pagination uses real `<a href>` links, each page self-canonicalized.
- [ ] Internal links are dofollow except login/admin/duplicate-filter
      URLs.
- [ ] No broken (4XX) internal links.
- [ ] Paid links marked `sponsored`; untrusted/UGC links marked
      `nofollow`/`ugc` as appropriate.

## Conflicting Evidence

- **Claim**: there is (or isn't) an ideal/target number of internal
  links per page.
  - Supported by (numeric target): [[ahrefs-internal-links-for-seo]]
    (2026-03-10) — "3-5 contextual links per article" as the "optimal"
    density, justified via a simplified PageRank-dilution argument.
  - Contradicted by: [[google-links-crawlable]] (Google Search Central,
    no date shown) — "There's no magical ideal number of links a given
    page should contain. However, if you think it's too much, then it
    probably is."
  - **Resolved (2026-07-07, user preference)**: defer to Google — no
    numeric cap. Google is the primary, ranking-authoritative source and
    deliberately avoids a numeric target, framing it as reader-judgment
    ("if you think it's too much, then it probably is") instead. Ahrefs'
    "3-5" is a third-party simplification and should not be treated as a
    rule to design content around. Link as much as genuinely serves the
    reader, including well beyond 5 links on longer/more comprehensive
    pages.

## See also

- [[how-google-search-works]] — links are how Google discovers URLs in
  the first place (crawling stage).
- [[traditional-seo-ranking-factors]] — backlinks as a classic ranking
  signal.
- [[classic-seo-ranking-factors]] — broader classic-SEO tactic list this
  playbook complements.
