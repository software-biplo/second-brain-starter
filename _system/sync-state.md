# Sync State

This file tracks import checkpoints for each source.

The AI updates this file after every successful import (see `00-workflows/import-with-connectors.md`).

## Gmail

```yaml
source: gmail
account:
last_successful_sync:
last_message_date:
last_run:
  imported: 0
  skipped: 0
notes:
```

## Google Drive

```yaml
source: google_drive
scope: # for example one shared drive or one folder
last_successful_sync:
last_modified_time:
last_run:
  imported: 0
  skipped: 0
notes:
```

## Google Calendar

```yaml
source: google_calendar
calendar:
last_successful_sync:
last_run:
  imported: 0
  skipped: 0
notes:
```
