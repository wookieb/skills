---
name: review-implementation
description: Review implementation for a Linear issue when the user invokes /review-implementation or asks to review issue work and update acceptance criteria.
---

# Review Implementation

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS`, current branch name, or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Read the Linear issue, every parent issue, and their comments. Extract every `## Grilling outcome` comment as implementation and design context.
3. Select the review target. If `$ARGUMENTS` contains a commit point, run `/code-review $ARGUMENTS`, preserving `$ARGUMENTS` exactly. If no commit point is provided, review the current working tree: staged and unstaged changes against `HEAD`, plus every untracked file.
4. For a working-tree review, apply the same Standards and Spec review axes as `/code-review`. Use the Linear issue and parent grilling outcomes as spec sources.
5. List every acceptance criterion on the Linear issue with its current done state.
6. For each unchecked acceptance criterion, inspect the review result and current code until there is direct evidence that the criterion is satisfied. If evidence is missing, conflicting, or unclear, leave it unchecked.
7. Mark only satisfied acceptance criteria as done in Linear.
8. Report which criteria were marked done and which remain unchecked, with the blocking evidence gap for each unchecked criterion.

## Done Gate

An acceptance criterion is done only when the implementation satisfies the criterion exactly and no code-review finding contradicts it.

## Completion

- One Linear issue resolved.
- Every parent issue and its `## Grilling outcome` comments read.
- A commit-point review or working-tree review completed.
- Every acceptance criterion checked against review results and code evidence.
- Only actually satisfied criteria marked done in Linear.
- Remaining unchecked criteria reported with evidence gaps.
