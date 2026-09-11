---
name: grilling-outcome
description: Maintain the single `Grilling outcome` Linear comment for an issue after a grilling round or when another skill needs its current outcome recorded.
---

# Grilling Outcome

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS`, current branch name, or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Synthesize every answered grilling question, decision, constraint, open risk, and follow-up into the current outcome. Do not include unanswered questions.
3. Capture every code snippet discussed during grilling that defines or changes an interface, class, type, or other codebase-design decision. Keep each snippet in a fenced code block. Preserve its language and essential signatures.
4. Include a `## Grilling outcome` section. Include `## Codebase design` when grilling established codebase-design content, such as module depth, interface, class, type, seam, adapter, leverage, locality, or a design decision about them. Put every captured code snippet in this section.
5. Put the same relevant codebase-design snippets in each Linear issue created during the grilling session. Include them in the issue description or a dedicated issue comment. Do this before finalizing the outcome.
6. List the issue's comments containing `## Grilling outcome`. If none exist, create one dedicated outcome comment. If one exists, update it. If several exist, retain the oldest, update it with the synthesized outcome, and delete every duplicate. If deletion is unavailable, remove `## Grilling outcome` from every duplicate and state that the oldest comment is canonical.
7. Re-read the issue comments and every issue created during the session. Confirm exactly one comment contains `## Grilling outcome`, its contents match the current grilling session, and each created issue contains its relevant design snippets.

## Completion

- One Linear issue resolved.
- Exactly one issue comment contains `## Grilling outcome`.
- The outcome reflects every answered grilling point.
- `## Codebase design` exists only when codebase-design content exists.
- Every discussed interface, class, type, and other codebase-design snippet appears in `## Codebase design`.
- Every Linear issue created during grilling contains its relevant codebase-design snippets.
