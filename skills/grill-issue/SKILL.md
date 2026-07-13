---
name: grill-issue
description: Grill a Linear issue when the user invokes /grill-issue or asks to stress-test one issue before implementation.
---

# Grill Issue

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS`. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Move the issue to `grilling` status. If that status does not exist, ask before choosing another status.
3. Run `/grill-with-docs $ARGUMENTS`, preserving `$ARGUMENTS` exactly.

## Completion

- One Linear issue resolved.
- Issue moved to `grilling` or user approved a substitute status.
- `grill-with-docs` started with unchanged `$ARGUMENTS`.
