# Why ChatGPT Cites One Page Over Another (Study of 1.4M Prompts)

Source: https://ahrefs.com/blog/why-chatgpt-cites-pages/
Authors: Louise Linehan, Xibeijia Guan (reviewed by Ryan Law)
Published: 2026-04-15
Fetched: 2026-07-08

## Methodology

1.4 million ChatGPT prompts, February 2025, ChatGPT 5.2 desktop.
Semantic relevance approximated via cosine similarity on open-source
embeddings, comparing prompt text (and ChatGPT's internal fanout
queries) against retrieved-URL titles. Quantitative analysis by data
scientist Xibeijia Guan. Care taken to segment analysis by reference
type (`ref_type`) rather than aggregate cited-vs-non-cited comparisons,
since aggregate comparisons confound source-specific retrieval
mechanics with genuine selection signals.

## Overall Citation Rate

ChatGPT cites roughly half of the URLs it retrieves (49.98% cited vs.
50.02% not cited). The system uses lightweight retrieval metadata
(title, snippet, URL, ID) to decide which pages are worth opening
before it reads full page content.

## Citation Rate by Source Type

| Source Type | Citation Rate | Data Points |
|---|---|---|
| Search | 88.46% | 25.6M |
| News | 12.01% | 3.9M |
| Reddit | 1.93% | 16.2M |
| YouTube | 0.51% | 953K |
| Academia | 0.40% | 185K |

Search-index results dominate: about 88% of all ChatGPT citations come
directly from the search index reference type.

## Reddit's Hidden Influence

Reddit makes up 67.8% of all non-cited URLs — ChatGPT retrieves Reddit
content extensively to build context and gauge consensus, but rarely
cites it directly. Functions as an unacknowledged background resource
rather than an attributed source.

## Semantic Relevance (Cosine Similarity)

- Prompt vs. cited-URL title: 0.602
- Prompt vs. non-cited-URL title: 0.484
- Fanout query vs. cited-URL title (best match): 0.656

Cited pages show meaningfully higher semantic alignment with both the
user's original prompt and ChatGPT's internal fanout sub-queries than
non-cited pages do.

## URL Structure

Search results with natural-language URL slugs were cited 89.78% of
the time, vs. 81.11% for URLs without natural-language formatting.

## Content Age Patterns

**Search results**: median age of cited pages is ~500 days (~1.3
years); some cited pages exceed 2,700 days (~7.4 years) old. Non-cited
pages skew notably younger. Within a given retrieval set, older,
established pages are cited more than fresh ones.

**News results**: cited news articles have a median age of ~200 days
vs. ~300 days for non-cited news articles — the opposite direction
from the search-results pattern. Title relevance is nearly identical
between cited/non-cited news articles, so freshness functions as the
deciding tiebreaker specifically in the news vertical.

## Retrieval-Data Field Analysis

An initial pass found non-cited URLs had more populated metadata
fields (snippets present 14.81% vs. 4.36%; publication dates present
92.72% vs. 35.98%) — but this reflected compositional bias (different
mixes of reference types have different field-population rates by
default) rather than a genuine anti-correlation. Isolating the
comparison to search-result URLs only made these differences shrink
substantially.

## Strategic Implications

Ranking in the search index is a prerequisite for citation; semantic
alignment (to both the literal prompt and ChatGPT's internal fanout
sub-queries) then drives selection within the retrieved set. Content
addressing ChatGPT's fanout sub-questions specifically, not just the
surface-level prompt, outperforms surface-only optimization. Within
retrieval sets, relevance beats recency for search-sourced citations
(older/established pages win), but recency remains the deciding factor
specifically for the news vertical. Reddit is heavily used as
uncredited context even though it's almost never cited directly.
