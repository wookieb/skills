---
name: finish-grilling-issue
description: Finish a Linear issue grilling session when the user invokes /finish-grilling-issue or asks to complete grilling.
---

# Finish Grilling Issue

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS`, current branch name, or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Check every question, challenge, or follow-up from the grilling session. If any are unanswered, stop and report what still needs an answer.
3. Ensure the grilling outcome is saved against the Linear issue and up to date. If it is missing or stale, update Linear before continuing.
4. Inspect git status. If any files changed during the grilling session, commit only those grilling-session changes and push the commit.
5. Move the Linear issue to `ready for agent` status. If that status does not exist, ask before choosing another status.

## Completion

- One Linear issue resolved.
- Every grilling question, challenge, and follow-up answered.
- Grilling outcome saved against Linear and current.
- Grilling-session file changes committed and pushed, or no such file changes existed.
- Issue moved to `ready for agent` or user approved a substitute status.
