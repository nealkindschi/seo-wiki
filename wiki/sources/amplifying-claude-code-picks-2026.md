---
type: source
tags: [aeo]
date_published: 2026-02
date_ingested: 2026-07-07
origin: raw/studies/amplifying-claude-code-picks-2026.md
---

# What Claude Code Actually Chooses (Amplifying, Feb 2026)

**Citation:** Ong, Edwin and Vikati, Alex. "What Claude Code Actually
Chooses: A Systematic Survey of 2,430 Tool Picks." Amplifying
(agent-intelligence). February 2026, v1.0.
https://amplifying.ai/research/claude-code-picks/report

## Key takeaways

- First empirical study of what a coding agent (Claude Code) actually
  recommends/installs when developers ask open-ended questions ("add a
  database," "how do I deploy this?") without naming a specific tool —
  2,430 prompts, 20 tool categories, 4 repos, 3 models.
- **Agents build rather than buy in 12 of 20 categories.** Custom/DIY
  is the single most common recommendation category-wide (12% overall,
  up to 100% for Python auth, 69% for feature flags).
- **A consistent "default stack" exists** where agents do pick
  third-party tools: GitHub Actions (93.8%), Stripe (91.4%), shadcn/ui
  (90.1%), Vercel/Railway (deployment, ecosystem-dependent), Tailwind
  CSS (68.4%), Zustand (64.8%), Sentry (63.1%), Resend (62.7%), Vitest/
  pytest (testing), PostgreSQL (58.4%), pnpm (56.3%).
- **90% cross-model consensus within ecosystem** — the three models
  tested agree on the top tool in 18/20 categories once JS/Python
  results aren't pooled together.
- **Recency gradient**: newer model versions systematically favor newer
  tools even at the expense of previously-dominant incumbents — e.g.
  Prisma (2019) goes from 79% to 0% pick share while Drizzle (2022)
  goes from 21% to 100%, across Sonnet 4.5 → Opus 4.5 → Opus 4.6.
- **Being "known but unpicked" is a real, distinct state** from being
  invisible: Redux (0 primary picks, 23 mentions), MongoDB (0 primary,
  30 mentions), and Prisma (0 from the newest model specifically) are
  actively considered and passed over — worse than never being
  discussed, since the agent has already evaluated and rejected them.
  Tools with high "alternative" pick rates but low primary rates
  (Netlify, SendGrid, Yarn) are closer to becoming default than tools
  that never surface at all.
- Recommendations are strongly stack/ecosystem-aware, not rote pattern
  matching (Drizzle for JS, SQLModel for Python; NextAuth.js for
  Next.js, Custom/DIY for Python auth).
- Stability varies a lot by category: CI/CD, Payments, Deployment,
  Databases, Auth, and API Layer are highly stable across phrasing and
  repeated runs; Background Jobs, Caching, File Storage, Real-time, and
  ORM choice are comparatively unstable/context-sensitive.
- Vendor-facing implications: appear in recent, high-quality code
  examples (training data); ship a clear, well-documented
  getting-started path; try to be the primitive agents build *on top
  of* rather than compete with Custom/DIY; being a known alternative
  beats being invisible.
- Caveats: not a developer-consensus survey, can't separate quality
  signal from training-data frequency, JS/Python-heavy, snapshot of
  early-2026 model versions, self-judged extraction (~85% accuracy on
  manual spot-check).

## What this updated in the wiki

- Created new concept [[ai-coding-agent-tool-selection]]: the build-vs-
  buy pattern, default-stack list, consensus/recency dynamics, and
  stability findings, as the technical-visibility counterpart to
  [[generative-engine-optimization]] but for a coding-agent audience
  (tool vendors) rather than a general-content audience.
- Created new playbook
  [[optimizing-for-coding-agent-recommendations]]: actionable tactics
  for tool/library vendors who want Claude Code (and similar coding
  agents) to recommend and install their product by default.
- Cross-linked from [[generative-engine-optimization]] as a sibling
  domain — same "visibility inside an AI-generated answer" mechanic,
  different engine type and audience.
- No conflicts — new topic area, first source in the wiki on coding-
  agent tool selection.
