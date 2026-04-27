---
name: drop-initiative
description: >-
  Alias skill for initiative-level dropping. Use when the user says drop
  initiative or retire initiative. Follow remove-initiative workflow.
---

# Drop Initiative

Use this skill when the user asks to **drop** an initiative.

This is an alias of `skills/remove-initiative/SKILL.md` and should follow that workflow exactly, including:

- Option handling when active ideas still exist
- Archiving the initiative bundle or clearing projects first
- Cleaning `DASHBOARD.md` initiative and approval rows
- Preserving history via archive bundles rather than inline `ideas.md` tables

If any instruction here conflicts with `remove-initiative`, `remove-initiative` is the source of truth.
