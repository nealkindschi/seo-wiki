---
type: concept
tags: [seo]
updated: 2026-09-10
---

# Robots.txt Strategy: What It Is, What It Isn't

Robots.txt is a crawler-management tool that lives in your site root and tells search engines which URLs they *can* crawl. It is **not** a hiding mechanism, indexing control tool, or security barrier—a widespread misconception that leads to misuse.

## What robots.txt actually does

- **Manages crawler traffic**: Tells Googlebot (and other crawlers) which URLs to crawl, helping prevent server overload
- **Optimizes crawl allocation**: Directs crawler resources toward important content, away from duplicate/parameter pages
- **Controls media appearance**: Prevents images, videos, and audio from appearing in Google's image/video results
- **Reduces redundant crawling**: Keeps crawlers out of admin areas, staging sites, search results pages, test URLs, etc.

## File structure & syntax

- **Location**: Must be in site root: `domain.com/robots.txt` (not subdirectories)
- **Size limit**: ~500KB max (rarely an issue for most sites)
- **Format**: User-agent declarations followed by directives, one per line
- **Comments**: Use `#` for clarity; each comment on its own line

## User-agents (crawler targeting)

Robots.txt can target specific crawlers or all crawlers:

- **Googlebot** — Google's general search crawler
- **Googlebot-Image** — Google Image Search crawler (images only)
- **Bingbot** — Bing/Microsoft search crawler
- **Slurp** — Yahoo search crawler
- **Baiduspider** — Baidu (Chinese search engine)
- **DuckDuckBot** — DuckDuckGo crawler
- **`User-agent: *`** — Applies rules to all crawlers (wildcard, most common)

LLM/AI-chat products also publish their own user agents, distinct from
the training/indexing/retrieval bot taxonomy in
[[how-google-search-works]] — useful when deciding whether to allow or
block a specific LLM's crawler (per
[[wix-generative-engine-optimization]]):

| LLM | User agent |
|---|---|
| ChatGPT | `OAI-SearchBot`, `ChatGPT-User`, `GPTBot` |
| Copilot | `BingBot` |
| Gemini | `Google-Extended` (inferred — Google hasn't explicitly confirmed this maps to Gemini) |
| Claude | `ClaudeBot` |
| Perplexity | `PerplexityBot` |

These crawlers exist to help the LLM understand/summarize content
rather than to rank it — they generally don't need access to
navigation or pagination pages the way a ranking crawler benefits from;
prioritize their access to brand/product/service content instead.

Example targeting a specific crawler:
```
User-agent: Googlebot
Disallow: /admin/

User-agent: Bingbot
Disallow: /staging/

User-agent: *
Disallow: /private/
```

## Directives (core rules)

### Disallow
Prevents crawler access to a path:
```
Disallow: /admin/
Disallow: /staging/
Disallow: /temp/
```

### Allow
Permits access to subdirectories within a blocked path. Useful for granular control:
```
Disallow: /blog/
Allow: /blog/public-posts/
```
(Blocks everything in `/blog/` except `/blog/public-posts/`)

### Sitemap
References sitemap location for better discovery:
```
Sitemap: https://www.domain.com/sitemap.xml
Sitemap: https://www.domain.com/sitemap-news.xml
```

## Syntax gotchas

- **Trailing slashes matter**: 
  - `Disallow: /de/` blocks only the `/de/` directory
  - `Disallow: /de` blocks `/de/`, `/designer-dresses/`, `/delivery-info.html` — dangerous overgeneralization
- **Pattern matching**:
  - `*` = wildcard (matches anything)
  - `$` = end-of-string (exact match)
  - Example: `Disallow: /*?*` blocks all URLs with query parameters
- **One character misplaced** = SEO damage. Double-check trailing slashes and prefixes

## Subdomain strategy

Maintain separate robots.txt for each subdomain:
- `domain.com/robots.txt`
- `blog.domain.com/robots.txt`
- `staging.domain.com/robots.txt`

Each subdomain has its own root; robots.txt doesn't cascade.

## Critical misconception: robots.txt does NOT prevent indexing

**This is the #1 robots.txt mistake.** Even if a URL is blocked in robots.txt:
- Google can still index it if another website links to it (it indexes
  the URL without crawling the page)
- It may appear in search results (though "without a description," since Google can't access the page)
- It wastes your robots.txt directive

Example: You block `/admin/` in robots.txt. Another site links to `/admin/user123`. Google may still index that URL—robots.txt has no authority over incoming links.

### The "quick fix for duplicate content" version of this mistake

A widely repeated practitioner shortcut is to disallow duplicate or
thin pages in robots.txt to keep them out of the index. It's half
right: it does save crawl budget, which is a real benefit. It does not
control indexing, and it makes the situation worse — because Google
never fetches a disallowed page, it never sees a `noindex` on it, so
the block *prevents* the directive that would have worked. Per
[[google-robots-txt-intro]] (official) and [[ahrefs-robots-txt-guide]]
(which lists this among the common implementation mistakes), the rule
is: robots.txt for crawl management, `noindex` for indexing control,
and never both on the same URL.

This page carries no **Conflicting Evidence** section because no source
in this wiki argues the opposite — the disagreement is between official
guidance and folklore, not between sources.

### For actual indexing prevention, use:
1. **`noindex` meta tag** — Most reliable for HTML pages
2. **`X-Robots-Tag: noindex` HTTP header** — For PDFs, images, API responses
3. **Password protection** — Prevents crawling entirely (most secure)
4. **Content removal** — Delete the page from your server
5. **HTTPS + robots.txt** — Prevents Googlebot from seeing robots.txt (only for truly private content)

## What it can do by type

### HTML/PDF web pages
- Manage crawl traffic and server load
- Save crawl budget for canonical content
- **Cannot** hide from search results (if externally linked)

### Images/videos/audio
- Prevent from appearing in Google Image Search, Video Search results
- **Cannot** stop others from linking to them
- **Cannot** prevent Googlebot from discovering them via other sites' links

## Key limitations

1. **Not universal**: Not all crawlers respect robots.txt (bad actors, AI crawlers, etc.)
2. **Syntax interpretation varies**: Different crawlers may handle edge cases differently
3. **Linkage overrides it**: External backlinks can bypass your robots.txt rules
4. **No security value**: Google treats it as advisory only, not a security boundary
5. **Crawler still sees directives**: Googlebot still accesses robots.txt to read your rules (it's not hidden from crawlers)

## Empirical AI-assistant compliance data

Per [[ai-assistants-robots-txt-compliance-2026]] (controlled experiment,
10 AI assistants, HMAC-validated test pages, 200 trials) — hard data
behind limitation #1 above ("not all crawlers respect robots.txt...
AI crawlers"):

- **Compliance is assistant-specific, not a given.** Claude and Mistral
  respected robots.txt allow/disallow rules as expected in this test.
  DeepSeek, Gemini, Grok, and Qwen accessed disallowed pages regardless
  of the robots.txt rule.
- **Some assistants can't be targeted even if you wanted to.** Several
  exposed generic browser user-agents (Chrome/Safari strings) instead
  of an identifiable bot signature, making assistant-specific
  allow/disallow rules technically impossible to write — you can't
  target what your server logs can't distinguish.
- **What an assistant answers doesn't tell you what it accessed.**
  Copilot accessed all test pages in this study but returned no correct
  answers from them; ChatGPT sometimes answered without accessing
  allowed content at all. Don't infer crawl/access behavior from
  citation or answer behavior.
- **Access can continue well outside a visible interaction window** —
  Grok generated 173+ additional accesses to test pages in the weeks
  after the initial test, at 48-52x the expected per-trial request
  rate to a single page, a distinct load pattern from traditional
  crawling.
- Practical implication: treat robots.txt as one control among several
  (see "For actual indexing prevention" above), not as a reliable
  content-governance boundary against AI assistants specifically — a
  real risk of AI overview/agent access exists even for explicitly
  disallowed content, and it isn't reliably auditable from server logs
  alone when the assistant uses a generic user-agent.

## Related pages

- [[ai-assistants-robots-txt-compliance-2026]] — the per-assistant
  compliance data and attribution/access findings above.
- [[robots-txt-audit-checklist]] — Operational audit checklist with syntax rules, dangerous mistakes, GSC monitoring
- [[technical-seo-audit-checklist]] — Broader crawl/index/serve audit; robots.txt is one section
- [[how-google-search-works]] — Crawl stage and crawl budget allocation
- [[google-robots-txt-intro]] — Official Google guidance on robots.txt purpose and limitations
- [[ahrefs-robots-txt-guide]] — Practical implementation details, trailing-slash syntax gotchas, common mistakes
