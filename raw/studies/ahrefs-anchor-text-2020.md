# Anchor Text: A Data-Driven Guide

Source: https://ahrefs.com/blog/anchor-text/
Author: Joshua Hardwick (reviewed by Sam Oh, Si Quan Ong)
Published/Updated: 2020-04-03
Fetched: 2026-07-08

## Scope

Covers backlink (external, inbound) anchor text specifically —
distinct from internal-linking anchor text already covered elsewhere
in the wiki. Anchor text types defined: exact match, phrase match,
partial match, branded, naked URL, random/generic ("click here"), and
image-link (alt-text-derived).

## Study 1: Anchor Text Type vs. Ranking Correlation

384,614 pages across 19,840 keywords. Spearman correlation between
anchor-text-type presence in a page's backlink profile and ranking:

- Exact-match anchors: 0.1436 avg / 0.1869 median — weak correlation.
- Phrase-match anchors: 0.1057 avg / 0.1393 median — very weak.
- Partial-match anchors: 0.1076 avg / 0.1393 median — very weak.
- Random anchors: 0.0161 avg / 0.0130 median — effectively no
  correlation.

## Study 2: Surrounding Link-Text Context

16,000 pages with random (non-keyword) anchor text, examining whether
keyword-relevant words *around* the link (not the anchor text itself)
correlate with ranking:

- Exact-match phrase in surrounding text: 0.0640 — no notable effect.
- Partial-match words in surrounding text: 0.0205 — almost zero.
- 1+ query words present in surrounding text: -0.0701 — effectively no
  correlation (slightly negative).

## Why Traditional Keyword-Anchor Strategy Doesn't Hold Up

- **Topics beat single keywords**: on average, only ~22% (about 1/5)
  of a page's organic traffic comes from its single main target
  keyword — most traffic comes from long-tail variations Google
  matches via improved natural-language understanding (attributed to
  post-Hummingbird algorithm improvements), so optimizing anchor text
  for one exact keyword undersells how pages actually rank.
- **Legitimate keyword-rich anchor links are hard to earn**: building
  a meaningful volume of exact-match-anchor backlinks through
  above-board means is difficult; doing so at scale typically requires
  manipulative tactics (e.g. private blog networks).
- **The correlation data itself is weak** across every anchor-text
  type studied, undermining the premise that anchor text optimization
  meaningfully moves rankings today.

## Core Recommendation

Don't try to manipulate anchor text ratios in a backlink profile at
all — let it occur naturally as external sites link to you in their
own words. This is framed as both the safest and most effective
approach, since natural link building (the only truly "white hat"
path) provides limited control over anchor text anyway. The one
partial exception is guest blogging, where a branded or generic anchor
should be chosen deliberately over a keyword-rich one, to avoid
looking manipulated.

## Historical Context

Google's original 1998 PageRank paper described anchor text as often
giving "more accurate descriptions of web pages than the pages
themselves" — a foundational reason search engines weighted it
heavily early on. This weighting created a manipulation incentive,
which Google's 2012 Penguin update specifically targeted (aimed at
sites "overly aggressive" with exact-match anchor backlinks),
initially affecting about 3.1% of search queries; subsequent Penguin
iterations continued refining anchor-text-spam detection.

## Acknowledged Limitation

The study authors note a structural flaw: at the scale of 384,614
pages, there's no reliable way to determine each page's single
"primary" target keyword, especially since individual pages often rank
for hundreds or thousands of query variations — introducing inherent
noise/bias into any single-keyword correlation analysis like this one.
