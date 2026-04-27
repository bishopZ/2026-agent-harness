---
name: drop-project
description: >-
  Alias skill for project-level dropping. Use when the user says drop project,
  retire project, or dissolve project. Follow remove-project workflow.
---

# Drop Project

Use this skill when the user asks to **drop** a project.

This is an alias of `skills/remove-project/SKILL.md` and should follow that workflow exactly, including:

- Option handling for active ideas (archive, move, delete)
- Recording dropped ideas in `history/dropped-history.md` (not inline in `ideas.md`)
- Keeping `ideas.md` `## Done` and `## Dropped` sections as link-only pointers
- Updating project-level history in `## Completed Projects` or `## Dropped Projects`
- Cleaning up `DASHBOARD.md` approval rows and wiki bookkeeping

If any instruction here conflicts with `remove-project`, `remove-project` is the source of truth.
