# progress/ — Context

Decision-making instructions for this folder. See [[PROGRESS_FORMAT]] for entry-format details.

## Structure

- `status.md` — registry: active-thread table + concluded index + graveyard index (one line per item, no detail)
- `threads/YYYY-MM-DD-<topic>/` — active research directions: `hypothesis.md`, `log.md`, `results/` (raw outputs, figures, tables; any format). The date is the thread's start date and the folder name never changes afterwards, including when it moves to `concluded/` or `graveyard/`
- `concluded/YYYY-MM-DD-<topic>/` — threads closed because their question was answered: `conclusion.md` + the original thread contents, preserved as-is
- `graveyard/YYYY-MM-DD-<topic>/` — abandoned threads: `postmortem.md` + the original thread contents, preserved as-is
- `related-work/` — see [[RELATED-WORK_CONTEXT|related-work/RELATED-WORK_CONTEXT.md]]

## Context Layering

1. Threads under `threads/` are active — open a specific one only when the user's instruction calls for it, never all of them by default.
2. Do not open `concluded/` or `graveyard/` unless the user asks about past attempts, prior framings, or where a current thread came from.
3. **Abandoning a thread**: move the whole folder from `threads/` to `graveyard/` (never delete), write a short `postmortem.md` (why abandoned, what was learned, anything salvageable), and swap its row in `status.md` from the active table to the graveyard table (one line, linking the postmortem).
4. **Concluding a thread**: when the thread's question is answered (as opposed to dropped), move the whole folder from `threads/` to `concluded/` (never delete), write a short `conclusion.md` (why concluded, what was gained, what it led to), and swap its row in `status.md` from the active table to the concluded table (one line, linking the conclusion). Before moving, close the thread with a final `log.md` entry pointing at the conclusion.
5. **Lineage**: every `conclusion.md` and `postmortem.md` ends with a `## Led to` section naming the successor thread(s) or `writing/paper/` section by wikilink, with one line on why the work moved there (`pending` if the successor does not exist yet; replace it once it does). Every new thread's `hypothesis.md` opens with a `**Came from:** [[...]]` line pointing back at the conclusion or postmortem it grew out of (or `none` for a fresh start). Reading `status.md`'s concluded and graveyard tables in date order, then following these links, should reconstruct the project's whole trajectory after the fact.
6. A graveyard thread is a source of prior-work comparison against our own past attempts — never delete it.
7. `graveyard/` also holds **parked ideas** that never became a formal thread — e.g. a tangent noticed while reading a paper for a different reason. Same shape (`YYYY-MM-DD-<topic>/postmortem.md`), same one-line row in `status.md`'s graveyard table, just without a `threads/` folder to move from.

## File Size Limit (decision)

`status.md`'s active-thread table growing past the limit in the top-level [[AGENTS]] signals too many concurrent threads, not a file-size problem — flag it to the user instead of splitting. For `log.md`/`hypothesis.md` splitting mechanics, see [[PROGRESS_FORMAT]].
