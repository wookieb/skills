---
name: finish-grilling-issue
description: Finish a Linear issue grilling session when the user invokes /finish-grilling-issue or asks to complete grilling.
---

# Finish Grilling Issue

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS` or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Check every question, challenge, or follow-up from the grilling session. If any are unanswered, stop and report what still needs an answer.
3. Run `/grilling-outcome $ARGUMENTS`, preserving `$ARGUMENTS` exactly. Do not continue until it confirms the single current outcome comment.
4. Inspect git status. If any files changed during the grilling session, commit only those grilling-session changes and push the commit.
5. Move the Linear issue to `ready for agent` status. If that status does not exist, ask before choosing another status.

## Completion

- One Linear issue resolved.
- Every grilling question, challenge, and follow-up answered.
- One current grilling outcome comment maintained by `/grilling-outcome`.
- Grilling-session file changes committed and pushed, or no such file changes existed.
- Issue moved to `ready for agent` or user approved a substitute status.
