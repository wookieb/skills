---
name: fast-commit
description: Use as the default workflow when the user asks to commit current work. Do not use for commit-and-close.
---

# Fast Commit

## Inputs

- Current conversation.
- `$ARGUMENTS`.
- `git status --short` output.

## Workflow

1. Run `git status --short`. Record every changed path and its status. Do not read Git diff contents.
2. Select paths changed by this agent in the current work. If a changed path has an unknown author or purpose, report it and stop before staging.
3. Resolve the issue key from `$ARGUMENTS`, then current conversation. Use `NONE` when no issue key exists.
4. Build one subject from the current conversation and selected path names: `<issue-key> <type>: <imperative summary>`. Keep it short. Cover all selected work. Start the subject with the resolved issue key.
5. Run `git add -- <selected-paths>`, then `git commit -m "<subject>"`. Do not read Git diff contents. Push only when the user asks.
6. Report commit hash and subject after `git commit` succeeds.

## Completion

- Every staged path came from the current work.
- Commit subject starts with an issue key or `NONE`.
- Commit subject reflects current conversation and selected path names.
- No Git diff contents were read.
