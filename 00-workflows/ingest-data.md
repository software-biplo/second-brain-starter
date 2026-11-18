# Workflow: Ingest Data

Use this workflow when adding new raw information to the brain by hand.

## Goal

Capture information quickly, without choosing the perfect folder immediately.

## Inputs

Examples:

- emails (forwarded, or saved as a file)
- meeting notes and call notes
- voice memo transcripts
- exported WhatsApp chats ("Export chat" in WhatsApp)
- links
- screenshots, PDFs, and other files
- quick business notes and project updates

## Rule

New raw information goes into `90-inbox/` first, unless the user explicitly asks for a final location.

## Steps

1. Identify the input type.
2. Choose the closest inbox folder:
   - `90-inbox/emails/`
   - `90-inbox/meetings/`
   - `90-inbox/notes/`
   - `90-inbox/links/`
   - `90-inbox/files/`
3. Create a small Markdown file using `_templates/inbox-item.md`.
4. Add YAML frontmatter.
5. Preserve the raw source content.
6. Add any obvious tags, client, project, or source metadata.
7. If this folder is a Git repository, commit with an `inbox:` message.

For a PDF or other file, keep the original file next to a Markdown file with the same name. Put the text or a short summary in the Markdown file.

## Filename Convention

Use:

```txt
YYYY-MM-DD-short-topic.md
```

Examples:

```txt
2026-11-18-acme-website-followup.md
2026-11-18-sales-call-prospect-name.md
2026-11-18-brand-positioning-idea.md
```

## Frontmatter

Use this minimum metadata:

```md
---
type: inbox_item
source: manual
created: YYYY-MM-DD
status: unprocessed
related_client:
related_project:
tags: []
---
```

## Output

One or more files in `90-inbox/`.

## Agent Prompt

```txt
Ingest this information into my second brain.

Put it in the correct `90-inbox/` subfolder.
Use Markdown with YAML frontmatter.
Preserve the raw input.
Add only obvious metadata.
Do not process it into PARA yet.
```
