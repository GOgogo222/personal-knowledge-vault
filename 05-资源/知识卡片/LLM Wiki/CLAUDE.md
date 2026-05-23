# Wiki Schema — LLM Wiki

This file defines how this wiki is structured, what conventions apply, and how you (the LLM) should behave when ingesting sources, answering queries, and maintaining the wiki. Read this file at the start of every session.

---

## Directory layout

```text
05-资源/知识卡片/LLM Wiki/
├── CLAUDE.md          ← this file (schema / instructions for the LLM)
├── index.md           ← master catalog of all wiki pages
├── log.md             ← append-only operation log
├── overview.md        ← high-level synthesis of the entire wiki
├── entities/          ← pages for people, places, organizations, products
├── concepts/          ← pages for ideas, terms, frameworks, theories
├── sources/           ← one summary page per ingested raw source
├── queries/           ← saved answers to notable queries
└── llm-wiki.md        ← the original pattern description (reference only)

00-收件箱/LLM Wiki 原始材料/raw/
└── source documents   ← immutable source documents awaiting ingestion

99-附件/通用图片/IImwiki-assets/
└── image assets       ← locally downloaded images attached to sources
```

---

## Page format

Every wiki page should have YAML frontmatter:

```yaml
---
title: "Page Title"
type: entity | concept | source | query | overview
tags: [tag1, tag2]
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: 0          # number of raw sources that contributed to this page
---
```

Use `[[WikiLink]]` for all internal links. Prefer specific section anchors `[[Page#Section]]` when linking to a specific part of a page.

Use `> [!note]` / `> [!warning]` / `> [!question]` callouts for flagging contradictions, uncertainties, or open questions.

---

## Workflows

### Ingest

When the user provides a new source (file path, pasted text, or URL):

1. Read the source fully.
2. Briefly discuss key takeaways with the user (3–5 bullet points).
3. Create a summary page in `sources/` named after the source slug.
4. Update `index.md` — add the new source page to the Sources section.
5. Update or create pages in `entities/` and `concepts/` for every significant entity or concept mentioned.
6. Update `overview.md` if the source changes or enriches the big picture.
7. Append an entry to `log.md`:
   ```
   ## [YYYY-MM-DD] ingest | Source Title
   - Summary page: [[sources/slug]]
   - Pages touched: [[entities/X]], [[concepts/Y]], ...
   - Key additions: one-line per page
   ```
8. Report to the user: which pages were created/updated, and any contradictions found.

A single source typically touches 5–15 wiki pages.

### Query

When the user asks a question:

1. Read `index.md` to identify relevant pages.
2. Read those pages.
3. Synthesize an answer with `[[citations]]` to wiki pages.
4. Ask: "Should I save this answer as a wiki page?" If yes, create a page in `queries/` and update `index.md`.
5. Append to `log.md`:
   ```
   ## [YYYY-MM-DD] query | Question summary
   - Pages read: [[...]]
   - Saved: [[queries/slug]] or "not saved"
   ```

### Lint

When the user asks for a health check (or periodically every ~10 ingests):

1. Scan all pages in this LLM Wiki folder for:
   - Contradictions between pages
   - Claims superseded by newer sources
   - Orphan pages (no inbound links)
   - Concepts mentioned inline but lacking their own page
   - Missing cross-references between related pages
   - Data gaps that a web search could fill
2. Produce a lint report listing issues by category.
3. Fix issues the user approves.
4. Append to `log.md`:
   ```
   ## [YYYY-MM-DD] lint
   - Issues found: N
   - Fixed: N
   - Deferred: N
   ```

---

## Conventions

- **Language**: Write wiki pages in the same language as the source being ingested. If the user writes in Chinese, answer in Chinese. Wiki page content follows the source language; frontmatter fields are always English.
- **Naming**: File names are lowercase kebab-case, e.g. `transformer-architecture.md`, `andrej-karpathy.md`.
- **Disambiguation**: If two entities share a name, append a parenthetical: `apple-company.md` vs `apple-fruit.md`.
- **Contradictions**: When a new source contradicts an existing claim, add a `> [!warning]` callout to the affected page noting both claims and their sources. Do not silently overwrite.
- **Stubs**: It is fine to create a minimal stub page (`## Overview\n*stub — to be expanded*`) to hold a link target. Prefer a stub over an unlinked mention.
- **Sources count**: Keep `sources:` in frontmatter up to date. Increment whenever a new raw source contributes to a page.
- **Images**: If a source references images stored in `99-附件/通用图片/IImwiki-assets/`, embed them with Obsidian image links such as `![[filename.png]]`. Read the text first; view images separately for additional context.
- **Do not modify raw sources**: Treat all files in `00-收件箱/LLM Wiki 原始材料/raw/` as immutable. Never edit, move, or delete them during ingest.

---

## Index format

`wiki/index.md` is organized into sections by page type. Each entry is one line:

```
- [[path/to/page|Page Title]] — one-line description (N sources)
```

Sections: **Overview**, **Sources**, **Entities**, **Concepts**, **Queries**.

---

## Log format

`wiki/log.md` is append-only. Never delete or edit past entries. New entries go at the **top** (most recent first). Each entry starts with `## [YYYY-MM-DD] <operation> | <title>` so it is grep-parseable.

---

## Session start checklist

At the start of every new session:
1. Read `CLAUDE.md` (this file). ✓
2. Read `wiki/index.md` to get an overview of what exists.
3. Read the last 5 entries in `wiki/log.md` to understand recent activity.
4. Ask the user what they want to do: ingest, query, lint, or something else.
