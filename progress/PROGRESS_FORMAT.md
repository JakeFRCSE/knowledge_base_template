# progress/ — Format Details

## Skeletons

Every recurring file starts from its skeleton in `_templates/`: [[_templates/hypothesis|hypothesis]], [[_templates/log|log]], [[_templates/conclusion|conclusion]], [[_templates/postmortem|postmortem]].

## Entry format (`log.md`, `hypothesis.md`)

Entries lead with a one-line summary before detail, so they're skimmable per the Reading Protocol in the top-level [[AGENTS]]:

```
## YYYY-MM-DD — <one-line summary>
<full detail>
```

`hypothesis.md` = `**Came from:**` line, title, dated hypothesis entries (a revised hypothesis is a new dated entry, not an edit), then a `## Related Work` section.

## `status.md` rows

- Thread cell links the thread by folder name: active → `[[<folder>/hypothesis\|<topic>]]`, concluded → `[[<folder>/conclusion\|<topic>]]`, graveyard → `[[<folder>/postmortem\|<topic>]]`.
- `Led to` cell = the wikilink(s) from the conclusion/postmortem's `## Led to` section, or `pending`/`none`.
- Active `Status` column: a short free-text phrase on where the thread stands right now (e.g. `reading`, `running E1`, `writing up`).
- Update `_Last updated:_` whenever a row changes.

## Splitting when oversized

`log.md` exceeding the size limit in the top-level [[AGENTS]] → split by time range, e.g. `log-2026-09.md`, `log-2026-10.md`. `hypothesis.md` should not grow that large; if it does, the thread has likely split into two threads.
