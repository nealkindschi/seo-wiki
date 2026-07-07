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
