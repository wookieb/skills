---
name: acceptance-criteria-status
description: Show every acceptance criterion and status for the current Linear issue. Explain each unsatisfied criterion.
---

# Acceptance Criteria Status

## Workflow

1. Resolve the Linear issue from `$ARGUMENTS`, current branch name, or session context. If resolution is ambiguous or missing, ask for one issue key and stop until provided.
2. Read the Linear issue, its comments, and every acceptance criterion with its done state.
3. Report every criterion with status `✅ satisfied` when its Linear checkbox is done. Report status `❌ unsatisfied` when its checkbox is not done.
4. For each unsatisfied criterion, inspect the issue, its comments, current code, and relevant tests. Explain what the criterion requires, current implementation status, test status, and why it remains unsatisfied. State when evidence is missing or conflicting.
5. Do not modify Linear, code, tests, or acceptance criteria.

## Output

- Issue identifier and title.
- One row per acceptance criterion.
- `Criterion`: exact acceptance-criterion text.
- `Status`: `✅ satisfied` or `❌ unsatisfied`.
- `Explanation`: required for every `❌ unsatisfied` criterion. Include criterion intent, implementation status, test status, and reason it remains unsatisfied.

## Rules

- Linear checkbox state determines status.
- Do not infer `✅ satisfied` from code or test evidence when Linear leaves the criterion unchecked.
- Do not omit criteria with incomplete, unclear, or missing implementation evidence.
