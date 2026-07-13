---
name: merge-and-close
description: Merge completed Linear issue work when the user invokes /merge-and-close or asks to merge and close an issue.
---

# Merge And Close

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS`, current branch name, or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Read the Linear issue and list every acceptance criterion with its done state.
3. Require every acceptance criterion to be marked done in Linear. If any criterion is not marked done or its state is unclear, stop before merging and report the unchecked criteria.
4. Run `yarn run compile`. Stop before merging if it fails.
5. Determine merge target: parent task branch when the Linear issue has a parent task, otherwise `master`. If the parent task branch cannot be resolved, ask for the branch name and stop until provided.
6. Inspect git status and diff. Stop before merging if unrelated user changes would be included.
7. Merge the current branch into the target branch after acceptance criteria are satisfied, compile succeeds, and the diff is scoped.
8. Close the Linear issue only after the merge succeeds.

## Completion

- One Linear issue resolved.
- Every acceptance criterion is marked done in Linear.
- `yarn run compile` passed.
- Target branch resolved without guessing.
- Merge succeeded.
- Linear issue closed after merge.

## Rules

- Do not run `/code-review`.
- Do not infer acceptance-criterion completion from code, tests, or review evidence; use the done state in Linear.
