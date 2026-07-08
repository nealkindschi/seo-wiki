# We Studied Over 1 Million Domains to Find the Most Common Technical SEO Issues

Source: https://ahrefs.com/blog/site-audit-study/
Author: Patrick Stox (reviewed by Joshua Hardwick)
Published: 2023-08-31
Fetched: 2026-07-08

## Methodology

1,002,165 domains analyzed via Ahrefs' Site Audit tool. Percentages
represent the share of domains where an issue was found on at least
one page, not the share of *pages* affected.

## Top 15 Issues by Domain Prevalence

1. 3XX redirect present — 95.2%
2. HTTP→HTTPS redirect present — 88%
3. Missing alt attributes — 80.4%
4. Meta description missing/empty — 72.9%
5. Slow page — 72.3%
6. Page/SERP title mismatch — 68.5%
7. Only one dofollow internal link to a page — 66.2%
8. Title too long — 63.2%
9. Links to a redirect (not the final URL) — 62.7%
10. H1 missing/empty — 59.5%
11. Meta description too short — 59.2%
12. Open Graph tags incomplete — 56%
13. Meta description too long — 54.5%
14. Multiple H1 tags — 51.3%
15. Meta description missing (on non-indexable pages) — 50.8%

## Issue-by-Issue Notes

- **Redirects (95.2%)**: near-universal and mostly benign; the real
  risk is redirect chains/loops. Google follows up to ~5 redirect hops
  per crawl session; chains beyond ~10 hops break signal
  consolidation (e.g. link equity) to the final URL.
- **HTTPS migration (88%)**: broad HTTPS adoption is a positive sign,
  but over 6% of sites have a broken HTTPS→HTTP redirect running in
  the wrong direction. Mixed-content issues from incomplete HTTPS
  migrations are usually fixable via a Content Security Policy rather
  than manual per-page updates.
- **Missing alt attributes (80.4%)**: framed as both an accessibility/
  legal risk (ADA-compliance lawsuits) and a minor SEO factor — alt
  text counts as page text and matters for image search, but its
  direct ranking impact is often overstated.
- **Meta descriptions (72.9% missing/empty, 59.2% too short, 54.5%
  too long)**: not a direct ranking factor. Google rewrites meta
  descriptions in the SERP roughly 62.78% of the time regardless of
  what's written. Recommendation: write good meta descriptions only
  for high-traffic pages or pages with a distinct selling proposition
  worth controlling — don't mass-fix the whole site.
- **Slow pages (72.3%)**: recommends enabling Core Web Vitals checks
  in the crawl config; distinguishes lab data (Lighthouse, synthetic)
  from field data (Core Web Vitals/CrUX, real Chrome users) — Ahrefs
  pulls the latter via the PageSpeed Insights API.
- **Title tags (68.5% SERP mismatch, 63.2% too long)**: title tags
  remain an actual ranking factor and Google ranks against the full
  tag text, not the truncated SERP display — prioritize fixing titles
  on pages that already get meaningful search traffic. Mobile SERPs
  typically show longer titles than desktop.
- **Internal links (66.2% with only one dofollow internal link)**: a
  contextual-linking opportunity-finder approach is recommended —
  identify other pages ranking for related keywords and add links from
  there.
- **H1 tags (59.5% missing, 51.3% multiple)**: a missing H1 is
  considered a minor issue; multiple H1s have been valid HTML5 since
  2014 and Google has stated this isn't a problem.
- **Open Graph tags (56% incomplete)**: not an SEO ranking factor
  directly; relevant only for pages that get shared on social
  platforms, where it affects click-through/shareability rather than
  ranking.

## Prioritization Framework

Recommends an impact-effort matrix: estimate each fix's likely impact
and the development effort required, and prioritize high-impact/
low-effort fixes first. Explicitly notes that sometimes the right call
is to do nothing, when a fix's cost outweighs its likely benefit —
prevalence in this dataset indicates commonality, not priority; every
site needs its own priority assessment rather than fixing issues in
frequency order.
