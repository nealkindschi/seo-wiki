# Ahrefs: Robots.txt and SEO Implementation Guide

Source: https://ahrefs.com/blog/robots-txt/

## What It Is

A robots.txt file provides instructions to search engines about which areas of your website they can and cannot access. It's a simple text file placed in your site's root directory that controls crawler behavior.

## Critical Syntax Rules

**File Structure:**
- Place in root directory: `domain.com/robots.txt`
- Use new lines for each directive
- Format: User-agent declaration followed by directives
- Maximum file size: approximately 500 kilobytes

**User-Agents:**
Common search engine identifiers include Googlebot, Googlebot-Image, Bingbot, Slurp, Baiduspider, and DuckDuckBot. Use the wildcard (*) to apply rules to all bots.

## Supported Directives

**Disallow:** Prevents access to specific paths
```
User-agent: *
Disallow: /admin/
```

**Allow:** Permits crawling of subdirectories within otherwise restricted areas
```
Disallow: /blog/
Allow: /blog/public-post/
```

**Sitemap:** Specifies sitemap location
```
Sitemap: https://www.domain.com/sitemap.xml
```

## Best Practices

- Use trailing slashes for specificity: `/de/` blocks only that directory, not pages beginning with `/de`
- Apply wildcards and "$" symbols for pattern matching
- Include comments using # for clarity
- Declare each user-agent once to avoid confusion
- Maintain separate robots.txt files for each subdomain

## Common Mistakes to Avoid

One character out of place can damage SEO performance. The most dangerous error is unintentionally blocking important pages through overly broad directives. For example, `Disallow: /de` would block `/designer-dresses/` and `/delivery-information.html`.

## Important Limitations

Robots.txt cannot guarantee exclusion from search results. Content linked from external sites may still appear in Google search results even if blocked via robots.txt. To truly prevent indexing, use meta robots tags or x-robots HTTP headers instead.

## Auditing Tools

Google Search Console's Coverage report and URL Inspection tool reveal robots.txt blocking issues. Watch for errors like:
- Submitted URLs blocked by robots.txt
- Indexed content that's blocked by robots.txt

These require investigation and adjustment to align robots.txt with your indexing goals.
