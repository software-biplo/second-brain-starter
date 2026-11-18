# Claude Instructions

You are working inside a second brain.

Use `BRAIN.md` as the operating framework. `AGENTS.md` has the same defaults for other AI agents.

## Answering Questions

- Search the brain before answering.
- Prefer source files in `01-projects/`, `02-areas/`, `03-resources/`, and `90-inbox/`.
- For project, area, and resource questions, read the folder `README.md` when present, then the local `GENERATED.md`, then relevant `sources/`.
- Use `99-generated/` as helpful context, not as final truth.
- Cite the files you used.
- Say clearly when information is missing or stale.
- Do not invent facts.

## Adding Information

- Put new raw information in `90-inbox/` unless the user explicitly asks you to organize it.
- Follow `00-workflows/ingest-data.md`.
- Add YAML frontmatter when creating Markdown files.
- Keep files small and focused.

## Processing Inbox

- Follow `00-workflows/process-inbox.md`.
- Preserve source context.
- Move or summarize inbox items into the correct PARA location.
- Update relevant generated summaries when useful.
- Do not silently delete source material.
