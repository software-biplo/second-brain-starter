# Workflow: Import With Connectors

Use this workflow when an AI app imports new information through its connectors, for example Gmail, Outlook, Google Drive, or Google Calendar.

## Principle

The connector is only the pipe. The data lands in this folder, in this format.

If you switch AI apps, connect the pipe of the new app. The brain stays the same.

## Requirements

- An AI app that can use connectors and write files in this folder.
- The connectors are connected in that app. Read access is enough.

## Steps

1. Read `_system/sync-state.md` for the last checkpoint of each source.
2. For each source, fetch only items newer than the checkpoint. On the first run, use a short window, for example the last 14 days.
3. Skip low-value items. For email, apply `_system/gmail-ignore.json`.
4. Check that the item is not in the brain yet: search for its `source_id` in the whole brain, because processed items move to `sources/` folders.
5. Write one Markdown file per item in the right inbox folder:
   - email threads: `90-inbox/emails/`
   - documents: `90-inbox/files/`
   - calendar events: `90-inbox/meetings/`
6. Use `_templates/inbox-item.md` and add the source metadata below.
7. Update `_system/sync-state.md` with the new checkpoint, the number of imported items, and the number of skipped items.
8. Do not process the items yet. Processing follows `00-workflows/process-inbox.md`.

## Source Metadata

Every imported item needs enough metadata to prevent duplicate imports:

```md
---
type: inbox_item
source: gmail
source_account:
source_id:
source_url:
source_updated_at:
imported_at:
status: unprocessed
related_client:
related_project:
tags: []
---
```

Use `source: google_drive`, `source: google_calendar`, or `source: outlook` for other sources.

For Drive items, also add the folder path. Folder names like `Clients/Active/` or `Clients/Archive/` help to classify the item later:

```md
source_folder_paths: []
```

## What To Keep

- **Email:** from, to, date, subject, attachment names, and the raw body of the thread.
- **Document:** title, folder path, link, and the text. For a very long document, keep a summary and the link.
- **Calendar event:** title, start and end, attendees, location, and description.

Do not import Drive folders as items. Folders are only used for the folder path.

## Filenames

```txt
YYYY-MM-DD-short-subject.md
```

Use the date of the source, not the import date.

## Agent Prompt

```txt
Import new information into my second brain.

Follow `00-workflows/import-with-connectors.md`.
Read `_system/sync-state.md` and import only items newer than each checkpoint.
Use my Gmail, Google Drive, and Google Calendar connectors.
Skip items that match `_system/gmail-ignore.json`, and items that are already in the brain.
Write each item to `90-inbox/` with full source metadata.
Update `_system/sync-state.md`.
Do not process the inbox yet.
Report what you imported and what you skipped.
```
