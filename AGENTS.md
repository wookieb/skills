# Skills Repository

Use this repository as a source catalog for the `skills` npm package.

## Source Layout

Store shared skills under `skills/<skill-name>/SKILL.md`:

```text
skills/
  my-skill/
    SKILL.md
  another-skill/
    SKILL.md
```

Each `SKILL.md` must include YAML frontmatter with `name` and `description`:

```md
---
name: my-skill
description: When this skill should be used
---
```

The package can also discover `.agents/skills/`, but keep this repo's source catalog in `skills/` for cleaner sharing across machines and agents.
