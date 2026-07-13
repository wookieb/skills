---
name: review-implementation
description: Review implementation for a Linear issue when the user invokes /review-implementation or asks to review issue work and update acceptance criteria.
---

# Review Implementation

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS`, current branch name, or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Run `/code-review $ARGUMENTS`, preserving `$ARGUMENTS` exactly.
3. Read the Linear issue and list every acceptance criterion with its current done state.
4. For each unchecked acceptance criterion, inspect the code-review result and current code until there is direct evidence that the criterion is satisfied. If evidence is missing, conflicting, or unclear, leave it unchecked.
5. Mark only satisfied acceptance criteria as done in Linear.
6. Report which criteria were marked done and which remain unchecked, with the blocking evidence gap for each unchecked criterion.

## Done Gate

An acceptance criterion is done only when the implementation satisfies the criterion exactly and no code-review finding contradicts it.

## Completion

- One Linear issue resolved.
- `/code-review` completed.
- Every acceptance criterion checked against review results and code evidence.
- Only actually satisfied criteria marked done in Linear.
- Remaining unchecked criteria reported with evidence gaps.
