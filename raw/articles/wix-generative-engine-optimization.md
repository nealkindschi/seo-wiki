# Generative Engine Optimization (GEO): LLM Optimization Strategies

Source: https://www.wix.com/studio/ai-search-lab/generative-engine-optimization
Author: Crystal Carter (Wix Studio AI Search Lab)
Published: 2026-07-07 (updated from earlier version)

## Definition
GEO ("LLM optimization"/"AI search") = taking steps to increase references and traffic to a brand/website in generative AI search and LLM responses, prioritizing platforms like Gemini, Perplexity, DeepSeek over traditional search engines for audience growth/share of voice/traffic.

## GEO is NOT AI Overview optimization
Fundamentally different user journeys:
- LLMs: users choose the LLM for search, interact/give feedback/ask follow-ups, control which LLM content they see.
- AI Overviews: users happen upon them (don't always trigger), receive content passively, generated per Google's system needs, no opt-in/consent.

## Why brands should care (traffic data, May 2025 SimilarWeb)
- ChatGPT: 5.5B monthly visits, 22B page views, ~7 min/session, 79% market share among LLM chatbots
- Gemini: 528M; Claude: 436M; Perplexity: 127M; Copilot: 31.36M
- Combined ~7B+ monthly visits across LLM chatbot channels
- Gartner: predicts 25% drop in search engine use by 2026, 50% drop in organic traffic by 2028

## Three LLM Categories
1. **Static pre-trained data LLMs** (e.g. Claude 3-3.5, GPT-3, Gemini 1.5, NotebookLM, Copilot app) — fixed training set, links may not be included.
2. **Search-augmented LLMs** (e.g. Perplexity, Copilot, GPT-4) — fixed training set + live search engine data, includes links/updates from web crawling.
3. **Reasoning models with search** (DeepSeek R1-R2, Gemini 2.5, OpenAI o1-o4) — "mixture of experts" niche networks, includes links/updates from crawling.

## Optimizing for Static Pre-Trained LLMs
- Expect visibility to change only as training data updates
- Don't expect consistent links — optimize for **brand mentions, not links**
- Adapt approach per model (each has different training cutoff, update cadence, user journey)
- Give feedback on response accuracy (thumbs up/down) — LLMs learn from user feedback even without fresh training data
- Monitor training data updates for visibility changes

**Knowledge cutoff dates** (at time of writing): Claude April 2024; Gemini from 2023; ChatGPT September 2021-December 2023 depending on version/tier.

**Case example**: author asked Gemini about a new site ("Site of Sites") — initially not recognized; gave thumbs-down feedback with correct URL; the model returned the correct information in a later query, demonstrating the feedback loop works.

**Model-specific content adaptation example**: Gemini 1.5 Flash-8B (most common consumer variant) has only 54.7% accuracy interpreting long-context text — shorter content may aid visibility in that specific model.

Tools: GPT for Sheets (bulk querying/tracking), SpyGPT by RiverFlowAI (searches 250M ChatGPT queries for brand mentions), Seer Interactive (LLM visibility monitoring service).

## Optimizing for Search-Augmented LLMs
- Optimize for the underlying search engine (Copilot ← Bing rankings, not Google rankings)
- Check core queries regularly — visibility fluctuates like search rankings
- Prioritize pages that already show as citations in the LLM when planning internal linking — link from already-cited pages to build more LLM visibility, similar to being indexed in traditional search

## Optimizing for ALL LLMs
1. **Optimize for the crawl** — LLM crawlers are controllable via robots.txt; their purpose is to help the LLM understand content (not rank it), so navigational/pagination pages don't need to be crawled — prioritize brand/product/service content instead.

   | LLM | User agent |
   |---|---|
   | ChatGPT | OAI-SearchBot, ChatGPT-User, GPTBot |
   | Copilot | BingBot |
   | Gemini | Google-Extended (inferred, not officially confirmed) |
   | Claude | ClaudeBot |
   | Perplexity | PerplexityBot |

2. **Prioritize search-augmented LLMs first** — they show real-time feedback on content changes; static LLMs require waiting for the next training update. Data from search-augmented systems within a model family (e.g. ChatGPT/Copilot) likely filters down to the static counterpart over time.
3. **Manage brand entities** — both LLM types train on Wikipedia (65M+ pages), core to Google's Knowledge Graph/semantic web. Strong entity presence (structured data, Wikipedia, semantic footprint) drives accurate, high visibility (example: "Barbie" entity links to Mattel/dolls/toy industry even without explicit mention, via Wikipedia's opening line "Barbie is a fashion doll").
4. **Get involved with LLM platforms directly**, not just optimize for inclusion:
   - Content partnerships: OpenAI (Hearst, Le Monde, Prisa, Vox Media, Condé Nast, The Atlantic, GEDI, News Corp, Time); Perplexity Publisher Program (Time, Entrepreneur, The Texas Tribune, Der Spiegel)
   - Custom GPTs — rank on Google too, and can embed outbound links driving traffic (example: "Diagrams: Flowcharts & Mindmaps" GPT)
   - Perplexity Pages — curated brand experiences within the app

## Author
Crystal Carter, Wix Studio AI Search Lab.
