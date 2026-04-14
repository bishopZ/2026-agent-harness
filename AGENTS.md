# AGENTS.md

## Overview

### What this repo is

This is a pure Markdown knowledge management system for tracking initiatives and ideas through a staged lifecycle. There is no source code, no build system, no package manager, and no runnable services. The "application" is the collection of Markdown documents and the AI assistant workflow described in `SYSTEM_OVERVIEW.md`.

### Key documents

- `SYSTEM_OVERVIEW.md` defines the system, file organization, wiki operations, and naming conventions.
- `IDEA_LIFECYCLE.md` defines every lifecycle stage, its inputs, outputs, wiki hooks, and approval gates.
- `DASHBOARD.md` is the high-level dashboard and approval queue.
- `USER.md` has context about the user and should be read at the start of every session.
- Each initiative lives under `initiatives/[Name]/` with its own `ideas.md`, project-named idea artifact folders, `sources/`, and `wiki/` directories.

### Active initiatives

The current initiative list and their priority stack live in `DASHBOARD.md`. Read that file for the authoritative list. Wiki domain layouts for each initiative type (business, personal brand, creative project) are in `SYSTEM_OVERVIEW.md` under **Wiki Domain Structure**.

### No dependencies or services to run

There are no dependencies to install, no servers to start, and no build or test commands to run. The only tooling required is Git and a text editor. Linting, testing, and building are not applicable to this repo.

### How to work in this repo

1. Read `USER.md` first for user context.
2. Read `SYSTEM_OVERVIEW.md` for the full system design.
3. Read `IDEA_LIFECYCLE.md` when advancing an idea through stages.
4. Never delete wiki pages. Archive them to `wiki/.archive/` instead.
5. Never modify files in `sources/`. They are immutable after ingestion.
6. Always update `wiki/index.md` and `wiki/log.md` after any wiki operation.
