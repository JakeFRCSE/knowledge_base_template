# writing/paper/ — Context

Decision-making instructions for this folder. No separate format file yet — add `PAPER_FORMAT.md` if section-file conventions grow detailed enough to need one.

## Structure

- `outline.md` — section order + status
- `sections/` — one file per section (`NN-<name>.md`, skeleton: [[_templates/section|section]]), drafted independently
- `outline.md` status values: `not started` | `drafting` | `draft done` | `final`

## Workflow

- The file-per-section hierarchy maps 1:1 onto a future LaTeX/Overleaf document on purpose — sections will be transferred by hand eventually, so keep this mapping instead of tracking a separate one.
- Cite inline as `\cite{key}`, followed once per section by a `Sources:` line of wikilinks (`[[key]]`) so citations show up in Obsidian's graph. Keys match the citation key used for that paper's file under `progress/related-work/papers/`, even though these files are Markdown — keeps the eventual transfer close to copy-paste. The actual `.bib` entry is written by hand in Overleaf at transfer time.
- When a research finding changes the paper's argument, update [[status|progress/status.md]] (or the relevant thread's `log.md`) and the corresponding file here in the same pass, so the two don't drift apart.
