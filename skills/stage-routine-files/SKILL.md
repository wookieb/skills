---
name: stage-routine-files
description: Stage routine generated and dependency files without reviewing them.
disable-model-invocation: true
---

# Stage Routine Files

Use only when the user invokes `/stage-routine-files` after work is complete.

## Input

- Files changed by this agent during the current work.

Do not inspect file contents or Git diffs to rediscover these changes. Do not stage files whose author is uncertain.

## Workflow

1. From current-work knowledge, select changed `index.ts`, `entrysmith.config.js`, and `*.lock` files. Run `git add -- <selected-paths>`. Skip this command when no path qualifies.
2. Select each changed `package.json` only when its change is limited to dependency declarations. Run `git add -- <package-path>`. Leave it unstaged when `scripts` or any non-dependency field changed.
3. Select each changed `tsconfig.*.json` only when no `compilerOptions` value changed. Run `git add -- <tsconfig-path>`. Leave it unstaged when any `compilerOptions` value changed.
4. Run `git diff --cached --name-only -- <selected-paths>`. Confirm every selected path appears in output. Report paths left unstaged and why.

## Completion

- Every qualifying current-work file is staged.
- No uncertain, `scripts`, or `compilerOptions` change is staged by this workflow.
- No file contents or Git diff contents were read.
