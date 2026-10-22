# progress/related-work/ — Format Details

Skeletons: [[_templates/paper|paper]] (per-paper file), [[_templates/comparison|comparison]] (`comparisons/` note).

## Per-paper file (`papers/<citation-key>.md`)

```
# <Title> (Year)

- Authors:
- Venue:
- Link: <required — Google Scholar, arXiv, DOI, or publisher page>
- Status: read | skimmed | to-read
- Core claim:
- Relevance: <why it matters to this project, or "background only">
```

- **Filename = citation key** (author+year+shortword, e.g. `smith2024example.md`; year = first public release, e.g. the arXiv year, and the key never changes after a later venue acceptance — update only the `Venue` field) — for later manual BibTeX entry in Overleaf; no `.bib` file is tracked in this repo.
- **Link is required, no exceptions.** Reference hallucination is a research-ethics violation. If a link can't be found, don't create the file — flag it as unverified instead.
- **Core claim**: one or two sentences — what the paper actually argues/shows, not the abstract restated.
- **Relevance**: be specific — "same question, different method", "motivates our metric", "background only", "counterexample to our hypothesis", etc. If it's genuinely unrelated background reading, say so instead of forcing a connection.

## Index (`papers.md`)

One table per theme (e.g. "Activation Verbalization (NLA core)", "Lens & Vocabulary-Projection Readouts", "Knowledge Editing & Localization" — themes emerge from the actual papers logged, not a fixed taxonomy; add/rename/split a theme as the collection grows). Each row: citation key (linking to its file), title, venue, logged date, status (`read` | `skimmed` | `to-read`) — a status column, not a separate table, since papers move between themes far less often than between read/to-read. Within a theme's table, `read`/`skimmed` rows go above `to-read` rows, most recently logged first within each group.

- **Venue column**: the accepted venue if the paper is published/accepted somewhere (e.g. `ACL 2025 Findings`), otherwise `arXiv preprint`.
- **Logged column**: the date this row was added to this index (not the arXiv submission date), `YYYY-MM-DD`.
- **Assigning a theme**: when logging a new paper, put it in the closest existing theme; only create a new theme table once a handful of papers would belong to it. For the very first paper, rename the `<First theme>` placeholder table in `papers.md` to that paper's theme.

## Comparison notes (`comparisons/`)

Filename `YYYY-MM-DD-<our-result>-vs-<citation-key>.md`. One note per comparison, linked from the thread's `log.md` entry that produced the result.

## Splitting when oversized

`papers.md`'s index table exceeding the size limit in the top-level [[AGENTS]] → split by topic/cluster into separate index files (e.g. `papers-<topic>.md`); `papers.md` itself becomes a thin pointer to those. Individual files under `papers/` never need splitting — each holds exactly one paper.
