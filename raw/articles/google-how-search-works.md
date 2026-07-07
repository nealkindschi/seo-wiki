# How Google Search Works

Source: https://developers.google.com/search/docs/fundamentals/how-search-works
Last updated (per page): 2025-12-18 UTC
Fetched: 2026-07-07

## Introduction

"Google Search is a fully-automated search engine that uses software
known as web crawlers that explore the web regularly to find pages to
add to our index." The vast majority of pages in search results are
found automatically rather than manually submitted. Google does not
accept payment for more frequent crawling or higher rankings, and
"Google doesn't guarantee that it will crawl, index, or serve your page,
even if your page follows the Google Search Essentials."

## Three stages

1. **Crawling**: "Google downloads text, images, and videos from pages
   it found on the internet with automated programs called crawlers."
2. **Indexing**: "Google analyzes the text, images, and video files on
   the page, and stores the information in the Google index, which is a
   large database."
3. **Serving search results**: "When a user searches on Google, Google
   returns information that's relevant to the user's query."

## Crawling

- **URL discovery**: since there's no central registry of web pages,
  Google discovers URLs via previously-visited pages, links found on
  known pages, and submitted sitemaps.
- **The crawling process**: "We use a huge set of computers to crawl
  billions of pages on the web. The program that does the fetching is
  called Googlebot." Googlebot algorithmically decides which sites to
  crawl, how often, and how many pages per site — and adjusts crawl
  speed to avoid overloading a site (including responding to HTTP 500
  errors as a "slow down" signal).
- **JavaScript rendering**: "During the crawl, Google renders the page
  and runs any JavaScript it finds using a recent version of Chrome...
  Rendering is important because websites often rely on JavaScript to
  bring content to the page, and without rendering Google might not see
  that content."
- **Common crawling issues**: server problems, network issues, or
  robots.txt rules blocking access. Some discovered pages are never
  crawled — disallowed by robots.txt, or requiring login.

## Indexing

- **Content analysis**: "Google tries to understand what the page is
  about... processing and analyzing the textual content and key content
  tags and attributes, such as title elements and alt attributes,
  images, videos, and more."
- **Canonicalization**: Google clusters pages with duplicate/similar
  content, selects the most representative page as canonical, and may
  still use alternate versions for specific contexts (mobile, certain
  searches).
- **Signal collection**: language, geographic relevance, and page
  usability are collected as signals on the canonical page for later use
  in serving.
- **Storage**: canonical page + cluster information is stored in the
  Google index, "a large database hosted on thousands of computers."
- **Indexing isn't guaranteed**: "not every page that Google processes
  will be indexed." Common causes: low quality content, robots meta
  rules disallowing indexing, or crawling-unfriendly site design.

## Serving search results

- **No pay-for-rank**: "Google doesn't accept payment to rank pages
  higher, and ranking is done programmatically."
- **Relevancy factors**: "hundreds of factors," including user location,
  language, and device.
- **Context-specific results**: e.g., "bicycle repair shops" shows
  different results in Paris vs. Hong Kong.
- **Search feature variation by query type**: "bicycle repair shops"
  triggers local results and no image results; "modern bicycle" triggers
  image results but not local results.
- **Indexed but not ranking**: a page can appear indexed in Search
  Console yet not appear in results because it's irrelevant to the
  query, low quality, or blocked from serving by robots meta rules.

## Continuous improvement

"While this guide explains how Search works, we are always working on
improving our algorithms. You can keep track of these changes by
following the Google Search Central blog."
