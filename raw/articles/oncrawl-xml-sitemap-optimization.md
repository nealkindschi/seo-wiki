# XML Sitemap Optimization for SEO

Source: https://www.oncrawl.com/technical-seo/optimize-xml-sitemap/

## What Are XML Sitemaps?

XML sitemaps are files that list URLs for search engines like Google, Bing, and Yahoo to discover and crawl. They can include metadata about each URL such as modification dates and priority levels.

## Why They Matter

According to Google's analysis, approximately "80% of discovery is following links, close to 20% is just following Sitemaps." Sitemaps help ensure important pages receive proper crawl attention and make efficient use of your crawl budget—the number of URLs Googlebot can and wants to index.

## Key Optimization Strategies

**1. Follow the Sitemaps Protocol**
Ensure your XML follows standard requirements: opening/closing `<urlset>` tags, proper namespace declarations, and `<url>` entries with `<loc>` child tags.

**2. Organize by Site Section**
Create separate sitemap index files for different website sections (products, blog, directories) to monitor valid and excluded URLs through Google Search Console.

**3. Include Only Money Pages**
List only URLs that provide SEO value and should be indexed and ranked—pages that drive business results.

**4. Maintain Proper HTTP Status Codes**
Exclude URLs returning non-200 responses; including them wastes crawl budget.

**5. Exclude Noindexed URLs**
Don't include pages marked with noindex tags, as they won't generate search traffic.

**6. Avoid Canonicalized URLs**
Exclude URLs that redirect to other pages, as they shouldn't compete for rankings.

## Implementation
Submit sitemaps to Google Search Console and Bing Webmaster Tools to monitor errors and crawl data.
