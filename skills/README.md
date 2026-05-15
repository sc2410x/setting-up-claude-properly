# Skills (project-scoped)

These skills auto-trigger when Claude is working inside this project. They do not run in other projects.

## How a skill is structured

```
skills/
└── my-skill/
    └── SKILL.md
```

`SKILL.md` opens with YAML frontmatter:

```yaml
---
name: my-skill
description: One-paragraph description Claude reads to decide when to trigger this skill. Be specific about what tasks should trigger it.
---
```

Then the rest of the file is plain markdown — instructions, examples, checklists, whatever the skill needs.

## How to add a new skill

1. Create the folder: `skills/your-skill-name/`
2. Add `SKILL.md` with frontmatter (name + description) at the top
3. Write the skill body in plain markdown
4. That's it. Claude reads it on the next session.

## Project-scoped vs global

Global skills live at `~/.claude/skills/` and trigger in any project. Project-scoped skills live here and trigger only when Claude is working inside this project.

**Use project-scoped when:**
- The skill is specific to this project's domain
- The skill references files inside this project
- You want the skill to travel with the project if it ever moves to a shared repo

**Use global when:**
- The skill is genuinely cross-project (e.g. a personal coding helper)
- The skill operates on projects rather than within them (e.g. the project migrator)

If unsure, default to project-scoped. Global skills are easier to lose track of.
