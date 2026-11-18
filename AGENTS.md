# Agent Instructions

This folder is a second brain: a folder-backed knowledge base.

Follow `BRAIN.md`.

## Defaults

- Search before answering.
- Cite source files.
- Keep edits small and understandable.
- Prefer appending structured notes over rewriting canonical knowledge.
- Do not treat `99-generated/` as source truth.
- For project, area, and resource questions, read the folder `README.md` when present, then the local `GENERATED.md`, then relevant `sources/`.
- Do not reorganize folders unless the user asks or the current structure clearly violates `BRAIN.md`.
- For ingestion, follow `00-workflows/ingest-data.md` or `00-workflows/import-with-connectors.md`.
- For inbox processing, follow `00-workflows/process-inbox.md`.

## Commits

If this folder is a Git repository, use clear commit messages:

- `inbox: add client note`
- `process: classify inbox items`
- `generate: update project summaries`
- `sync: update second brain YYYY-MM-DD`
- `maintenance: clean metadata`
