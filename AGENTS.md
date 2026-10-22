# AGENTS.md

Guidance for agents working in this repository. This file holds only project structure and rules that apply regardless of folder or task.

Per-folder detail follows a fixed chain: `AGENTS.md` → `<FOLDERNAME>_CONTEXT.md` (decision-making instructions for that folder; `<FOLDERNAME>` is the folder's own name in capitals, e.g. `RELATED-WORK` for `related-work/`) → `<FOLDERNAME>_FORMAT.md` / `<FOLDERNAME>_LIST.md` (optional further detail, referenced from `_CONTEXT.md` when needed). Open a `_CONTEXT.md` only when the task at hand is actually in that folder, and its `_FORMAT.md`/`_LIST.md` only when `_CONTEXT.md` points you to it.

## Project Overview

Personal research repository for **<PROJECT>**: <one-line goal>. Built to keep research exploration and paper writing happening in parallel, without dead-end research directions cluttering the context an agent (or the user) needs to move forward.

## Folder Structure

```
_templates/                             # skeletons for every recurring file (Obsidian Templates folder)

progress/                              # see progress/PROGRESS_CONTEXT.md
├── status.md
├── threads/
├── concluded/
├── graveyard/
└── related-work/                       # see progress/related-work/RELATED-WORK_CONTEXT.md
    ├── papers.md                         # index
    ├── papers/                            # one file per paper
    └── comparisons/

writing/
└── paper/                              # see writing/paper/PAPER_CONTEXT.md
    ├── outline.md
    └── sections/
```

There is intentionally no `code/` or `automation/` here — code implementation lives elsewhere and is decided fresh when needed.

## Common Rules (apply regardless of folder or task)

1. **Default read scope on session start is this file only.** Do not auto-open `status.md`, a `_CONTEXT.md`, or anything else — open a file only when the user's instruction that turn calls for it.
2. **Write all new documents in English by default.** Only deviate if the user explicitly asks for another language for a specific document.
3. **Metadata files (every Markdown file in this repo except paper `sections/`) are capped at ~300 lines / ~10,000 characters.** When one is exceeded, split it along a natural boundary (topic, time range) rather than letting it keep growing — see the relevant folder's `_CONTEXT.md`/`_FORMAT.md` for how that folder splits.
4. **Ask before deciding on a genuine workflow-design fork** (e.g. tooling choices, structural changes) rather than picking a default silently. Routine execution within an already-agreed structure doesn't need this.
5. **This folder is interfaced via Obsidian.** When referring to another file from within a document (not from chat), use Obsidian's wikilink syntax (`[[filename]]` or `[[filename|display text]]`, path omitted unless needed for disambiguation) instead of a Markdown link — Obsidian renders these as graph connections, which is the point of linking here.
   - Files that share a name across threads (`hypothesis`, `log`, `conclusion`, `postmortem`) are linked as `[[<thread-folder>/<file>]]`: thread folder name only, never the `threads/`/`concluded/`/`graveyard/` parent. Obsidian resolves this by path suffix, so the link keeps working when the folder moves between parents. Never rename a thread folder when moving it.
   - Inside a Markdown table cell, escape the alias pipe: `[[file\|text]]`.
   - New files start from the matching skeleton in `_templates/`.
6. **Reading Protocol: read section by section.** Never read a whole file top-to-bottom by default. Scan section headers or entry titles first, decide relevance from those alone, then expand only the relevant section. This applies recursively (e.g. `status.md`'s table → a thread's `log.md` headers → the one dated entry that matters). Accumulating files (`log.md`, `papers.md`, etc.) must lead every entry with a one-line summary so this skim-then-expand pattern works.
7. **Summary format: nested bullet hierarchy.** Applies only to summaries the user asks for, not to the file formats defined in `_FORMAT.md` files. When asked to summarize something (a paper, a section), lead with a header naming what is summarized, then use top-level category bullets with indented sub-bullets, at near keyword-level compactness (short noun phrases, not full sentences). No em-dashes; show relationships through nesting instead.
