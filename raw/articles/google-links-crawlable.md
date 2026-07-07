# Make links crawlable

Source: https://developers.google.com/search/docs/crawling-indexing/links-crawlable
Fetched: 2026-07-07

## Overview
Google uses links to determine page relevancy and discover new pages for crawling. The guidance covers making links crawlable and improving anchor text for both users and search engines.

## Making Links Crawlable

### Required HTML Format
Google primarily crawls links formatted as `<a>` HTML anchor elements with `href` attributes. The documentation states: "Google can only crawl your link if it's an `<a>` HTML element with an `href` attribute."

**Google Can Parse:**
- `<a href="https://example.com">`
- `<a href="/products/category/shoes">`
- `<a href="./products/category/shoes">`
- `<a href="/products/category/shoes" onclick="javascript:goTo('shoes')">`
- `<a href="/products/category/shoes" class="pretty">`
- Dynamically inserted links using proper HTML markup with JavaScript

**Google Cannot Reliably Parse:**
- `<a routerLink="products/category">` (framework-specific routing)
- `<span href="https://example.com">` (non-anchor elements)
- `<a onclick="goto('https://example.com')">` (onclick-only links)

### URL Resolution Requirements
The href attribute must contain an actual web address resembling a URI that Google crawlers can request.

**Resolvable URLs (Recommended):**
- `<a href="https://example.com/stuff">`
- `<a href="/products">`
- `<a href="/products.php?id=123">`

**Non-Resolvable URLs (Not Recommended):**
- `<a href="javascript:goTo('products')">`
- `<a href="javascript:window.location.href='/products'">`

## Anchor Text Placement and Content

### Definition and Placement
Anchor text is visible link text communicating to users and Google what the linked page covers. It must appear between `<a>` elements that Google can crawl.

**Good Example:**
`<a href="https://example.com/ghost-peppers">ghost peppers</a>`

**Bad Example (Empty Link Text):**
`<a href="https://example.com"></a>`

### Fallback Mechanisms
When anchor text is empty, Google can use the `title` attribute as fallback: `<a href="https://example.com/ghost-pepper-recipe" title="how to pickle ghost peppers"></a>`

For image links, Google uses the `alt` attribute of the `img` element as anchor text. The guidance recommends "add descriptive alt text to your images."

**Good Image Link:**
`<a href="/add-to-cart.html"><img src="enchiladas-in-shopping-cart.jpg" alt="add enchiladas to your cart"/></a>`

**Bad Image Link (Empty Attributes):**
`<a href="/add-to-cart.html"><img src="enchiladas-in-shopping-cart.jpg" alt=""/></a>`

### JavaScript-Inserted Anchor Text
Use the URL Inspection Tool to verify anchor text appears in rendered HTML when inserted via JavaScript.

## Writing Quality Anchor Text

### Core Principles
Good anchor text should be "descriptive, reasonably concise, and relevant to the page that it's on and to the page it links to." The text provides context and sets reader expectations.

**Test**: "Try reading only the anchor text (out of context) and check if it's specific enough to make sense by itself."

### Avoid Generic Anchor Text
**Poor Examples:**
- `<a href="https://example.com">Click here</a> to learn more.`
- `<a href="https://example.com">Read more</a>.`
- Learn more about our cheese on our `<a href="https://example.com">website</a>.`
- We have an `<a href="https://example.com">article</a>` that provides more background on how the cheese is made.

**Better Examples:**
- For a full list of cheese available for purchase, see the `<a href="https://example.com">list of cheese types</a>.`

### Avoid Excessive Length
**Poor Example (Weirdly Long):**
Starting next Tuesday, the `<a href="https://example.com">Knitted Cow invites local residents of Wisconsin to their grand re-opening by also offering complimentary cow-shaped ice sculptures</a>` to the first 20 customers.

**Better (More Concise):**
Starting next Tuesday, the `<a href="https://example.com">Knitted Cow invites local residents of Wisconsin</a>` to their grand re-opening by also offering complimentary cow-shaped ice sculptures to the first 20 customers.

### Keyword Considerations
Write "as naturally as possible, and resist the urge to cram every keyword that's related to the page." Keyword stuffing violates spam policies. Ask: "Does the reader need these keywords to understand the next page?"

### Link Spacing and Context
Surrounding words matter. Avoid chaining multiple links together — it's harder for readers to distinguish between links and loses contextual text for each.

**Poor (Too Many Adjacent Links):**
I've written about cheese `<a href="https://example.com/page1">so</a>` `<a href="https://example.com/page2">many</a>` `<a href="https://example.com/page3">times</a>` `<a href="https://example.com/page4">this</a>` `<a href="https://example.com/page5">year</a>.`

**Better (Spaced with Context):**
I've written about cheese so many times this year: who can forget the `<a href="https://example.com/blue-cheese-vs-gorgonzola">controversy over blue cheese and gorgonzola</a>`, the `<a href="https://example.com/worlds-oldest-brie">world's oldest brie</a>` piece that won the Cheesiest Research Medal, the epic retelling of `<a href="https://example.com/the-lost-cheese">The Lost Cheese</a>`, and my personal favorite, `<a href="https://example.com/boy-and-his-cheese">A Boy and His Cheese: a story of two unlikely friends</a>`.

## Internal Links: Cross-Referencing Content

The guidance emphasizes internal linking strategy: "Every page you care about should have a link from at least one other page on your site." Consider what resources on your site help readers understand a given page and link contextually.

**Caveat on Link Volume**: "There's no magical ideal number of links a given page should contain. However, if you think it's too much, then it probably is."

## External Links: Linking to Other Sites

### Building Trustworthiness
"Linking to other sites isn't something to be scared of; in fact, using external links can help establish trustworthiness (for example, citing your sources)."

**Good Example (Citing Sources):**
According to a recent study from Swiss researchers, Emmental cheese wheels that were exposed to music had a milder flavor when compared to the control cheese wheels (which experienced no such musical treatment), with the full findings available in `<a href="https://example.com">Cheese in Surround Sound—a culinary art experiment</a>`.

### Link Qualification with Rel Attributes
Use `nofollow` only "when you don't trust the source, and not for every external link on your site."

**When to Use `nofollow`**: Disagreeing with a source and not wanting to transfer reputation through the link.

**When to Use `sponsored`**: Links you've been paid for in any way.

**When to Use `ugc`**: User-generated content (forums, Q&A sites) where users can insert links.
