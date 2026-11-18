# Workflow: Daily Routine

Use this when you, or a scheduled task in your AI app, update the brain end to end.

## Goal

Repeat the full knowledge pipeline without relying on chat history:

```txt
external sources -> 90-inbox/ -> PARA folders -> GENERATED.md + 99-generated/ -> saved
```

## Rhythm

- **Level 1:** once a week, 15 minutes, started by hand.
- **Level 2:** every morning, as a scheduled task in your AI app.

## Steps

1. **Save first.** If this folder is a Git repository and there are local changes, commit them with `maintenance: save changes YYYY-MM-DD`. Then pull the latest version.
2. **Import.** Follow `00-workflows/import-with-connectors.md`. Things you collected by hand are already in `90-inbox/` (see `00-workflows/ingest-data.md`).
3. **Process.** Follow `00-workflows/process-inbox.md`.
4. **Summarize.** For every project, area, or resource that changed:
   - update the `README.md` source index
   - update the local `GENERATED.md`
   - update the matching summary in `99-generated/`
   - check that the summaries mention the newest signals, not only new counts
5. **Weekly overview.** Once a week, write `99-generated/weekly/YYYY-Www.md`: what moved, what is open, what needs attention.
6. **Review.** List the items in `99-generated/indexes/needs-review.md`.
7. **Save.** If this folder is a Git repository, commit with `sync: update second brain YYYY-MM-DD` and push. If nothing changed, do not create an empty commit.
8. **Optional.** Write the morning brief (`00-workflows/morning-brief.md`).

## Rules

- Never delete source material.
- If a pull or push fails, stop and report. Do not merge, rebase, or overwrite.
- One run, one commit.

## Agent Prompt

```txt
Run the daily routine of my second brain.

Follow `00-workflows/daily-routine.md`.
Save local changes first, import new items through my connectors, process the inbox,
update the generated summaries for every touched project, area, and resource, and save the result.
Do not delete source material.
Report what changed, what needs my review, and the commit (if any).
```
