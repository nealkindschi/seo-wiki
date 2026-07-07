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
the linked page is about. Based on [[google-links-crawlable]].

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
  [[how-google-search-works]]'s URL-discovery step).
- No magic ideal link count per page — but "if you think it's too much,
  then it probably is."
- Link contextually: point to resources on the site that actually help
  the reader understand the current page.

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
- [ ] No keyword-stuffed or excessively long anchor text.
- [ ] No unbroken chains of adjacent links.
- [ ] Linked images have descriptive `alt` text.
- [ ] Every important page has at least one internal inbound link.
- [ ] Paid links marked `sponsored`; untrusted/UGC links marked
      `nofollow`/`ugc` as appropriate.

## See also

- [[how-google-search-works]] — links are how Google discovers URLs in
  the first place (crawling stage).
- [[traditional-seo-ranking-factors]] — backlinks as a classic ranking
  signal.
- [[classic-seo-ranking-factors]] — broader classic-SEO tactic list this
  playbook complements.
