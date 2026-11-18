---
type: system_note
status: active
---

# Projects

Projects are grouped by lifecycle.

## Active

Work that is currently being delivered or actively maintained.

## Seeding

Possible, early, paused, or not-yet-confirmed work: leads, scoping, proposals. Keep these lighter until there is a concrete commitment.

## Archived

Completed, cancelled, or no-longer-active work. It remains searchable, but it does not pollute the active context.

When a project changes phase, move its whole folder to the new lifecycle folder.

## Processing Rule

Move high-confidence source items into:

```txt
01-projects/<lifecycle>/<project-slug>/sources/<source-type>/
```

Each project also has:

```txt
README.md
GENERATED.md
```

`README.md` is the human-owned current truth. `GENERATED.md` is regenerated from sources and should be read by AI agents before diving into `sources/`.

Leave low-confidence items in `90-inbox/` and list them in `99-generated/indexes/needs-review.md`.
