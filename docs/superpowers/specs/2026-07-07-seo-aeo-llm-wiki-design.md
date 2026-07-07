# SEO/AEO LLM Wiki — Design

## Purpose

A persistent, LLM-maintained knowledge base of SEO and AEO (Answer Engine
Optimization) best practices, tactics, strategies, studies, and reports —
built on the "LLM Wiki" pattern (Karpathy's gist on incrementally-built,
LLM-maintained knowledge wikis). Instead of re-deriving answers from raw
sources on every question (RAG-style), Claude incrementally builds and
maintains interlinked markdown pages that compound in value over time.

Used from Claude Code (CLI) and Claude Desktop — both have local file
system access to this folder, so no remote sync or connector is required.

## Architecture

```
LLM Wiki - SEO/
├── CLAUDE.md              ← schema: operating instructions for Claude
├── raw/                   ← immutable source material, never edited by Claude
│   ├── articles/
│   ├── studies/
│   ├── reports/
│   └── assets/            ← downloaded screenshots/charts referenced by sources
├── wiki/
│   ├── index.html         ← docsify loader (renders wiki/ as a browsable site in Chrome)
│   ├── index.md           ← catalog of every wiki page, one-line summary, by category (docsify homepage)
│   ├── log.md             ← append-only chronological record of wiki activity (ingests/queries/lints)
│   ├── timeline.md        ← append-only chronological record of real-world SEO/AEO events, dated by source publish/event date
│   ├── concepts/          ← topic synthesis pages ("what is X, what do we know")
│   ├── playbooks/         ← actionable reference: checklists, tactics, step-by-step strategies
│   └── sources/           ← one page per ingested source: citation, date, key takeaways, links out
└── .git/                  ← version history, local only, no remote required
```

- `raw/` is the source of truth. Claude reads from it but never modifies it.
- `wiki/` is entirely Claude-owned: concepts, playbooks, sources, index, log, timeline.
- `concepts/` pages cross-link to `playbooks/` and cite `sources/`, which cite files in `raw/`.
- Cross-references use **standard relative markdown links**
  (e.g. `[Technical SEO Audit Checklist](../playbooks/technical-seo-audit-checklist.md)`),
  not Obsidian-style `[[wikilinks]]` — this is what makes them clickable in
  the Chrome viewer (see Viewing the Wiki below).
- SEO and AEO are **not** split into separate sections — they share one
  concept/playbook space, distinguished only by the `tags` frontmatter field
  (`seo`, `aeo`, or both), since the two overlap heavily.

## Page types & frontmatter

**Concept page** (`wiki/concepts/<slug>.md`) — synthesis of what's known about a topic.
```yaml
---
type: concept
tags: [seo, aeo]
updated: YYYY-MM-DD
---
```
Body: overview/definition, current best understanding, links to relevant
`playbooks/` and `sources/`, and a **Conflicting Evidence** section when
sources disagree (see Conflict Handling below).

**Playbook page** (`wiki/playbooks/<slug>.md`) — actionable, reusable reference.
```yaml
---
type: playbook
tags: [seo]
updated: YYYY-MM-DD
---
```
Body: checklist / numbered steps / tactic writeup, a "why / when to use
this" line, and links back to the concept(s) it belongs to.

**Source page** (`wiki/sources/<slug>.md`) — one per ingested source.
```yaml
---
type: source
tags: [aeo]
date_published: YYYY-MM-DD    # date of the article/study/report itself
date_ingested: YYYY-MM-DD     # date it was added to the wiki (secondary importance)
origin: raw/studies/<file>
---
```
Body: short citation, key takeaways, which concepts/playbooks it updated.

## Conflict handling

On ingest, before writing, Claude checks whether the new source agrees
with, extends, or conflicts with existing concept/playbook claims.

- **Agrees/extends**: add as a supporting citation, bump `updated:` date.
- **Conflicts**: never silently overwrite or delete the old claim. Add or
  update a **Conflicting Evidence** section on the concept page:
  ```
  ## Conflicting Evidence
  - **Claim**: <claim>
    - Supported by: [source-x](../sources/source-x.md) (date)
    - Contradicted by: [source-y](../sources/source-y.md) (date), <reason>
  - **Current best guess**: <leaning, with reasoning>, flagged as unresolved
  ```
  Old claims are marked superseded-with-reasoning, not deleted — SEO/AEO
  practices shift over time and it's valuable to know *when* something was
  true. Claude may suggest a "current best guess" using signals like
  recency, official-source vs. speculation, and study size, but does not
  quietly resolve conflicts — they're surfaced to the user during ingest
  discussion or the next lint pass, and logged as a `conflict` entry in
  `log.md`.

## Workflows

### Ingest

Trigger: user hands Claude a source in any form — a URL, a file path
anywhere on disk (e.g. `~/Downloads/report.pdf`), pasted text, or an
attached file in Desktop app. **The user never manually places files into
`raw/` subfolders** — Claude does this itself:

1. Intake: fetch the URL (WebFetch) / read the given file / take the pasted
   text, and save it into the appropriate `raw/{articles,studies,reports}/`
   subfolder (Claude decides category and filename). Download referenced
   images into `raw/assets/` if present.
2. Read the source, discuss key takeaways with the user (per user
   preference — stay involved per source, not silent batch processing).
3. Create/update the `wiki/sources/` page for it.
4. Create or update relevant `wiki/concepts/` and `wiki/playbooks/` pages,
   applying Conflict Handling above where claims disagree with existing
   pages.
5. Update `wiki/index.md`.
6. Append an entry to `wiki/log.md`.
7. If the source carries a real-world date (published date, algorithm
   update date, study period), append an entry to `wiki/timeline.md`.

### Query

User asks a question. Claude checks `wiki/index.md` to find relevant
concept/playbook pages, reads them (and underlying `sources/`/`raw/` if
needed), and answers with citations. If the answer is itself valuable
(a comparison, a synthesized strategy, an analysis) Claude offers to file
it back into `wiki/` as a new or updated page rather than letting it
disappear into chat history.

### Lint

Run periodically, on request. Claude scans for: contradictions between
pages, claims superseded by newer sources, orphan pages with no inbound
links, concepts mentioned but lacking their own page, and missing
cross-references. Reports findings; fixes with user go-ahead. Logged as a
`lint` entry in `log.md`.

## Log & timeline formats

`wiki/log.md` — wiki *activity*, dated by when Claude did the work:
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
[source-slug](sources/source-slug.md) · <optional: superseded/updated [concept-slug](concepts/concept-slug.md)>
```

Both are append-only and use a consistent line prefix so they stay
greppable (`grep "^## \[" wiki/log.md | tail -5`).

## Viewing the wiki (Chrome)

`wiki/` is served as a browsable local site using
[docsify](https://docsify.js.org) — a no-build documentation site
generator that renders a folder of markdown files client-side.

- `wiki/index.html` is a small static file that loads docsify and points
  it at `index.md` as the homepage. It's checked into git alongside
  everything else — no build step, no generated output to maintain.
- To view it: run a one-line local server from the `wiki/` folder (e.g.
  `npx docsify-cli serve wiki`) and open `http://localhost:3000` in
  Chrome. A local server is required because docsify fetches markdown
  files via AJAX, which browsers block on plain `file://` URLs.
- Navigation comes from `index.md` itself (already the wiki's catalog) and
  the standard relative markdown links between pages — no separate
  sidebar file to maintain.
- Because `wiki/` uses standard relative links rather than
  `[[wikilinks]]`, this same content also renders correctly on GitHub, in
  VS Code's markdown preview, or in Obsidian later if desired — docsify
  isn't a one-way door.

## Out of scope / deferred

- **Live SEO tool integration** (Semrush, Ahrefs data pulls during
  query/lint to check staleness of wiki claims) — noted in `CLAUDE.md` as a
  possible future extension, not built now.
- **Search tooling** (e.g. qmd) — `index.md` is sufficient at current
  scale (gist reports this holds up to ~100 sources / hundreds of pages).
  Revisit if the wiki outgrows it.
- **Obsidian** — explicitly skipped per user preference (no extra app).
  Viewing is instead handled via a local docsify site in Chrome (see
  Viewing the Wiki above); the structure still works fine in Obsidian
  later since it's just markdown with standard relative links.
- **Folder-watching / browser extension ingestion** — natural-language
  ingestion (URL, path, or pasted text handed to Claude directly) was
  chosen over building additional tooling.

## Setup (initial implementation)

1. `git init` the wiki folder. *(done during brainstorming, since git
   tracking was already decided as part of this design)*
2. Create `raw/{articles,studies,reports,assets}/`,
   `wiki/{concepts,playbooks,sources}/`.
3. Create empty `wiki/index.md`, `wiki/log.md`, `wiki/timeline.md` with
   header/format notes.
4. Create `wiki/index.html` (docsify loader, homepage set to `index.md`).
5. Write `CLAUDE.md` encoding all of the above: architecture, page types,
   conflict handling, workflows, log/timeline formats, link conventions,
   the Chrome viewer, and the out-of-scope notes.
6. Initial commit.

No sources are migrated in this pass — that happens in the first real
ingest session once the structure exists.
