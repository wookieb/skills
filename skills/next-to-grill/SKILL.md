---
name: next-to-grill
description: Find and claim the next Linear task to grill when the user invokes /next-to-grill or asks for the next grill-me issue.
---

# Next To Grill

## Workflow

1. Find the first Linear task matching every filter:
   - Status is `to grill`.
   - Has no `blockedBy` relation to a task in status `to-grill` or `grilling`.
   - A `blockedBy` task in status `ready-for-agent` or `implementing` does not block selection.
2. If no task matches, report that no grillable task is available and stop.
3. Mark the selected task as `grilling` before doing any other work, so no other OpenCode session picks it.
4. Run `/grill-with-docs <issue-key>`, using the selected Linear issue key.

## Completion

- One matching Linear task selected.
- Selected task marked `grilling` before grilling starts.
- `grill-with-docs` started for the selected issue key.
