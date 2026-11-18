# Workflow: Morning Brief

A short message about what needs attention **today**: a greeting and one to three concrete actions or questions when warranted. One useful item is enough. On a quiet day, one line is enough.

Write it in the language set in `BRAIN.md`. Show it in the chat, or send it where you read it (mail, chat app) if your AI app can do that.

## Context

Gather, after the daily routine:

- summaries that changed today (a changed file is not proof of new progress)
- all active projects in `01-projects/active/`, also the ones without changes
- meetings in the next seven days
- `_system/morning-brief-actions.json`: the state of earlier actions and your corrections
- the last seven briefs in `_system/morning-brief-history.jsonl`

For each selected project, read its `README.md`, `GENERATED.md`, and relevant sources. Generated open loops can be stale. Newer source facts and your corrections take precedence.

## Select Today's Actions

For each candidate, decide:

- **Why today?** A due action, a client blocker, preparation needed now, or a follow-up whose review date has arrived. A future date or a recent mention alone is not enough.
- **What is the actual next step?** Respect who owns it and what already happened.
- **Was it already in a brief?** Compare meaning, not wording, with earlier briefs.
- **Does it add anything beyond the calendar?** "You have a meeting" is not an action. A meeting only qualifies with an open decision, a deliverable due today, or a change.

Put client delivery and blockers first, then actions due today, then preparation and follow-ups.

Exclude:

- items that wait on someone else, before a sensible review date
- solved threads (request, done, thanks)
- earlier briefs as evidence (they are derived messages)
- archived projects and speculative tasks without a reason for today

Repeat an action only when the evidence changed, an agreed reminder is due, or the urgency increased.

On a quiet day, write one simple line, for example: "Good morning! Nothing urgent today." Do not fill space.

## Action Memory

Keep `_system/morning-brief-actions.json` up to date. Each action has an `id`, a project, the next step, source files, and one state:

- `actionable`: we can and should act.
- `needs_status`: a short status question is needed.
- `waiting`: another person owns the next step.
- `meeting_booked`: the topic is on the calendar.
- `deferred`: intentionally later.
- `done`: closed. Reopen only with newer evidence.

Use `review_after` for an internal check date. After a brief, add `last_briefed_at` to the selected actions, and append the brief to `_system/morning-brief-history.jsonl` as one line: `{"date": "YYYY-MM-DD", "text": "..."}`.

## Message Shape

- Plain language, one line per action or question, names when known.
- Readable in 15 seconds: 40 to 80 words, fewer if enough.
- No file paths, state labels, or explanations of what was left out.

## Agent Prompt

```txt
Write my morning brief. Follow `00-workflows/morning-brief.md`.

Read the action memory, the last briefs, today's changes, upcoming meetings, and all active projects.
Check the candidates against README.md, GENERATED.md, and the sources.
Only include actions with a reason for today. Do not repeat calendar entries.
Write a greeting and one to three actions or questions. On a quiet day, one line.
Update the action memory and the brief history.
```
