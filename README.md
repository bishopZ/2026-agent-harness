# 2026 Agent Harness

**A lifecycle system for working with AI agents — combining [Karpathy's](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) persistent wiki architecture with [Osmani's](https://github.com/addyosmani/agent-skills) structured skill discipline.**

For developers and power users who want human-approved stages, fair prioritization across every project they're managing, and a knowledge base that never disappears between sessions.

![Version](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/bishopZ/2026-agent-harness/main/docs/badges/version.json)

---

## Why

AI editors default to the shortest path — without structure, every session starts over and prior context evaporates. This system applies Karpathy's wiki pattern (persistent structured memory that accumulates across sessions) together with Osmani's skill discipline (staged workflows with explicit human verification gates). The result: every idea moves through the same 11-stage pipeline, and nothing advances without your sign-off.

---

## What you get

Clone the repo and you have a complete working system on disk. No server, no install step, no build.

| What             | Count | Where                                                                                      |
| ---------------- | ----- | ------------------------------------------------------------------------------------------ |
| Skills           | 13    | `skills/`                                                                                  |
| Rules            | 6     | `rules/`                                                                                   |
| Agent runbooks   | 3     | `agents/`                                                                                  |
| Lifecycle stages | 11    | `IDEA_LIFECYCLE.md`                                                                        |
| Core docs        | 5     | `USER.md`, `DASHBOARD.md`, `SYSTEM_OVERVIEW.md`, `IDEA_LIFECYCLE.md`, `PRIORITIZATION.md` |

_Counts current as of v2.0.0. Update on MINOR version bumps that add skills or rules._

---

## What makes it different

Three things set it apart from the peer repos in this space.

| Differentiator                        | What it means                                                                                                                                                      |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Human-approved at every stage         | 11 stages from brief to growth; nothing advances without your explicit sign-off. No peer repo in the benchmark scan does this — all default to autonomous chaining. |
| Fair prioritization across everything | A combined score (`staleness × 2 + tier + project + idea`) ensures lower-priority initiatives are not starved. The system tracks what has waited longest.          |
| Everything is a Markdown file         | No SQLite, no embeddings, no hosted memory. Every rule, stage, and decision record is a plain file: inspectable, diffable, and yours to own.                       |

---

## Quick start

```bash
git clone https://github.com/bishopZ/2026-agent-harness
```

Open the repo in your AI-enhanced editor (Cursor, Windsurf, VS Code + Copilot, or similar).

Tell your agent:

> "Run the bootstrap skill."

The agent will interview you with a short series of questions and personalize the system for your work. For a full walkthrough, see [SYSTEM_OVERVIEW.md](SYSTEM_OVERVIEW.md).

---

## How it works

Every idea in your system moves through an 11-stage pipeline — from a raw Backlog entry through Brief, Pressure Test, Research, PRD, Design, Build, Evaluation, Launch, Marketing, and Growth — with a human approval gate at each transition. The agent runs the lifecycle stages; you decide what advances. The result is a cumulative wiki that knows what each project looked like at every stage and why each decision was made. See [IDEA_LIFECYCLE.md](IDEA_LIFECYCLE.md) for the complete pipeline.

---

## Deeper reading

- [SYSTEM_OVERVIEW.md](SYSTEM_OVERVIEW.md) — full architecture, folder conventions, and wiki rules
- [IDEA_LIFECYCLE.md](IDEA_LIFECYCLE.md) — all 11 stages with templates, gates, and acceptance criteria
- [PRIORITIZATION.md](PRIORITIZATION.md) — how the combined score selects the next idea across initiatives
- [wiki/](wiki/) — initiative knowledge base: market research, positioning, and strategy

---

## Contributing & version

Fork the repo and adapt it to your own initiatives. The system is intentionally generic — swap out initiative names, tier points, and skill scripts. See [CHANGELOG.md](CHANGELOG.md) for release history and the semver policy. Current version: read the [`VERSION`](VERSION) file.

---

## License

[MIT License](https://opensource.org/licenses/MIT). No `LICENSE` file is bundled in this repo — the link is the reference.
