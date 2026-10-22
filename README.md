# Research Knowledge Base Template

An Obsidian vault for running research threads and paper writing in parallel, built to be operated together with a coding agent (Claude Code, Codex, etc.). Dead-end directions are archived rather than deleted, so the active context stays small while the full trajectory remains traceable.

## Quick start

1. Clone and open as a vault:
   ```bash
   git clone https://github.com/JakeFRCSE/knowledge_base_template.git my-research
   ```
   In Obsidian: **Open folder as vault** → select `my-research/`.
2. Fill in the **Project Overview** in `AGENTS.md` (replace `<PROJECT>` and `<one-line goal>`).
3. (Optional) Edit the paper-search preferences in `progress/related-work/RELATED-WORK_CONTEXT.md` and the section list in `writing/paper/outline.md`.
4. Start your agent in the vault folder. Claude Code reads `CLAUDE.md` → `AGENTS.md`; other agents read `AGENTS.md` directly. Ask it to open your first thread.

## How it works

| Folder | Purpose |
|---|---|
| `progress/status.md` | One-line registry of every thread: active, concluded, abandoned |
| `progress/threads/` | Active research directions (`hypothesis.md`, `log.md`, `results/`) |
| `progress/concluded/` | Threads whose question was answered, with `conclusion.md` |
| `progress/graveyard/` | Abandoned threads and parked ideas, with `postmortem.md` |
| `progress/related-work/` | One file per paper read, an index, and result-vs-prior-work notes |
| `writing/paper/` | Paper outline and one file per section |
| `_templates/` | Skeletons for every recurring file |

- **Rules for agents:** `AGENTS.md` holds the folder map and universal rules. Each folder's own rules live in its `*_CONTEXT.md` (and `*_FORMAT.md`), which the agent opens only when working there.
- **Lineage:** every conclusion/postmortem ends with `## Led to`, and every new hypothesis starts with `**Came from:**`, so following links from `status.md` reconstructs how the project evolved.
- **Templates by hand:** in Obsidian, `Cmd/Ctrl+P` → **Templates: Insert template** inserts any skeleton from `_templates/`.

## Typical first session

1. Log a paper you have read: ask the agent to add it (`papers/<citation-key>.md` + a row in `papers.md`).
2. Open a thread: `progress/threads/YYYY-MM-DD-<topic>/` with `hypothesis.md` citing that paper, plus a row in `status.md`.
3. Record progress as dated entries in the thread's `log.md`.
4. When the question is answered, conclude it (moves to `concluded/`); if dropped, abandon it (moves to `graveyard/`). Nothing is ever deleted.
