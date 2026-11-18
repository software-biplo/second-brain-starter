# Second Brain Starter

A second brain made of plain folders and Markdown files. You own it, and any AI can work in it.

This starter kit uses the same structure as Chantal, the second brain of Biplo.

## Three Principles

1. **No lock-in.** Everything is a plain Markdown file in a folder you own. Any editor opens it. Any AI reads it.
2. **The right structure.** New information enters through the inbox, then moves into PARA: projects, areas, resources, archive. Raw sources stay separate from AI summaries.
3. **Your AI of choice.** The rules live in `BRAIN.md`, not in an app. `AGENTS.md` and `CLAUDE.md` both point to it, so Claude, ChatGPT/Codex and other agents work the same way.

## Quick Start

1. Put this folder on your computer.
2. Choose how to keep it safe: a private GitHub repository or a cloud-synced folder (Google Drive, OneDrive, iCloud, Dropbox). Do not use both on the same folder.
3. Open `BRAIN.md` and fill in "About This Brain".
4. Rename the folders in `02-areas/` to fit your business.
5. Open the folder in an AI app that can read and write local files.
6. Put a few things in `90-inbox/` and ask: "Process my inbox according to `00-workflows/process-inbox.md`."
7. Ask a question: "What do we know about <client>?"

Then make it a habit with `00-workflows/daily-routine.md`.

## Folder Map

| Folder | What goes in it |
| --- | --- |
| `00-workflows/` | How information moves through the brain. The AI follows these. |
| `01-projects/` | Work with an end: `active/`, `seeding/` (possible, not confirmed), `archived/`. |
| `02-areas/` | Ongoing responsibilities without an end date: sales, finance, operations. |
| `03-resources/` | Reference material: research, tools, inspiration, events. |
| `04-archive/` | Inactive material that stays searchable. |
| `90-inbox/` | Everything new arrives here first. |
| `99-generated/` | AI summaries, indexes and overviews. Useful, but not the source of truth. |
| `_templates/` | The fixed shape of new files. |
| `_system/` | Sync checkpoints and memory for the routines. |

Each project, area and resource folder has:

- `README.md`: the current state, owned by you.
- `GENERATED.md`: the summary the AI keeps up to date.
- `sources/`: the raw material. Never edited, only added to.

## Three Levels

| Level | Import | Routine |
| --- | --- | --- |
| 1. By hand | Forward, save or drag things into `90-inbox/`. | Once a week you ask the AI to process the inbox. |
| 2. Connectors | The Gmail, Drive or Calendar connector of your AI app writes into `90-inbox/`. | A scheduled task in your AI app, every morning. |
| 3. Own automation | Your own sync scripts. | A server runs everything and sends a morning brief. |

This kit covers level 1 and level 2. Level 3 is what Chantal does.

## Git Or Cloud Sync

- **Cloud sync** is the easiest. You get a backup and version history without extra tools.
- **Git (GitHub)** gives you a clear history of every change the AI made, an easy undo, and a path to a server later. Use a **private** repository. GitHub Desktop works without a terminal, or you can ask the AI to "commit and push my changes".
- Do not put a Git repository inside a cloud-synced folder. The two ways of syncing conflict.
