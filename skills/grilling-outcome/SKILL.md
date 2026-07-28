---
name: grilling-outcome
description: Maintain the single `Grilling outcome` Linear comment for an issue after a grilling round or when another skill needs its current outcome recorded.
---

# Grilling Outcome

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS`, current branch name, or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Synthesize every answered grilling question, decision, constraint, open risk, and follow-up into the current outcome. Do not include unanswered questions.
3. Include a `## Grilling outcome` section. Include `## Codebase design` only when the grilling established codebase-design content, such as module depth, interface, seam, adapter, leverage, locality, or a design decision about them.
4. List the issue's comments containing `## Grilling outcome`. If none exist, create one dedicated outcome comment. If one exists, update it. If several exist, retain the oldest, update it with the synthesized outcome, and delete every duplicate. If deletion is unavailable, remove `## Grilling outcome` from every duplicate and state that the oldest comment is canonical.
5. Re-read the issue comments. Confirm exactly one comment contains `## Grilling outcome` and its contents match the current grilling session.

## Completion

- One Linear issue resolved.
- Exactly one issue comment contains `## Grilling outcome`.
- The outcome reflects every answered grilling point.
- `## Codebase design` exists only when codebase-design content exists.
