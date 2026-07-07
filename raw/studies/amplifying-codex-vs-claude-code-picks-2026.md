# Codex vs Claude Code: AI Agent Tool Selection Study

Source: https://amplifying.ai/research/codex-vs-claude-code-picks
Authors: Edwin Ong & Alex Vikati (Amplifying)
Date: March 2026
Fetched: 2026-07-07

## Methodology

Tested two flagship AI coding agents against identical prompts across
five repository types, generating 1,470 successful responses (1,452
analyzable tool picks: 729 Codex, 723 Claude). Focused on 12 categories
of *contested* infrastructure decisions — search, secrets management,
rate limiting, edge compute, etc. — deliberately excluding already-
standardized categories like CI/CD or authentication covered in the
earlier Claude-only study.

- Codex CLI 0.114.0 running GPT-5.3.
- Claude Code v2.1.78 running Opus 4.6.
- Repos: Next.js SaaS, FastAPI Python, Vite React SPA, Go microservice,
  Rails application. Three runs per repository/category.

## Key findings

### Agreement and consensus
7 of 12 categories showed agreement on the top pick between the two
agents; 6 of those 7 agreement categories converged on Custom/DIY. The
only category where both agents converged on the same *named* tool was
Log Aggregation → Grafana (Claude 32%, Codex 43%).

### Major divergences (5 of 12 categories)
- **JS Runtime & Toolchain**: largest gap. Claude → Bun 63% vs Codex →
  Node.js 50%/Bun 13% (50-point gap). Codex emphasized existing Node
  compatibility/conservative upgrades; Claude highlighted Bun's speed.
- **Search**: Claude → PostgreSQL FTS 37%, Custom/DIY 35%; Codex →
  Custom/DIY 31%, PostgreSQL FTS 28%, Typesense 19%. Both converge on
  PostgreSQL FTS for backend-heavy stacks (Go 40-60%, Rails 47-63%).
- **SMS/Push**: Claude → Twilio 59% (consistently 57-70% across
  languages) vs Codex → Custom/DIY 27%, Twilio 25%, OneSignal 21%.
- **Scheduled Tasks/Cron**: Codex → OS cron 23%; Claude splits
  APScheduler/Vercel Cron 23% each. Both converge on Vercel Cron for
  Next.js (80-93%).
- **Edge/Serverless Compute**: Codex → Cloudflare Workers 49% (global
  isolate architecture reasoning) vs Claude → Vercel Edge 24%, Fly.io
  20% (Next.js integration reasoning).

### Ownership/acquisition signals
- **Statsig (OpenAI-acquired)**: Codex picks it primary in 27% of
  feature-flag responses (20/75); Claude never picks it primary despite
  mentioning it in 28% of cases. Conversion rate: Codex 64.5%, Claude
  0%.
- **Bun (Anthropic-acquired)**: Claude picks it 63% for JS runtime vs
  Codex 13%. Both mention it often (Claude 97%, Codex 73% of
  responses), but conversion differs sharply: Claude 65.5%, Codex
  18.2%.
- Researchers' framing: "alignment between an agent and its parent
  company's acquired tools" is observed, but this is "correlation, not
  causation" — acquisition targets may already be best-in-class.
- **Headline framing**: "The safest conclusion is descriptive:
  conversion differs much more than awareness does" — both agents often
  *mention* the same competing tools, but differ sharply in which one
  they actually convert to a primary pick.

### Platform preferences (beyond acquisitions)
- Codex: 47 Cloudflare-branded picks across categories (Edge/Serverless
  49%, Cloudflare Images 22%) vs Claude's 9.
- Claude: 29 Vercel-branded picks (Vercel Edge 24%, Vercel Cron 23%) vs
  Codex's 17.

## Category-by-category breakdown

- **Feature Flags** (agreement): Codex Custom/DIY 40%, Statsig 27%,
  PostHog 12%. Claude Custom/DIY 41%, Unleash 19%, Flipper 12%. Python
  stack diverges (Codex 40% DIY vs Claude 53% Unleash).
- **JS Runtime & Toolchain** (disagreement): see above.
- **Search** (disagreement): see above.
- **Image & Media Processing** (agreement): Codex Custom/DIY 27%,
  Cloudflare Images 22%, ImageKit 13%. Claude Custom/DIY 35%,
  Cloudinary 17%, Pillow 17%. Codex recommends Cloudflare Images (22%);
  Claude avoids it entirely (0%).
- **Headless CMS** (agreement): Codex Custom/DIY 24%, Storyblok 22%,
  Contentful 11%. Claude Custom/DIY 33%, Sanity 22%, Contentful 18%.
  Both heavily avoid CMS recommendations for early-stage repos.
- **SMS & Push** (disagreement): see above.
- **Secret Management** (agreement): Codex Custom/DIY 31%, Doppler 21%,
  AWS Secrets Manager 17%. Claude Custom/DIY 36%, HashiCorp Vault 33%,
  Doppler 20%. Doppler recognized by both at 20-21%.
- **Rate Limiting** (agreement): Codex Custom/DIY 32%, Cloudflare 20%,
  Rack::Attack 20%. Claude Custom/DIY 33%, Redis 22%, Rack::Attack 12%.
  Rails repos drive Rack::Attack to 73-80%.
- **Scheduled Tasks/Cron** (disagreement): see above.
- **RBAC/Authorization** (agreement): Codex Custom/DIY 55%, Pundit 16%,
  Auth0 9%. Claude Custom/DIY 81%, Pundit 13%. Highest-DIY category
  overall.
- **Log Aggregation** (agreement): Codex Grafana 43%, Datadog 37%,
  Axiom 7%. Claude Grafana 32%, Datadog 25%, Custom/DIY 17%. Only
  category with full named-tool agreement.
- **Edge & Serverless Compute** (disagreement): see above.

## Up-and-coming tools
- **Doppler** (Secrets): ~20-21% from both agents — emerging consensus.
- **Upstash** (Rate Limiting): ~8-10% from both — consistent serverless
  Redis pick.
- **Meilisearch** (Search): Claude 19% vs Codex 8% — emerging Claude
  preference for modern search engines.
- **Axiom** (Log Aggregation): 7-10% from both — emerging in hosted
  logging.

## Conclusion

Agents agree on fundamental architectural decisions (custom RBAC,
Grafana for logging) but diverge meaningfully where ecosystem lock-in
or platform/parent-company preference plays a role. 7/12 agreement
suggests reasonable convergence overall; the 5/12 divergences show
platform affinity, acquired-tool familiarity, and architectural
philosophy still produce genuinely different recommendation patterns
per agent — with real technology-adoption consequences given each
agent's install-base.
