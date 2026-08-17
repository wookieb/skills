---
name: write-skill
description: Write or revise an agent skill.
disable-model-invocation: true
---

# Write Skill

Create a small, deterministic workflow. Prefer a skill only when a repeatable process changes agent behavior.

## Process

1. Identify invocation.
   - Model-invoked: needs autonomous discovery or use by another skill. Write a precise `description` with distinct triggers.
   - User-invoked: set `disable-model-invocation: true`; keep its description human-facing and brief.
   - Completion: invocation mode and trigger boundary are explicit.

2. Define the workflow.
   - State actions in execution order.
   - Give each action a checkable completion criterion.
   - Name the inputs, outputs, and decisions which change the path.
   - Completion: another agent can run the workflow without inventing its sequence.

3. Place information by need.
   - Keep required steps and rules in `SKILL.md`.
   - Move conditional, detailed reference to named sibling files; link it with a pointer that says when to read it.
   - Keep each rule in one authoritative location.
   - Completion: the main path is legible without loading irrelevant reference.

4. Set the boundary.
   - Durable project rules belong to conventions; skills keep workflows and point there.
   - Do not copy coding standards, architecture rules, or product facts into a skill. Link their authoritative convention or document instead.
   - Completion: skill contains process only; project rules remain authoritative elsewhere.

5. Prune and validate.
   - Remove duplicate triggers, stale guidance, and statements which do not alter behavior.
   - Use lowercase hyphenated `name`, matching directory name, with `SKILL.md` as the filename.
   - Check frontmatter and every completion criterion.
   - Completion: each remaining line changes invocation or execution behavior.

## Design Rules

- Split a skill when it has an independent trigger or later steps cause premature completion of earlier work.
- Prefer a compact leading word over repeated explanation when it reliably anchors the desired behavior.
- Use one branch per distinct workflow. Do not add synonyms as separate triggers.
- Reference specific paths, commands, and templates when they determine the workflow.
