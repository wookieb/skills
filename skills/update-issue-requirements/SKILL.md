---
name: update-issue-requirements
description: Apply a scope or requirement change to the current Linear issue.
disable-model-invocation: true
---

# Update Issue Requirements

## Workflow

1. Use the Linear issue already linked to this session when exactly one exists. Only when no issue is linked, resolve one from an issue key in `$ARGUMENTS` and link it to this session. If resolution does not identify exactly one issue, ask for one issue key. Stop until the user provides it.
2. Use Linear MCP tools to read the current description and all comments before mutation.
3. Extract the current user direction. Treat it as authoritative over conflicting earlier issue text and comments. Identify each affected decision and its rationale.
4. Patch the existing issue description. Preserve unrelated content. Update every affected section: Goal, Public contract, Storage or behavior requirements, Nest or configuration scope, Out-of-scope list, and Acceptance criteria. Add an affected section only when it does not exist.
5. Make the description the current source of truth. For each changed or new acceptance criterion, use an unchecked checkbox. Preserve checkbox state for unchanged criteria. Leave every criterion unchecked when its text changes. Do not mark any criterion complete.
6. Add one concise Linear comment headed `## Scope update`. Record the user direction, its rationale, and superseded decisions.
7. Modify the existing issue only. Do not create an issue or modify code, tests, status, branch, or commits.
8. Re-read the Linear issue with Linear MCP tools. Verify the description contains every requested decision. Report the resolved issue identifier and title, changed sections, changed or new acceptance criteria, and every remaining unchecked criterion.
