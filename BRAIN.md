# Brain Operating Rules

This folder is a second brain. It should stay simple, searchable, and useful for both humans and AI agents.

## About This Brain

Fill this in. The AI reads it before every task, so it knows whose brain this is.

- **Who:** <your name or company, and what you do in one sentence>
- **People:** <who works in this brain, and their roles>
- **Clients and work:** <what kind of clients and projects you have>
- **Language:** <the language for summaries and briefs, for example Dutch (nl-BE)>
- **Sources:** <where information comes from: Gmail, Outlook, Google Drive, calendar, WhatsApp, meeting notes>

## Structure

- `00-workflows/`: documented processes for ingesting, processing, and summarizing knowledge.
- `01-projects/`: work with a concrete outcome, grouped by lifecycle (`active/`, `seeding/`, `archived/`).
- `02-areas/`: ongoing responsibilities that need to stay healthy.
- `03-resources/`: useful reference material, research, inspiration, and reusable knowledge.
- `04-archive/`: inactive material and old notes.
- `90-inbox/`: raw unprocessed input.
- `99-generated/`: AI-generated summaries, indexes, dashboards, and rollups.
- `_templates/`: reusable file templates.
- `_system/`: sync checkpoints and routine memory.

## Core Rules

- New raw information goes into `90-inbox/`.
- Manual ingestion follows `00-workflows/ingest-data.md`.
- Imports through AI connectors follow `00-workflows/import-with-connectors.md`.
- Inbox processing follows `00-workflows/process-inbox.md`.
- The daily or weekly update follows `00-workflows/daily-routine.md`.
- Processed knowledge belongs in PARA: projects, areas, resources, or archive.
- Generated files are derived views, not source of truth.
- Project, area, and resource folders keep a `README.md` (current state, owned by humans) and a `GENERATED.md` (summary of the sources, maintained by the AI).
- When researching a project, area, or resource, read its `README.md`, then `GENERATED.md`, then source files as needed.
- Generated summary decisions follow `00-workflows/summary-policy.md`.
- If a fact is wrong, correct the original source file first, then regenerate summaries.
- Prefer small Markdown files with YAML frontmatter. Use the templates in `_templates/`.
- Use clear filenames: `YYYY-MM-DD-topic.md` for dated notes.
- When answering questions, search the brain first and cite the files used.
- Do not invent missing facts. Say when information is missing, stale, or uncertain.
- Never delete source material. Move it or mark it.

## PARA Rules

### Projects

Use `01-projects/` for work with an outcome or delivery target.

- `active/`: current delivery or maintenance.
- `seeding/`: early, possible, or not-yet-confirmed work, like a lead or a proposal.
- `archived/`: completed or inactive work.

Examples: client assignments, a website redesign, launching a new offer, internal projects.

A fixed-scope assignment is a project. Decide once how you handle long-running clients (an area, or one active project per client) and write that rule here.

### Areas

Use `02-areas/` for ongoing parts of the business.

Examples: brand, sales, finance, operations, delivery.

### Resources

Use `03-resources/` for material that may be useful later.

Examples: research, competitor notes, tools, inspiration, events, external articles.

### Archive

Use `04-archive/` for inactive or historical material that should remain searchable.

## Generated Summary Rules

Always generate summaries for:

- active clients
- active projects
- global open loops
- weekly business context
- important business areas

Generate optional summaries when something becomes large, frequently used, or decision-heavy.

Do not generate summaries for tiny one-off notes unless they are strategically important.

## Privacy

- Do not store passwords, API keys, or tokens in this brain.
- Only import what is useful. Skip invoices, newsletters, and notifications (see `_system/gmail-ignore.json`).
- Know which AI provider reads this folder, and what your clients agreed to.
