---
name: document-pattern
description: Document a project code pattern as an implementation skill and a verifiable convention.
disable-model-invocation: true
---

# Document Pattern

Create one project skill and one linked convention for the requested code pattern.

## Inputs

Require a pattern name. Convert it to lowercase kebab case as `[patternName]`.

Gather these facts before writing:

- Pattern purpose and use cases.
- Existing implementations that represent the pattern.
- Required structure, naming, dependencies, registration, tests, and verification commands.
- Existing project conventions that constrain the pattern.

Ask for missing facts. Do not invent project-specific paths, APIs, commands, or rules.

## Outputs

Create or revise these artifacts:

- A skill named `pattern-[patternName]`.
- A convention named `pattern-[patternName].md`.
- One link to the convention in the conventions index.

Locate existing project skill and convention infrastructure before writing. Do not assume paths. Preserve a working relative link between the skill and convention.

## Workflow

1. Inspect representative implementations and applicable conventions.
   - Prefer maintained production examples.
   - Record facts that distinguish this pattern from similar patterns.
   - Do not document optional style preferences as requirements.

2. Write the skill named `pattern-[patternName]`.
   - Set frontmatter `name: pattern-[patternName]`.
   - Use a precise description that states when to invoke `/pattern-[patternName]`.
   - State the pattern purpose and boundary.
   - Link to `pattern-[patternName].md` before implementation and in final verification.
   - Give ordered implementation steps.
   - Include exact paths, names, APIs, registration steps, tests, and commands only when project evidence supports them.
   - End with a completion section. Require the convention checklist to pass.

3. Write the convention named `pattern-[patternName].md`.
   - Give the document a descriptive title ending in `Pattern`.
   - State scope and non-goals.
   - Define required structure and implementation rules.
   - Define ownership and integration boundaries.
   - Define required test coverage.
   - End with `## Validation Checklist`.
   - Make each checklist item objective and independently verifiable.
   - Use `[ ]` Markdown checkboxes.

4. Update the conventions index.
   - Add one relative Markdown link: `[pattern-[patternName].md](pattern-[patternName].md)`.
   - Keep existing index ordering and link style.
   - Do not add duplicate links.

5. Verify the documentation.
   - Confirm skill frontmatter name is exactly `pattern-[patternName]`.
   - Confirm skill name, convention name, and index link use the same pattern name.
   - Confirm the convention link resolves from the skill file.
   - Confirm every skill requirement has one matching convention rule or checklist item.
   - Confirm each checklist item can be checked from code, tests, or a command.
   - Remove rules without project evidence.

## Completion

- `/pattern-[patternName]` explains how to implement the pattern.
- `pattern-[patternName].md` verifies the implementation.
- Conventions index links the convention.
- Skill and convention contain no invented project facts.
