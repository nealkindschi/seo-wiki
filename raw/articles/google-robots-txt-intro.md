# Google: Robots.txt Introduction

Source: https://developers.google.com/search/docs/crawling-indexing/robots/intro

## What It Is

A robots.txt file is a text file placed in a website's root directory that communicates with search engine crawlers about which URLs they can access. As Google states: "A robots.txt file tells search engine crawlers which URLs the crawler can access on your site."

## Primary Purpose

The file manages crawler traffic to prevent server overload. Importantly, it's **not** a security or privacy tool. Google emphasizes: "it is not a mechanism for keeping a web page out of Google."

## What It Can and Cannot Do

**For Web Pages (HTML, PDFs):**
- Manages crawling traffic to prevent server strain
- Helps avoid indexing redundant or unimportant content
- Does NOT hide pages from search results

**For Media Files:**
- Can prevent images, videos, and audio from appearing in Google results
- Won't stop others from linking to these files

**Critical Limitation:**
Even if blocked in robots.txt, a URL can still appear in search results if other websites link to it. Google notes that blocked pages may show "without a description" in results.

## Key Misconceptions

Google warns against using robots.txt as a hiding mechanism. To actually prevent indexing, webmasters should use password protection, the `noindex` meta tag, or remove content entirely.

## Limitations to Know

- Not all crawlers respect robots.txt rules
- Different crawlers may interpret syntax differently
- Blocked pages can still be indexed if externally linked

For actual privacy protection, Google recommends password-protecting sensitive files on your server instead.
