---
name: implement-issue
description: "Implement a piece of work based on a spec or set of tickets."
disable-model-invocation: true
---

Implement the work described by the user in the spec or tickets.

Before changing code, resolve the Linear issue and move it to `implementing` status. If that status does not exist, ask before choosing another status.

Use /tdd where possible, at pre-agreed seams.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once done, use /code-review to review the work.

Do not commit changes at the end. Leave the completed work uncommitted in the current branch.
