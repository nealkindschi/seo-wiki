# Google Images and Google Search

Source: https://developers.google.com/search/docs/appearance/google-images

## How Google Images Works
Google discovers images through multiple channels including text results, Google Discover, and the Images tab. It uses computer vision algorithms and page context to understand image subject matter.

## Core Technical Requirements
- Supported file formats when referenced in `<img src>`: BMP, GIF, JPEG, PNG, WebP, SVG, AVIF.
- Use standard HTML `<img>` elements (including inside `<picture>`) — Google does not index CSS background images.
- Submit an image sitemap to surface images Google might not otherwise discover, including images hosted on other-domain CDNs.

## Responsive Images
Use `srcset` or `<picture>` for responsive design, always with a fallback `src` — some browsers/crawlers don't understand those attributes.

## Landing Page Optimization
- Specify a preferred image via `schema.org` `primaryImageOfPage` or `og:image` meta tags. Avoid generic images, extreme aspect ratios, generic logos.
- Follow standard title-link/snippet guidelines — they influence how images appear in results.
- Structured data can make images eligible for rich results/badges in Google Images, requiring image properties as mandatory fields.

## Descriptive Elements
- Filenames: short and descriptive (e.g. "my-new-black-kitten.jpg" not generic IDs).
- Alt text: "the most important attribute" for image metadata — informative, no keyword stuffing (e.g. "Dalmatian puppy playing fetch").
- Placement: position images near topically relevant text.

## Performance & Quality
High-quality photos outperform blurry/unclear ones. Compress for speed without sacrificing visual quality; test with PageSpeed Insights.

## Dos and Don'ts
DO: semantic `<img>` tags, descriptive contextual alt text, image sitemaps, responsive images with fallbacks, high-resolution images.
DON'T: rely on CSS background images, generic filenames, keyword-stuffed alt text, extreme aspect ratios in metadata, omit alt text entirely.

## SafeSearch
Ensure Google understands site content nature so SafeSearch filters apply appropriately.
