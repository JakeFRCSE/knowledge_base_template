# progress/related-work/ — Context

Decision-making instructions for this folder. See [[RELATED-WORK_FORMAT]] for entry-format and splitting details.

## Structure

- `papers.md` — index: one row per paper read, linking to its file
- `papers/<citation-key>.md` — one file per paper, the actual record
- `comparisons/` — one note per "this result vs prior work X"

No `.bib` file is maintained here — BibTeX entries are written directly in Overleaf by hand at transfer time, not tracked in this repo.

## Requirements

- **Every reference must carry a real, checkable link** (Google Scholar, arXiv, DOI, publisher page) in its `papers/<citation-key>.md` file. Never fabricate or guess a link, citation, or any bibliographic detail — reference hallucination is a research-ethics violation. If a paper can't be found with a verifiable link, don't create the file.
- **Every paper read** — relevant yet or not — gets its own file under `papers/` and a row in the `papers.md` index. This is a reading log, not just a citation list for one thread.
- A new thread's `hypothesis.md` must include a "Related Work" section citing entries here by wikilink (`[[<citation-key>]]`). If a relevant paper isn't logged yet, add it first.
- When a result can be compared directly with a specific logged paper, add a comparison note under `comparisons/`.
- When writing a paper section, pull citation details from the relevant `papers/<citation-key>.md` rather than re-searching or re-typing them.

## Note-Taking Style

When told to write down something noticed while reading a paper (e.g. a reproducibility gap, a caveat, a limitation), keep it to a **short, essential summary** — not a full walkthrough of how it was found. Optimize for fast re-reading later, not completeness.

## Paper Search Preferences

When searching for candidate papers (not just logging ones the user already read):

- **Recency wins.** A more recent paper beats an older one covering similar ground.
- **Preferred venues**: NeurIPS, ACL, ICLR, EMNLP, ICML.
- **Preferred paper type**: oral presentations.
- **Exception**: if a paper is recent enough, a workshop paper is acceptable even without an oral slot.
- Log candidates with `Status: to-read` until the user confirms they've actually read one.

