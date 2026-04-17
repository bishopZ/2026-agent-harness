# Changelog

All notable changes to the Initiative & Idea Management System are recorded here.

This file follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) conventions.
Version numbers follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html) as applied to a knowledge system:

- **MAJOR** — breaking changes to file structure, stage names, scoring formula, or naming conventions that require migrating existing initiative data.
- **MINOR** — new skills, new lifecycle stages, new wiki domain types, or new system-level documents that are backward-compatible.
- **PATCH** — clarifications, copy fixes, non-breaking adjustments to templates or instructions.

---

## [Unreleased]

_Changes staged for the next release go here._

---

## [1.0.0] — 2026-04-14

### Added

- Core system documents: `SYSTEM_OVERVIEW.md`, `IDEA_LIFECYCLE.md`, `DASHBOARD.md`, `PRIORITIZATION.md`, `USER.md`, `README.md`, `AGENTS.md`.
- Full 11-stage idea lifecycle: Backlog → Brief → Pressure Test → Research → PRD → Design → Build → Evaluation → Launch → Marketing → Growth.
- Approval-gate pattern at every stage; `In Review` status and `Awaiting your approval` queue in `DASHBOARD.md`.
- Combined scoring formula: `score = staleness_days × 2 + tier_points + project_points + idea_points`.
- Initiative-level priority with tier points and staleness-based fairness (cap at 90 days).
- Per-initiative wiki structure: `index.md`, `log.md`, domain subfolders, `.archive/` for retired pages.
- Three wiki domain layouts: business, personal brand, creative project.
- Four wiki operations: Ingest, Query, Update, Lint (plus one-time Init).
- YAML front-matter standard for wiki pages (`domain`, `type`, `tags`, `related_documents`, `status`, `version`, `created`, `modified`).
- Three default initiatives: `My Company` (business), `My Personal Life` (personal brand), `My Hobby` (creative project).
- Skills library: `add-idea`, `add-initiative`, `add-project`, `approve-idea`, `bootstrap`, `complete-idea`, `drop-idea`, `health-check`, `import`, `next-idea`, `remove-initiative`, `remove-project`, `update`.
- `/raw/` drop zone, per-initiative `sources/` (immutable), and `outputs/` folders.
- `/archive/` for completed or dropped work bundles.
- `VERSION` file tracking system version.

[Unreleased]: https://github.com/bishopZ/2026-agent-harness/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/bishopZ/2026-agent-harness/releases/tag/v1.0.0
