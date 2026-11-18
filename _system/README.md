# System

Machine state for the routines. The AI reads and updates these files. You rarely need to edit them.

- `sync-state.md`: the last import checkpoint of each source, so an import only fetches new items.
- `gmail-ignore.json`: email the import skips (newsletters, invoices, notifications). Edit it to fit your mailbox.
- `morning-brief-actions.json`: the state of actions from earlier morning briefs.
- `morning-brief-history.jsonl`: the briefs that were sent, one per line.

Never store passwords, API keys, or tokens here.
