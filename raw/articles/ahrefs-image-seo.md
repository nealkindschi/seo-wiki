# Image SEO: 12 Actionable Tips

Source: https://ahrefs.com/blog/image-seo/
Author: Joshua Hardwick (Head of Content @ Ahrefs)
Updated: 2020-10-28

## 12 Recommendations
1. **Name images appropriately** — descriptive filenames ("chocolate-cheesecake.jpg" not "IMG00023.JPG"), no keyword stuffing. Google: "filename can give Google clues about the subject matter."
2. **Write descriptive alt text & captions** — formula: complete "This is a(n) ___ of ___" and use as alt text; include product numbers for product images; add captions where possible.
3. **Choose optimal file type** — JPEG for photos, PNG for line drawings/text/icons, GIF for animation; prioritize file-size reduction while maintaining quality.
4. **Resize images to site dimensions** — upload at max display width only.
5. **Reduce file size** — Google: "don't be afraid to dial down quality." Compression tool comparison (default settings): ImageOptim 69% (JPEG)/40% (PNG), ShortPixel 42%/59%, TinyPNG 27%/65%. Optionally preserve EXIF data for local SEO.
6. **Create image sitemaps** — use `<image:loc>`, `<image:title>`, `<image:caption>` tags; Yoast SEO automates for WordPress; CDN-hosted images can be included despite cross-domain restrictions.
7. **Use vector graphics (SVG)** — for logos/icons/simple shapes; minify and GZIP-compress (example: 8.54kb → 3.56kb, 41.67% reduction).
8. **Serve responsive images** — `srcset` attribute; WordPress 4.4+ auto-generates sizes.
9. **Utilize schema markup** — recipes/products/videos enable badges in Google mobile image search, improving CTR.
10. **Consider lazy loading** — defer below-the-fold image loading; recommended by PageSpeed Insights; WordPress: A3 Lazy Load.
11. **Leverage browser caching** — HTTP caching speeds repeat visits; WordPress: W3 Total Cache; non-WordPress: expiration headers in .htaccess.
12. **Use a CDN** — Cloudflare, KeyCDN, AWS CloudFront, Google Cloud CDN; use CNAME records (e.g. cdn.yourdomain.com) to preserve SEO value; image CDNs (Cloudinary, imgix) automate optimization.

## Bonus: Link Equity Recovery
Identify backlinks pointing directly to image files (.jpg/.png/.gif) via Site Explorer; outreach to request the link point to the source article instead — reportedly high conversion on this outreach.

## Key Evidence
- Google Cloud Vision API: near-perfect on cat photos, failed to distinguish butter from cheese (91% confidence) — cited as evidence alt text still matters despite ML image understanding.
- Ahrefs Site Audit identifies missing alt text and compressible images.

## Dos and Don'ts
DO: descriptive filenames/alt text, right file type per content, aggressive compression, responsive images, captions, minified/GZIP SVG, link-equity recovery outreach.
DON'T: keyword-stuff filenames/alt text, upload oversized images, skip compression, skip alt text relying on ML, use low-quality stock photos, link directly from CDN URLs, skip browser caching.
