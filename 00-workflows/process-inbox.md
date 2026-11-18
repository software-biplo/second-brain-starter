# Workflow: Process Inbox

Use this workflow to turn raw inbox items into structured knowledge.

## Goal

Move useful information from `90-inbox/` into the right PARA location while preserving source context.

## Steps

1. Review unprocessed files in `90-inbox/`.
2. Classify each item:
   - project
   - area
   - resource
   - archive
   - ignore/no action
3. Extract useful facts:
   - client
   - project
   - people
   - dates
   - decisions
   - commitments
   - open loops
   - risks
   - useful links
4. Create or update the relevant folders in:
   - `01-projects/`
   - `02-areas/`
   - `03-resources/`
   - `04-archive/`
   A new project folder starts from `_templates/project.md` as its `README.md`.
5. Move high-confidence source items into the destination `sources/` folder and mark them as processed.
6. Keep unclear items in `90-inbox/`, mark them as `needs_review`, and list them in `99-generated/indexes/needs-review.md`.
7. Update generated summaries when useful (see `00-workflows/summary-policy.md`). Write the local `GENERATED.md` next to the project, area, or resource it summarizes, and the matching global summary in `99-generated/`.
8. If this folder is a Git repository, commit with a `process:` message.

## Classification Rules

Use `01-projects/` when the item belongs to work with a concrete outcome.

Projects are grouped by lifecycle:

- `01-projects/active/` for current delivery or maintenance.
- `01-projects/seeding/` for early, possible, or not-yet-confirmed work, like leads, scoping, and proposals.
- `01-projects/archived/` for completed or inactive project material.

A lead or proposal for a specific client is a seeding project, not part of the Sales area. Use area folders only when the material is about the ongoing business function itself.

Use `02-areas/` when the item belongs to an ongoing responsibility, like brand, sales, finance, operations, or delivery.

Use `03-resources/` when the item is useful reference material.

Use `04-archive/` when the item is historical or inactive but should remain searchable.

Leave it in `90-inbox/` if the destination is unclear.

## Known Merge Rules

Add a rule here every time the AI files something in the wrong place. Examples:

- `<client> / <client domain> / <product name>` belongs to `01-projects/active/<client-slug>`.
- Emails from `<accountant domain>` belong to `02-areas/finance`.
- `<newsletter name>` is ignored.

## Folder Shape

```txt
01-projects/<lifecycle>/<project-slug>/
  README.md          current state, owned by humans
  GENERATED.md       summary of the sources, maintained by the AI
  sources/
    emails/
    files/
    meetings/
    notes/
```

Areas and resources use the same shape.

## Source Preservation

Do not delete source items during normal processing.

For high-confidence items, move them into the destination source folder and mark them as processed:

```md
status: processed
processed_at: YYYY-MM-DD
processed_to:
  - path/to/file.md
```

For unclear items, keep them in `90-inbox/` and mark them as review material:

```md
status: needs_review
review_reason: short reason
```

## Update Style

Prefer small, clear updates:

- append meeting notes
- add decisions to a decision file (`_templates/decision.md`)
- add action items to open loops
- update current state when the source clearly changes it

Do not rewrite large canonical files unless the user asks.

When a source changes the story of a project, area, or resource:

- update the `README.md` source index and recent sources
- update the local `GENERATED.md`: current state, recent signals, open loops, and source files
- update the matching global summary in `99-generated/`

## Output

- processed inbox items
- one or more updated PARA folders
- updated generated summaries where useful
- a list of items that need review

## Agent Prompt

```txt
Process the unprocessed inbox items in my second brain.

Follow `00-workflows/process-inbox.md`.
Classify each item into PARA.
Preserve source context.
Mark inbox items as processed.
Leave unclear items in the inbox as needs_review.
Update generated summaries only when useful.
Tell me what changed, and which items need my review.
```
