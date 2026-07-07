# SEO/AEO LLM Wiki Setup Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Scaffold the SEO/AEO LLM Wiki's directory structure, seed files, and `CLAUDE.md` schema doc so Claude can start ingesting sources and an Obsidian vault can be opened against `wiki/`.

**Architecture:** Two top-level folders — `raw/` (immutable sources, categorized into `articles/`, `studies/`, `reports/`, `assets/`) and `wiki/` (Claude-owned, doubling as the Obsidian vault: `concepts/`, `playbooks/`, `sources/`, plus `index.md`, `log.md`, `timeline.md`). `CLAUDE.md` at the project root encodes all conventions (page types, frontmatter, conflict handling, ingest/query/lint workflows, `[[wikilink]]` convention) so any future Claude Code or Desktop session picks up the same behavior without re-deriving it.

**Tech Stack:** Plain markdown files, YAML frontmatter, git for version history, Obsidian (external, user-installed) as the viewer. No code, no build step, no dependencies.

Full design rationale: `docs/superpowers/specs/2026-07-07-seo-aeo-llm-wiki-design.md`.

---

### Task 1: Scaffold `raw/` directory structure

**Files:**
- Create: `raw/articles/.gitkeep`
- Create: `raw/studies/.gitkeep`
- Create: `raw/reports/.gitkeep`
- Create: `raw/assets/.gitkeep`

Git does not track empty directories, so each subfolder gets an empty `.gitkeep` placeholder to make it exist in the repo before any real sources are ingested.

- [ ] **Step 1: Create the directories and placeholder files**

```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
mkdir -p raw/articles raw/studies raw/reports raw/assets
touch raw/articles/.gitkeep raw/studies/.gitkeep raw/reports/.gitkeep raw/assets/.gitkeep
```

- [ ] **Step 2: Verify the structure exists**

Run:
```bash
find raw -type d | sort
```
Expected output:
```
raw
raw/articles
raw/assets
raw/reports
raw/studies
```

- [ ] **Step 3: Commit**

```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
git add raw
git commit -m "Scaffold raw/ source directories"
```

---

### Task 2: Scaffold `wiki/` directory structure

**Files:**
- Create: `wiki/concepts/.gitkeep`
- Create: `wiki/playbooks/.gitkeep`
- Create: `wiki/sources/.gitkeep`

Same reasoning as Task 1 — these three subfolders start empty and need placeholders to be tracked by git.

- [ ] **Step 1: Create the directories and placeholder files**

```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
mkdir -p wiki/concepts wiki/playbooks wiki/sources
touch wiki/concepts/.gitkeep wiki/playbooks/.gitkeep wiki/sources/.gitkeep
```

- [ ] **Step 2: Verify the structure exists**

Run:
```bash
find wiki -type d | sort
```
Expected output:
```
wiki
wiki/concepts
wiki/playbooks
wiki/sources
```

- [ ] **Step 3: Commit**

```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
git add wiki
git commit -m "Scaffold wiki/ page directories"
```

---

### Task 3: Create `wiki/index.md`

**Files:**
- Create: `wiki/index.md`

This is the wiki's catalog — a one-line-summary entry per page, organized by category. Starts empty (no pages exist yet) but with the section headers Claude will fill in on each ingest, per the design spec's Ingest workflow (step 5: "Update `wiki/index.md`").

- [ ] **Step 1: Write the file**

```markdown
# Wiki Index

Catalog of every page in this wiki, organized by category. Updated by
Claude on every ingest (see `CLAUDE.md`). One line per page: link + a
short summary.

## Concepts

_(none yet)_

## Playbooks

_(none yet)_

## Sources

_(none yet)_
```

- [ ] **Step 2: Verify the file was written correctly**

Run:
```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
grep -c "^## " wiki/index.md
```
Expected output: `3` (the three section headers: Concepts, Playbooks, Sources)

- [ ] **Step 3: Commit**

```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
git add wiki/index.md
git commit -m "Add wiki index catalog"
```

---

### Task 4: Create `wiki/log.md`

**Files:**
- Create: `wiki/log.md`

Append-only chronological record of wiki *activity* (ingests, queries, lints), dated by when the work happened. Per the design spec's Log format, entries must start with a consistent `## [YYYY-MM-DD] <type> | ...` prefix so the file stays greppable.

- [ ] **Step 1: Write the file**

```markdown
# Log

Append-only chronological record of wiki activity. Each entry starts with
a consistent prefix so the file stays greppable, e.g.
`grep "^## \[" wiki/log.md | tail -5`.

Format:
```
## [YYYY-MM-DD] ingest | <source title>
## [YYYY-MM-DD] query | "<question>"
## [YYYY-MM-DD] lint | <summary of findings>
## [YYYY-MM-DD] conflict | <topic> — <one-line description>
```

---
```

- [ ] **Step 2: Verify the file was written correctly**

Run:
```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
grep -c "YYYY-MM-DD" wiki/log.md
```
Expected output: `4` (the four format-example lines)

- [ ] **Step 3: Commit**

```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
git add wiki/log.md
git commit -m "Add wiki activity log"
```

---

### Task 5: Create `wiki/timeline.md`

**Files:**
- Create: `wiki/timeline.md`

Append-only chronological record of real-world SEO/AEO *events*, dated by the source's own publish/event date — distinct from `log.md`, which is dated by when Claude did the work. Per the design spec, entries link to the source page and, when relevant, the concept page it affected.

- [ ] **Step 1: Write the file**

```markdown
# Timeline

Append-only chronological record of real-world SEO/AEO events (algorithm
updates, published studies/reports, industry announcements), dated by the
source's own publish/event date — **not** the date it was ingested into
this wiki.

Format:
```
## YYYY-MM-DD — <event description>
[[source-slug]] · <optional: superseded/updated [[concept-slug]]>
```

---
```

- [ ] **Step 2: Verify the file was written correctly**

Run:
```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
grep -c "source-slug" wiki/timeline.md
```
Expected output: `1`

- [ ] **Step 3: Commit**

```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
git add wiki/timeline.md
git commit -m "Add wiki timeline of real-world events"
```

---

### Task 6: Write `CLAUDE.md` schema doc

**Files:**
- Create: `CLAUDE.md`

This is the key file: it tells any future Claude Code or Desktop session how to read and maintain the wiki, so behavior is consistent across sessions without re-deriving conventions each time. Encodes everything from the design spec: directory layout, SEO/AEO tagging, `[[wikilink]]` convention, page types/frontmatter, conflict handling, the three workflows (ingest/query/lint), log/timeline formats, the Obsidian viewer, and out-of-scope notes.

- [ ] **Step 1: Write the file**

```markdown
# SEO/AEO LLM Wiki — Schema & Operating Instructions

This file tells Claude (Code or Desktop) how to read and maintain this
wiki. Full design rationale:
`docs/superpowers/specs/2026-07-07-seo-aeo-llm-wiki-design.md`.

## What this is

A persistent, LLM-maintained knowledge base of SEO and AEO (Answer Engine
Optimization) best practices, tactics, strategies, studies, and reports.
Instead of re-deriving answers from raw sources on every question, this
wiki incrementally builds and maintains interlinked markdown pages that
compound in value over time.

## Directory layout

- `raw/` — immutable source material. **Never edit files in here.**
  - `raw/articles/`, `raw/studies/`, `raw/reports/` — categorized by source type
  - `raw/assets/` — downloaded screenshots/charts referenced by sources
- `wiki/` — entirely Claude-owned, and doubles as the Obsidian vault the user opens
  - `wiki/index.md` — catalog of every wiki page, one-line summary each. Update on every ingest.
  - `wiki/log.md` — append-only chronological record of wiki activity
  - `wiki/timeline.md` — append-only chronological record of real-world SEO/AEO events
  - `wiki/concepts/` — topic synthesis pages
  - `wiki/playbooks/` — actionable reference: checklists, tactics, strategies
  - `wiki/sources/` — one page per ingested source

## SEO vs AEO

Not split into separate folders — they share one concept/playbook space.
Tag pages with `seo`, `aeo`, or both in frontmatter, since the two
overlap heavily.

## Link convention

Use **Obsidian-style `[[wikilinks]]`**, never relative markdown paths:

    [[technical-seo-audit-checklist]]

Obsidian resolves these natively, powers the graph view and backlinks
panel, and they don't break when pages move between folders.

## Page types & frontmatter

### Concept page (`wiki/concepts/<slug>.md`)

```yaml
---
type: concept
tags: [seo, aeo]
updated: YYYY-MM-DD
---
```

Body: overview/definition, current best understanding, links to relevant
playbooks and sources, and a **Conflicting Evidence** section when
sources disagree (see "Conflict handling" below).

### Playbook page (`wiki/playbooks/<slug>.md`)

```yaml
---
type: playbook
tags: [seo]
updated: YYYY-MM-DD
---
```

Body: checklist / numbered steps / tactic writeup, a "why / when to use
this" line, and links back to the concept(s) it belongs to.

### Source page (`wiki/sources/<slug>.md`)

```yaml
---
type: source
tags: [aeo]
date_published: YYYY-MM-DD
date_ingested: YYYY-MM-DD
origin: raw/studies/<file>
---
```

Body: short citation, key takeaways, which concepts/playbooks it updated.

## Conflict handling

On ingest, before writing anything, check whether the new source agrees
with, extends, or conflicts with existing concept/playbook claims.

- **Agrees/extends**: add as a supporting citation, bump `updated:` date.
- **Conflicts**: never silently overwrite or delete the old claim. Add or
  update a **Conflicting Evidence** section on the concept page:

```markdown
## Conflicting Evidence

- **Claim**: <claim>
  - Supported by: [[source-x]] (date)
  - Contradicted by: [[source-y]] (date), <reason>
- **Current best guess**: <leaning, with reasoning>, flagged as unresolved
```

Old claims are marked superseded-with-reasoning, never deleted —
SEO/AEO practices shift over time and it's valuable to know *when*
something was true. Lean on signals like recency,
official-source-vs-speculation, and study size to suggest a "current
best guess," but don't quietly resolve conflicts — surface them to the
user during ingest discussion or the next lint pass, and log a
`conflict` entry in `wiki/log.md`.

## Workflows

### Ingest

Trigger: the user hands you a source in any form — a URL, a file path
anywhere on disk (e.g. `~/Downloads/report.pdf`), pasted text, or an
attached file. **The user never manually places files into `raw/`** —
you do it:

1. Intake: fetch the URL (WebFetch) / read the given file / take the
   pasted text, and save it into the right
   `raw/{articles,studies,reports}/` subfolder — decide category and
   filename yourself. Download referenced images into `raw/assets/` if
   present.
2. Read the source, discuss key takeaways with the user before filing
   anything (stay involved per source — don't silently batch-process).
3. Create/update the `wiki/sources/` page for it.
4. Create or update relevant `wiki/concepts/` and `wiki/playbooks/`
   pages, applying "Conflict handling" above where claims disagree with
   existing pages.
5. Update `wiki/index.md`.
6. Append an entry to `wiki/log.md`.
7. If the source carries a real-world date (published date, algorithm
   update date, study period), append an entry to `wiki/timeline.md`.

### Query

User asks a question. Check `wiki/index.md` to find relevant
concept/playbook pages, read them (and underlying sources/raw if
needed), and answer with citations. If the answer itself is valuable (a
comparison, a synthesized strategy, an analysis), offer to file it back
into `wiki/` as a new or updated page rather than letting it disappear
into chat history. Log a `query` entry in `wiki/log.md`.

### Lint

Run when asked. Scan for: contradictions between pages, claims
superseded by newer sources, orphan pages with no inbound links,
concepts mentioned but lacking their own page, and missing
cross-references. Report findings; fix with the user's go-ahead. Log a
`lint` entry in `wiki/log.md`.

## Log & timeline formats

`wiki/log.md` — wiki *activity*, dated by when you did the work:

```
## [YYYY-MM-DD] ingest | <source title>
## [YYYY-MM-DD] query | "<question>"
## [YYYY-MM-DD] lint | <summary of findings>
## [YYYY-MM-DD] conflict | <topic> — <one-line description>
```

`wiki/timeline.md` — real-world *events*, dated by the source's own
publish/event date (not ingestion date):

```
## YYYY-MM-DD — <event description>
[[source-slug]] · <optional: superseded/updated [[concept-slug]]>
```

Both are append-only. Keep the prefix consistent so they stay
greppable, e.g. `grep "^## \[" wiki/log.md | tail -5`.

## Viewing the wiki (Obsidian)

`wiki/` is opened directly as an Obsidian vault (free, local, no
account) — no build step, no server. `[[wikilinks]]` resolve
automatically and power the graph view and backlinks panel.
Frontmatter (`type`, `tags`, `updated`) is Dataview-compatible if the
user installs that plugin later, but it's not required.

## Out of scope / deferred (do not build unless asked)

- **Live SEO tool integration** (Semrush, Ahrefs data pulls during
  query/lint to check staleness of wiki claims) — a possible future
  extension, not built now.
- **Search tooling** (e.g. qmd) — `index.md` is sufficient at current
  scale. Revisit if the wiki outgrows it (roughly >100 sources /
  hundreds of pages).
- **Dataview plugin** — not installed or required for the base setup.
- **Folder-watching / browser-extension ingestion** —
  natural-language ingestion (URL, path, or pasted text handed to you
  directly) was chosen instead.
```

- [ ] **Step 2: Verify the file was written correctly**

Run:
```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
grep -cE "^## (What this is|Directory layout|SEO vs AEO|Link convention|Page types & frontmatter|Conflict handling|Workflows|Log & timeline formats|Viewing the wiki|Out of scope)" CLAUDE.md
```
Expected output: `10` (one match per top-level section; this pattern
targets the specific section titles rather than counting every `## `
line, so it won't be thrown off by the `## [YYYY-MM-DD] ...` and
`## Conflicting Evidence` example lines inside the document's code
blocks)

- [ ] **Step 3: Commit**

```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
git add CLAUDE.md
git commit -m "Add CLAUDE.md schema and operating instructions"
```

---

### Task 7: Final structure verification

**Files:** none created — verification only.

- [ ] **Step 1: Verify the full directory tree matches the design**

Run:
```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
find . -path ./.git -prune -o -type f -print | sort
```
Expected output:
```
./CLAUDE.md
./docs/superpowers/plans/2026-07-07-seo-aeo-llm-wiki-setup.md
./docs/superpowers/specs/2026-07-07-seo-aeo-llm-wiki-design.md
./raw/articles/.gitkeep
./raw/assets/.gitkeep
./raw/reports/.gitkeep
./raw/studies/.gitkeep
./wiki/concepts/.gitkeep
./wiki/index.md
./wiki/log.md
./wiki/playbooks/.gitkeep
./wiki/sources/.gitkeep
./wiki/timeline.md
```

- [ ] **Step 2: Verify git history is clean**

Run:
```bash
cd "/Users/nealkindschi/Claude/LLM Wiki - SEO"
git status --short
```
Expected output: empty (nothing uncommitted)

- [ ] **Step 3: Tell the user the wiki is ready**

No commit needed for this task (verification only). Report to the user
that the structure is in place and they can now open `wiki/` as an
Obsidian vault, and start ingesting their first source by handing Claude
a URL, file path, or pasted text.
