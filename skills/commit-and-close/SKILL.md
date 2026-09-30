---
name: commit-and-close
description: Commit completed Linear issue work when the user invokes /commit-and-close or asks to commit and close an issue.
---

# Commit And Close

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS` or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Read the Linear issue and list every acceptance criterion with its done state.
3. Require every acceptance criterion to be marked done in Linear. If any criterion is not marked done or its state is unclear, stop before committing, report the unchecked criteria, and suggest running `/review-implementation $ARGUMENTS`.
4. Inspect git status and diff. Stop before committing if unrelated user changes would be included.
5. Commit the scoped issue changes after acceptance criteria are satisfied. Do not use `--no-verify` unless the user explicitly asks.
6. Close the Linear issue only after the commit succeeds.

## Completion

- One Linear issue resolved.
- Every acceptance criterion is marked done in Linear.
- Scoped commit succeeded.
- Linear issue closed after commit.

## Rules

- Do not run `/code-review`.
- Do not modify acceptance criteria.
- Do not infer acceptance-criterion completion from code, tests, or review evidence; use the done state in Linear.
