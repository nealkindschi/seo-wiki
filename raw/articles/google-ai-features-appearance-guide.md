# AI Features and Your Website - Google Search Central

Source: https://developers.google.com/search/docs/appearance/ai-features
Last updated (per page): 2025-12-10 UTC
Fetched: 2026-07-07

## Overview

Google's guide explains that AI features like AI Overviews and AI Mode
function within Search results. The document clarifies that "there are
no additional requirements to appear in AI Overviews or AI Mode, nor
other special optimizations necessary."

## How AI features work in Search

**AI Overviews** help users quickly understand complex topics and
provide links for deeper exploration. Google notes these features "show
up on queries where they can add additional benefits beyond what people
might already get on Search."

**AI Mode** assists with queries requiring "further exploration,
reasoning, or complex comparisons." The system enables users to ask
nuanced questions that previously required multiple searches.

Both features may employ "query fan-out" techniques — issuing multiple
related searches across subtopics — to develop comprehensive responses
while displaying "a wider and more diverse set of helpful links" than
traditional search.

## Appearing in AI features

### Technical requirements

Pages must meet standard Google Search technical requirements: be
indexed and eligible for snippets. The document states: "there are no
additional technical requirements" beyond standard Search eligibility.

### SEO best practices

Recommended practices include:
- Allowing crawling via robots.txt
- Using internal links for discoverability
- Providing excellent page experience
- Offering textual content
- Supporting content with quality images and videos
- Ensuring structured data matches visible text
- Maintaining current Merchant Center and Business Profile information

Notably, "you don't need to create new machine readable files, AI text
files, or markup to appear in these features."

## Measuring performance

Traffic from AI features appears in Search Console's Performance report
under the "Web" search type. Google indicates "clicks from search
results pages with AI Overviews" show higher quality engagement.

## Controlling content inclusion

Site owners can use existing controls: `robots.txt` directives for
Googlebot, `nosnippet`, `data-nosnippet`, `max-snippet`, or `noindex`
tags to limit content appearance in these features.
