# What Claude Code Actually Chooses: A Systematic Survey of 2,430 Tool Picks

Source: https://amplifying.ai/research/claude-code-picks/report
Authors: Edwin Ong & Alex Vikati (Amplifying / agent-intelligence)
Date: February 2026, v1.0
Fetched: 2026-07-07

## What was studied

A systematic analysis of Claude Code's tool recommendations across
2,430 open-ended prompts spanning 20 tool categories, 4 project types,
and 3 AI models (Sonnet 4.5, Opus 4.5, Opus 4.6). Core question: when
developers ask Claude Code open-ended questions like "add a database"
or "how do I deploy this?" without naming specific tools, what does the
agent actually install?

## Methodology

- Claude Code CLI v2.1.39 (agent mode), 3 models, 3 independent runs per
  model/repo combination.
- Test repos: TaskFlow (Next.js 14/TS/App Router, 100 prompts/20
  categories), DataPipeline (FastAPI/Python 3.11/Pydantic, 65
  prompts/13 categories), InvoiceTracker (Vite/React 18/TS, 85
  prompts/17 categories), deployctl (Node.js/TS/Commander.js, 20
  prompts/4 categories).
- 100 unique open-ended prompts, 5 phrasings per category, no tool
  names mentioned. Full `git checkout . && git clean -fd` between runs.
- Subagents extracted the primary tool recommendation from each
  response. Extraction success: 85.3% (2,073/2,430). Non-extractable:
  38% clarifying questions, 19% permission requests, 20% no tools
  found, 17% minimal responses, 6% misunderstood.
- Avg response time: 88s (range 32s deployment to 245s authentication);
  longer responses correlate with custom/DIY implementations.

## Key findings

### Agents build, not buy
In 12 of 20 categories, Claude Code frequently builds custom solutions
rather than recommending third-party tools. Custom/DIY = 252 of 2,073
primary picks (12%), the single most common recommendation category-
wide. Highest Custom/DIY rates: Auth (Python) 100%, Feature Flags 69%,
Auth (overall) 48%, Observability 22%, Email 22%, Real-time 21%, Forms
20%, Caching 19%. Manual validation of 50 Custom/DIY extractions: ~80%
genuine build-from-scratch.

### A default stack exists
Deployment: Vercel (100% JS; Railway 82% Python). Databases: PostgreSQL
58.4%. CI/CD: GitHub Actions 93.8%. Payments: Stripe 91.4%. UI:
shadcn/ui 90.1%. Email: Resend 62.7%. Package manager: pnpm 56.3%.
State: Zustand 64.8%. Testing: Vitest 59.1% (JS), pytest 100% (Python).
Observability: Sentry 63.1%. Styling: Tailwind CSS 68.4%.

### Complete top-20 rankings (excluding Custom/DIY)
1. GitHub Actions (CI/CD) 93.8%
2. Stripe (Payments) 91.4%
3. shadcn/ui (UI Components) 90.1%
4. Vercel (Deployment) 76.8%
5. Tailwind CSS (Styling) 68.4%
6. Zustand (State Management) 64.8%
7. Sentry (Observability) 63.1%
8. Resend (Email) 62.7%
9. Vitest (Testing) 59.1%
10. PostgreSQL (Databases) 58.4%
11. pnpm (Package Manager) 56.3%
12. React Hook Form (Forms & Validation) 52%
13. Redis (Caching) 41.6%
14. TanStack Query (API Layer) 39.5%
15. FastAPI (API Layer) 35.3%
16. AWS S3 (File Storage) 32.5%
17. NextAuth.js (Authentication) 31.2%
18. Next.js API Routes (API Layer) 28.6%
19. pytest (Testing) 25.7%
20. Railway (Deployment) 25.6%

### Category tiers
- **Near-monopolies (>75%)**: CI/CD (GitHub Actions 93.8%, zero picks
  for GitLab CI/CircleCI/Jenkins), Payments (Stripe 91.4%), UI
  Components (shadcn/ui 90.1%), Deployment (ecosystem-dependent:
  Vercel 100% JS, Railway 82% Python).
- **Strong defaults (50-75%)**: Styling (Tailwind 68.4%), State Mgmt
  (Zustand 64.8%, Redux zero primary picks despite 23 mentions —
  "known but deliberately not chosen"), Observability (Sentry 63.1%),
  Email (Resend 62.7%), Testing (Vitest 59.1% JS / pytest 100%
  Python), Databases (PostgreSQL 58.4%, MongoDB zero primary picks
  despite 30 mentions), Package Manager (pnpm 56.3%), Forms (React
  Hook Form 52%).
- **Competitive markets (<50%)**: Authentication (Custom/DIY 47.7%,
  NextAuth.js 31.2%), Caching (Redis 41.6%), API Layer (stack-fully-
  determined: TanStack Query/FastAPI/Next.js API Routes), File Storage
  (AWS S3 32.5%, stack-dependent), ORM (three-way race: SQLModel
  34.9%, Drizzle 32.5%, Prisma 20.5%, ecosystem-specific), Background
  Jobs (BullMQ 25.5% vs Inngest 23.6% vs Celery 18.2%, lowest
  extraction rate at 61.1%), Feature Flags (Custom/DIY 68.8%,
  LaunchDarkly 21.3% — clearest build-over-buy result), Real-time
  (most fragmented: Custom/DIY 20.8%, no dominant approach).

## Model comparison

- Extraction rates: Sonnet 4.5 86.3% (Custom/DIY 9.5%), Opus 4.5 86.7%
  (Custom/DIY 10.2%), Opus 4.6 82.9% (Custom/DIY 11.4%).
- **90% consensus within ecosystems**: all three models pick the same
  top tool in 18 of 20 categories when compared within-ecosystem.
- **Recency gradient**: newer models systematically favor newer tools.
  ORM (JS): Prisma 79%→0%, Drizzle 21%→100% (Sonnet→Opus 4.6) — "the
  strongest single-tool signal in dataset." Background Jobs (JS):
  BullMQ 50%→40%, Inngest 40%→50%. Caching (Next.js): Redis 46%→0%,
  Next.js Cache 31%→54%. Caching (Python): Redis 93%→29%, Custom/DIY
  0%→50%. Background Jobs (Python): Celery 100%→0%, FastAPI
  BackgroundTasks →44%.
- **Model personalities**: Sonnet 4.5 "The Conventional Model" (most
  decisive, lowest Custom/DIY 9.5%, extraction 86.3%). Opus 4.5 "The
  Balanced Model" (highest extraction 86.7%, most even distribution).
  Opus 4.6 "The Forward-looking Model" (favors newest tools, highest
  Custom/DIY 11.4%, lowest extraction 82.9%, asks more clarifying
  questions).

## Stability & consistency

- Phrasing stability (5 phrasings/category): avg 76%. 100% stable: API
  Layer, Authentication, CI/CD, Databases, Deployment, Payments. ≤50%
  stable: Background Jobs, Caching, File Storage, Real-time, ORM.
- Run-to-run consistency (3 runs/model/repo): 73% perfect agreement,
  25% two-of-three, 2.5% all differ. Most perfectly consistent: Package
  Manager/CI/CD (93%). Most variable: Real-time (40% perfect).
- Cross-repo "universal" tools (recommended across all applicable
  project types): GitHub Actions, Sentry, Custom/DIY (Feature Flags),
  pnpm, Zustand, shadcn/ui, Tailwind CSS, Stripe.
- Stack-specific tools vary predictably: Deployment (Vercel JS/Railway
  Python), Databases (PostgreSQL dominant, but React SPA favors
  Supabase 70%), Auth (NextAuth.js Next.js 91% / Custom/DIY Python
  100%), ORM (Drizzle JS 61% / SQLModel Python 72%), Testing (Vitest
  JS / pytest Python 100%).

## Tools rarely or never picked

Zero primary picks but "known": Redux (0 primary, 23 mentions),
MongoDB (0 primary, 30 mentions), Prisma (0 from Opus 4.6 specifically,
18 alt picks). Express: absent from primary and alternative
recommendations entirely. High alt-pick-but-low-primary ("known
alternatives"): Netlify (67 alt picks, 0 primary in Deployment),
SendGrid (55 alt picks, 6.9% primary), Yarn (51 alt picks, 0.7%
primary), TanStack Query (43 alt picks in State Management).

## Implications & recommendations

**For tool vendors:**
1. Claude Code shapes defaults — tools absent from primary
   recommendations become increasingly invisible; Custom/DIY prevalence
   (12/20 categories) makes this worse.
2. Ensure the tool appears in recent, high-quality code examples that
   models train on.
3. Create clear, well-documented getting-started paths.
4. Aim to become a primitive agents build *on top of*, rather than
   compete with Custom/DIY.
5. Being a "known alternative" (high alt-pick rate) is closer to
   becoming default than being invisible entirely.

**For developers:** an emergent "Claude Code Stack" exists — not
necessarily the best tools, but the most consistently recommended.
Strong context-awareness means recommendations are stack-appropriate,
not rote. The Custom/DIY tendency means developers should evaluate
whether hand-rolled code or a proper library better serves long-term
needs, especially for auth/payments/feature flags.

**For AI teams:** open questions include whether the Custom/DIY bias
serves users well in production-sensitive categories (auth, payments,
feature flags); whether the recency gradient creates a feedback loop
(newer tools recommended more → more adoption → more training data →
recommended even more); and whether response-time correlation with
custom solutions indicates model deliberation/uncertainty.

## Limitations

Not a developer-consensus survey; can't separate quality signals from
training frequency; Custom/DIY may overlap with extraction ambiguity;
self-judging extraction could introduce systematic bias; constrained
prompt space (N=2,430 from 100 base prompts); JS/Python-heavy, excludes
Go/Rust/Java; aggregate stats pool ecosystems (can mislead); snapshot
in time (early-2026 model versions). Manual validation of 50 Custom/DIY
extractions found ~85% accuracy; Wilson confidence intervals shown do
not account for extraction error.
