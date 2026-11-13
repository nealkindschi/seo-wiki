---
type: playbook
tags: [seo, aeo]
updated: 2026-11-12
---

# Google Search Traffic Attribution (Analytics & Server Logs)

Why / when to use this: use when organic Google traffic looks wrong in
analytics (too low, showing as direct or referral), when building
log-based reporting, or when someone asks why GA4 doesn't match Search
Console. Based on Google's own documentation
([[google-identify-search-traffic]]).

## How Google Search referrers work

- Google sends the `Referer` header with the **`origin` policy**:
  scheme and host only (`https://www.google.com/`). No path, no query.
- **No keyword data in the referrer, ever.** Queries come only from
  Search Console's Performance report.
- Search, Discover, Google Images, and (by inference) AI Overviews and
  AI Mode all share the same Google origins, so the referrer can't
  tell them apart. Use Search Console's search-type filters for that
  split (see [[controlling-ai-feature-inclusion]] on AI features being
  reported under "Web").

## Values to match

| Source | `Referer` |
|---|---|
| Web | `https://www.google.com/` or any local Google domain (`google.co.uk`, `google.co.jp`, …) |
| Google app, Android | `android-app://com.google.android.googlequicksearchbox/https/www.google.com`, or the web values |
| Google app, iOS | the web values |

For log analysis, match the host against `www.google.<tld>` (including
two-part ccTLDs like `.co.uk`) plus the Android app string. Don't hard-code
only `google.com`.

## Checklist

- [ ] Analytics channel grouping classifies all the values above as
      organic search. Check custom channel rules, referral exclusions,
      and filters if Google traffic shows up as referral or direct.
- [ ] Log analysis counts **landing-page requests only**. Subresource
      requests (images, CSS, JS) carry your own page as referrer and
      will inflate counts if included.
- [ ] Redirect audit: no JS or `meta refresh` redirects on organic
      landing pages (they overwrite the referrer with your URL). Use
      server-side 301/302 instead. See [[technical-seo-audit-checklist]].
- [ ] Redirects preserve the query string, so `gclid` and UTM
      parameters survive.
- [ ] No stricter `Referrer-Policy` (e.g. `no-referrer`) is set on
      redirect hops that would strip the inbound referrer.
- [ ] Reports that compare analytics to Search Console label the gap as
      expected, with these causes: blocked or consent-gated tracking,
      clicks that never finish loading the page, blank referrers
      (private browsing, new tabs, mobile widgets, privacy extensions),
      and paid traffic mixed into analytics totals (Search Console is
      organic-only).
- [ ] Analytics totals for "Google organic" exclude Google Ads traffic
      before comparing with Search Console clicks.

## What this can't tell you

- Which query drove a visit (use Search Console).
- Whether a visit came from Search, Discover, Images, or an AI feature.
- Whether an AI assistant prompted the search. Visits where someone
  got a recommendation in ChatGPT and then searched the brand on Google
  arrive with a normal Google referrer and count as branded organic
  ([[similarweb-downstream-impact-of-ai-visibility-2026]], discussed in
  [[aio-ctr-impact]]).

## See also

- [[seo-reporting]] — where reconciled organic numbers get reported.
- [[ai-traffic-scale-vs-hype]] — why search attribution looks cleaner
  than it is.
