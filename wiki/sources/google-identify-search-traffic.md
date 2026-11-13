---
type: source
tags: [seo]
date_ingested: 2026-11-12
origin: raw/articles/google-identify-search-traffic.md
---

# Identify Google Search traffic in your web analytics or server logs (Google)

**Citation:** Google Search Central, "Identify Google Search traffic in
your web analytics or server logs" (official developer documentation).
https://developers.google.com/search/docs/monitor-debug/identify-google-search-traffic
No publish or last-updated date on the fetched page, so no timeline entry.

## Key takeaways

- **Google Search sends a `Referer` using the `origin` referrer policy**:
  scheme and host only, no path, no query string. The search query is
  never in the referrer; use Search Console's Performance report for
  queries.
- **Exact referrer values to match:**

  | Source | `Referer` value |
  |---|---|
  | Google Search on the web | `https://www.google.com/` or a local Google domain (`https://www.google.co.uk/`, `https://www.google.co.jp/`) |
  | Google app on Android | `android-app://com.google.android.googlequicksearchbox/https/www.google.com` (link opened in a browser tab), or `https://www.google.com/` / local domain |
  | Google app on iOS | `https://www.google.com/` or a local Google domain |

- **Discover** traffic carries the same values as the surface it was
  viewed on (Google app or web). **Google Images** and other Google
  services on the same origins send the same values, so matching these
  patterns includes them. You can't separate Search from Discover or
  Images by referrer alone.
- **Blank referrers are expected** in some cases: private browsing and
  anti-fingerprinting, opening results in a new tab (some browsers),
  native mobile search widget → external browser, privacy extensions or
  strict settings. JS-based trackers also miss visits through consent
  management and ad blockers.
- **Matching in practice:** most analytics tools already bucket these
  as organic Google. If they land in referral or direct, check custom
  channel rules, referral exclusions, and filters. In logs, count only
  landing-page requests; subresource requests (images, CSS, JS) carry
  your own page URL as referrer.
- **Why numbers won't match Search Console:**
  - Privacy settings and client configs (blocked scripts, stripped
    parameters, suppressed referrer).
  - **Your own redirects**: JS or `meta refresh` redirects replace the
    referrer with your URL; redirects that drop the query string lose
    `gclid`; a stricter `Referrer-Policy` on the redirect can strip the
    referrer entirely.
  - Different measurement points: Search Console counts the click;
    analytics counts only after the page loads and tracking runs.
  - Search Console is organic-only; analytics may mix in Google Ads
    traffic depending on configuration.

## Inference (not stated by the source)

The page doesn't mention AI Overviews or AI Mode. Both are served on
google.com, so clicks from them should carry the same `origin`
referrer as classic results, making them indistinguishable in
analytics or logs. That fits [[google-ai-features-appearance-guide]],
which says AI-feature traffic is folded into Search Console's "Web"
search type. Treat this as a reasonable inference, not documented
behavior.

## Created / updated

- Created [[google-search-traffic-attribution]] (playbook: referrer
  matching, blank-referrer causes, Search Console reconciliation
  checklist).
- Updated [[seo-reporting]] with a reconciliation note and link.
- Updated [[aio-ctr-impact]]'s Similarweb attribution caveat: the
  referrer mechanics explain why AI-prompted branded searches look like
  ordinary organic Google traffic.
