# Initiative & Idea Management System - Overview

## What This System Is

This is a human-in-the-loop system for moving ideas from raw concept to market, built on two interlocking layers:

- **The Lifecycle Layer** - a structured pipeline for advancing ideas through stages (Backlog → Brief → Pressure Test → Research → PRD → Design → Build → Evaluation → Launch → Marketing → Growth), with approval gates at every step. This answers: *what stage is each idea in?*
- **The Knowledge Layer** - a persistent wiki per initiative that accumulates everything you learn: sources ingested, research synthesized, customer conversations recorded, decisions made. This answers: *what do we actually know?*

The two layers work together. The lifecycle drives action. The wiki captures learning. Every stage of the lifecycle both draws from and contributes to the wiki.

### Thinking partner, not only a draft engine

The default is to use AI for **thinking**, not only for producing documents. That means multi-step passes that build context, **explicit adversarial or contrarian steps** where they help, **human checkpoints** so you steer and validate, **accumulated context** that carries forward across steps, and **tools** (for example web search) at moments where evidence matters. Pressure Test exists so ideas are stress-tested before research deepens and long before a PRD commits the team to build.

### Context Assets (foundation before heavy chains)

**Context Assets** are durable inputs you maintain and reattach when running a long chain. They are not a second filing system. They map onto files this repo already uses.

| Context asset | Where it lives |
|---|---|
| **Founder context** - background, strengths, constraints, blind spots | [`USER.md`](USER.md). Enrich over time. You can use an interview-style session in chat to expand it; the durable home stays `USER.md`. |
| **Market context** - landscape, players, trends, what is validated vs assumed | Initiative `wiki/market/` and `wiki/strategy/` when decisions belong there. Mark **validated** vs **working assumption** on the page. |
| **Customer context** - segments, problems, language, buying behavior | `wiki/customers/` for business initiatives, `wiki/audience/` for personal brand. Same epistemic discipline as market pages. |
| **Product context** - what you ship, how it differs, current state | `wiki/offerings/` plus `identity/` or `strategy/` when the product story lives there. |

Lifecycle artifacts (`01_brief.md`, `02_pressure_test.md`, and so on) stay the **per-idea** record. The wiki stays the **initiative-wide** compounding base. Both should distinguish signal from assumption where it matters.

---

## The Core Documents

| Document | Purpose |
|---|---|
| `SYSTEM_OVERVIEW.md` | This document. How the system works. |
| `PRIORITIZATION.md` | Combined score (staleness + initiative tier + project + idea), tie-breakers, and how to pick the next idea (excluding blocked work). **Tier points** are **not** edited here. |
| `IDEA_LIFECYCLE.md` | Defines every stage an idea moves through, with templates and approval criteria. |
| `DASHBOARD.md` | Dashboard for all initiatives, **Initiative priority** (**tier points**, high to low), and the **Awaiting your approval** queue. |
| `initiatives/[Initiative Name]/ideas.md` | Per-initiative inventory. **Active Projects** table (with project **Priority**), ideas grouped by project, lifecycle status, Done, Dropped, and project history (Completed Projects, Dropped Projects). |
| `USER.md` | Context about you - preferences, background, working style. The agent reads this to stay oriented. |
| [`skills/next-idea/SKILL.md`](skills/next-idea/SKILL.md) | **next-idea skill** - invoke when you want the agent to pick the highest-priority idea and step it forward. Contains the execution protocol, file-keeping rules, wiki rules, prioritization procedure, and approval pattern. |
| [`skills/add-idea/SKILL.md`](skills/add-idea/SKILL.md) | **add-idea skill** - invoke when you want to capture a new idea. Handles initiative/project routing, row format, rich content files, new project scaffolding, and `00-how-to-use.md` creation. |

---

## How the Lifecycle Works

### 1. You maintain the dashboard and each initiative’s ideas file

`DASHBOARD.md` is the high-level dashboard, the **source of truth for initiative-level priority** (the **Initiative priority** table), and the approval queue. Each initiative’s `ideas.md` is the source of truth for that initiative’s ideas, projects, statuses, **project** and **per-idea** priorities, and next actions.

### 2. You delegate a task to The Agent

When you're ready to advance an idea, tell The Agent:

> "Take *Idea X* to the next step."
> "Run Pressure Test for *Idea Y*."
> "Run the market research stage for *Idea Y*."
> "Pick up *Idea Z* - it's at the Brief stage."

### 3. The Agent's execution protocol

Before starting any real work, The Agent will:
1. **Summarize** - restate the request, including any clarifying assumptions
2. **Plan** - lay out the step-by-step approach
3. **Wait for approval** - pause for you to confirm or redirect
4. **Execute** - work through the plan step by step
5. **Summarize** - deliver the output and a brief summary of what was done

The Agent will not skip planning approval or advance past a lifecycle gate without your go-ahead.

### 4. You review and approve (or redirect)

- **Approve** - advance to the next stage
- **Revise** - redo or adjust the current stage output
- **Pause** - mark the idea `On Hold` in that initiative’s `ideas.md`
- **Kill** - mark the idea `Dropped` in that initiative’s `ideas.md`

---

## How the Wiki Works

Each initiative has its own wiki - a directory of markdown files organized by domain. The Agent writes and maintains all of it. You source, explore, and ask questions; The Agent does the summarizing, cross-referencing, filing, and bookkeeping.

The wiki is a **persistent, compounding artifact**. The synthesis is already there. Cross-references are already built. Contradictions are already flagged. Every source you add, every question you ask, and every customer conversation you have makes it richer.

### Four Wiki Operations

**Ingest.** Drop a document into `/raw/` and tell The Agent to process it for a specific initiative. The Agent will: read the source, discuss key takeaways with you, write or update wiki pages in the relevant domains, update `index.md` and `log.md`, and move the source file to the initiative's `sources/` folder. A single source may touch pages across multiple domains.

**Query.** Ask a question about an initiative. The Agent reads `wiki/index.md` first to locate relevant pages across domains, then synthesizes an answer with citations. Good answers - comparisons, analyses, discovered connections - are filed back into the wiki as new pages. Filing a page back counts as an Update and is logged. Routine queries that don't produce a new page are not logged.

**Update.** After any significant conversation, decision, or session where you've discussed strategy or learned something new, tell The Agent to capture it. The Agent will review what was discussed, identify what's new or changed, propose specific updates to wiki pages (with exact changes), and wait for your approval before writing. Nothing important should disappear into chat history.

**Lint.** Periodically ask The Agent to health-check a wiki. The Agent will look for: contradictions between pages, stale claims superseded by newer sources, orphan pages with no inbound links, important concepts lacking their own page, missing cross-references, and data gaps that a web search could fill. Lint passes are logged. Run at least monthly.

**Init (one-time).** When a wiki is first created, The Agent records a single `init` entry in `log.md`. That is not part of the recurring loop above. It marks setup before the first ingest, query, update, or lint.

### The Two Navigation Files

Every wiki contains two special files at the root of the wiki folder:

- **`index.md`** - the architecture map. A catalog of every wiki page organized by domain, with status (Draft/Active), one-line summaries, and a cross-reference index (topic → primary page → also mentioned in). The agent reads this first on every query. Updated on every operation.
- **`log.md`** - append-only activity record. Log structural changes: ingests, updates, lint passes, and init. Skip routine queries - if a query produces something worth keeping, filing it as a new wiki page is the record. Format: `## [YYYY-MM-DD] operation | description`.

### Wiki Domain Structure

Each initiative wiki is organized into six domains - adapted to fit the initiative type. Domains become subfolders within `wiki/`. This allows loading an entire domain at once for relevant tasks.

**For a business initiative (e.g., My Company):**

| Domain | What lives here |
|---|---|
| `identity/` | Company brief, brand voice, mission, values, positioning |
| `offerings/` | Products, services, pricing, differentiation |
| `customers/` | Personas, conversation notes, journey maps, buying signals |
| `market/` | Competitor profiles, landscape, positioning matrix |
| `operations/` | Team structure, processes, tools stack |
| `strategy/` | Goals, active initiatives, key decisions |

**For a personal brand initiative (e.g., My Personal Life):**

| Domain | What lives here |
|---|---|
| `identity/` | Brand voice, personal positioning, values, your story |
| `audience/` | Audience profiles, platform segments, fan types |
| `offerings/` | Content types, products, services, programs |
| `market/` | Competitive creators, platform trends, landscape |
| `operations/` | Content workflow, publishing cadence, tools |
| `strategy/` | Growth goals, content strategy, partnerships |

**For a creative project (e.g., My Hobby):**

| Domain | What lives here |
|---|---|
| `identity/` | Premise, themes, author voice, genre |
| `characters/` | Character profiles, relationships, arcs |
| `world/` | Setting, lore, rules of the universe |
| `plot/` | Structure, chapters, story threads |
| `craft/` | Writing style, influences, research notes |
| `publishing/` | Query strategy, comp titles, audience, marketing |

### Wiki Document Standards

When creating wiki pages, include YAML front matter (`domain`, `type`, `tags`, `related_documents`, `status`, `version`, `created`, `modified`), a purpose callout explaining when to load the page, an Open Questions section, and See Also cross-links. Common types: `brief`, `profile`, `catalog`, `map`, `guide`, `playbook`, `synthesis`.

Where claims matter for strategy, separate **validated** knowledge from **working assumptions** (short labels or a small table are enough). That keeps Context Assets honest as they evolve.

**Deprecation:** Never delete wiki pages. Move outdated pages to `wiki/.archive/` with a note explaining why they were retired.

---

## Operating Principles

**Constructive Challenge.** The Agent won't just execute what's asked. It will look beneath the surface, flag what might be overlooked, and push back when something doesn't add up. On high-stakes steps (Pressure Test, research synthesis), it will also **steel-man the other side** and surface what you might be missing.

**Adaptive Guidance.** Depth and approach are tailored to where you are in the process. Early stages get exploratory thinking; later stages get precision.

**Interview before drafting.** When building a new wiki page or lifecycle artifact for the first time, The Agent will ask questions to gather real information rather than generating generic content. The goal is to capture what's true for this initiative, not what's plausible in general.

**Evidence grounding when it counts.** For important claims, The Agent can tag lines as `DATA` (grounded in a cited source or search), `INFERENCE` (follows from evidence), `ASSUMPTION` (needs validation), or `SPECULATION` (might be wrong). Use this especially in market and competitive work.

**Synthesis checkpoints.** After a heavy subsection, The Agent pauses to distill 3–5 bullets that must carry forward so context compounds instead of dissolving.

**Knowledge compounds.** Insights belong in the wiki, not in chat history. If something is learned - from a source, a conversation, or a decision - it gets written down, cross-referenced, and connected to what's already there.

**Ask before acting externally.** The Agent will not send emails, post publicly, or take actions outside the workspace without explicit permission.

Full patterns for optional deep chains (market analysis, GTM, customer research synthesis) and advanced prompting moves live in `IDEA_LIFECYCLE.md`.

---

## Idea Statuses

| Status | Meaning |
|---|---|
| `Backlog` | Captured, not yet started |
| `Brief` | Brief is being written or has been approved |
| `PressureTest` | Ideation pressure test (`02_pressure_test.md`) in progress or complete |
| `Research` | Market research and/or customer discovery underway or complete |
| `PRD` | Product requirements document in progress or approved |
| `Design` | Architecture, flows, or design specs in progress or approved |
| `Build` | Active development |
| `Evaluation` | Testing, QA, and pre-launch validation |
| `Launch` | Launch plan, minimum go-live assets, rollout, and go-live. Covers pre-release work and execution. Use **Notes** in the initiative’s `ideas.md` to spell out whether you are still planning or already live. |
| `Marketing` | Post-launch marketing pack: channel plan, copy, checklist; you publish; Agent prepares materials |
| `Growth` | Post-marketing-pack: metrics, product iteration, user-base growth, ongoing experiments |
| `In Review` | Stage or elaboration output is ready. Waiting on you before the next lifecycle action. No new execution on this idea until you approve or redirect. Keep this in sync with **Awaiting your approval** in `DASHBOARD.md` when the stage is done. |
| `On Hold` | Paused - reason should be noted |
| `Dropped` | Killed - reason should be noted |

### Project priority

The **Active Projects** table at the top of each initiative’s `ideas.md` lists only currently active projects. Each row has **Project**, **Purpose**, and **Priority**. When a project is completed or retired, its row moves out of this table and into **## Completed Projects** or **## Dropped Projects** at the bottom of the file. **Priority** ranks whole projects so every idea under that project inherits the same project layer in the combined score (see [PRIORITIZATION.md](PRIORITIZATION.md)).

You may set **Priority** using words or numbers (same meaning either way).

| Value | Meaning | Points in combined score |
|---|---|---:|
| `High` or `1` | Strongest project pull in this initiative | 6 |
| `Medium` or `2` | Normal project pull | 4 |
| `Low` or `3` | Weakest project pull | 2 |

If **Priority** is missing on a project row, treat it as **Medium** (4 points) for scoring until you set it.

### Priority levels (ideas)

Use these values in the **Priority** column on each **idea** row under a **Project:** section in that initiative’s `ideas.md`. You may use **`High` / `Medium` / `Low`** or **`1` / `2` / `3`** with the same mapping as **Project priority** above (1 = High, 2 = Medium, 3 = Low).

| Priority | Meaning |
|---|---|
| `High` or `1` | Do this before other work in this project unless blocked or overridden in **Notes**. |
| `Medium` or `2` | Normal queue for this project. |
| `Low` or `3` | Backlog of value. Pick after higher-priority ideas unless you promote it. |

**How layers combine.** Initiative **tier points** ([DASHBOARD.md](DASHBOARD.md)), **project_points**, and **idea_points** **add** in the combined score in [PRIORITIZATION.md](PRIORITIZATION.md). Staleness and phase tie-breakers there are unchanged.

If two ideas still tie after the score, use tie-breakers in [PRIORITIZATION.md](PRIORITIZATION.md). Cross-initiative ordering uses **combined score** and **Last initiative work** so lower-tier initiatives still get sessions.

---

## File & Folder Organization

```
/
  SYSTEM_OVERVIEW.md            ← How the system works (this file)
  PRIORITIZATION.md ← Combined score and next-work selection
  IDEA_LIFECYCLE.md             ← Stage definitions and templates
  DASHBOARD.md        ← Dashboard, initiative priority stack, approval queue
  USER.md                       ← Context about you

  /initiatives/
    [Initiative Name]/
      ideas.md                  ← All ideas for this initiative (by project), Done, Dropped
      sources/                  ← Immutable source documents (moved here from /raw)
      outputs/                  ← Finished deliverables produced by completed ideas (documents, reports, assets)
      [Project Name]/           ← Matches the Project in ideas.md
        [Idea Name]/            ← Full lifecycle artifacts from first brief onward
          01_brief.md
          02_pressure_test.md
          02_market_research.md
          02b_customer_discovery.md
          03_prd.md
          04_design.md
          05_build/
          outputs/              ← Finished deliverables produced by this idea (documents, reports, assets)
          06_evaluation.md
          07_launch_plan.md
          08_marketing_pack.md
          09_growth_log.md
      wiki/
        index.md                ← Architecture map: all pages, domains, cross-reference index
        log.md                  ← Append-only activity record
        .archive/               ← Deprecated wiki pages (never deleted, just retired)
        identity/               ← Domain subfolders (adapted to initiative type)
        [domain2]/
        [domain3]/
        [domain4]/
        [domain5]/
        [domain6]/

  /raw/                         ← Drop zone for unprocessed documents
  /archive/                     ← Completed, dropped, or outdated work
```

**Key rules:**
- `/raw/` is a staging area only. After ingestion, files move to that initiative’s `sources/`.
- `sources/` is immutable - The Agent reads from these files but never modifies them.
- `outputs/` holds finished deliverables produced by completed ideas - documents, reports, assets, and any other tangible products of the work. These are distinct from `sources/` (user-supplied input) and from lifecycle artifacts (process scaffolding). When an idea’s product is a document, place the finished file in that idea’s `outputs/` folder and link to it from the Done row in `ideas.md`. Use initiative-level `outputs/` for deliverables that apply across multiple ideas. Do not mix source documents into `outputs/` and do not mix output deliverables into `sources/`.
- `wiki/` is entirely The Agent-maintained - you read it, The Agent writes and updates it.
- `wiki/.archive/` holds retired pages - never delete, always archive.
- Lifecycle artifact folders live at `initiatives/[Initiative Name]/[Project Name]/[Idea Name]/` and hold the full lifecycle from `01_brief.md` onward.
- Completed or dropped work moves to `/archive/` when you take artifacts off the main tree. Completed and dropped ideas stay recorded in each initiative’s `ideas.md`. When archiving, move the lifecycle artifacts and `outputs/` folder together so deliverables stay with the work that produced them.

---

## Naming Conventions

- **Ideas:** Clear, noun-based names. e.g., `Podcast Series`, `Website Rebrand`, `Chapter 3 Draft`
- **Projects:** Folder names under `initiatives/[Initiative Name]/` match the **Project** column in that initiative’s `ideas.md` exactly.
- **Idea folders:** Under `initiatives/[Initiative Name]/[Project Name]/`, folder names match the **Idea** names in `ideas.md` exactly.
- **Wiki pages:** Lowercase, hyphenated. e.g., `competitor-analysis.md`, `target-audience.md`
- **Archived items:** Prefix with initiative and end date. e.g., `My Personal Life - Podcast Series - 2026-06-30`
- **Log entries:** `## [YYYY-MM-DD] ingest | Source Title` / `## [YYYY-MM-DD] query | Question` / `## [YYYY-MM-DD] update | Topic` / `## [YYYY-MM-DD] lint | notes` / `## [YYYY-MM-DD] init | description`

---

## Review Cadence

- **Weekly (10 min):** Run the initiative health pass in [`skills/health-check/SKILL.md`](skills/health-check/SKILL.md) (or ask the agent to run the **health-check** skill). It uses `DASHBOARD.md` and each initiative’s `ideas.md`. Update statuses, priorities, and next actions when you find drift.
- **Monthly:** In each initiative’s `ideas.md`, look at `On Hold` and `Backlog` ideas. Kill what's stale, revive what's ready. Run a wiki lint pass on at least one initiative.
- **Quarterly:** Review `/archive/` for patterns. What worked? What stalled? Let that inform the next round.

---

## Approval Gates

Every lifecycle stage ends with an Approval Gate. The Agent will not proceed without your explicit sign-off. The pattern is always:

1. The Agent produces the stage output (and updates relevant wiki pages)
2. The Agent sets the idea’s status to **`In Review`**, adds or updates a row in **Awaiting your approval** in `DASHBOARD.md` when helpful, and states: *"Stage complete. [Summary of what was produced and what changed in the wiki.] Ready to move to [Next Stage] when you approve."*
3. You review and respond

After you approve, update the idea status to the next lifecycle label (or keep the same label if you asked for revision). Clear or update the tracker row when the block is lifted.

Full gate criteria for each stage are in `IDEA_LIFECYCLE.md`. Elaboration for thin ideas uses the same gate pattern. See [PRIORITIZATION.md](PRIORITIZATION.md) for blocked ideas and next-work selection.

---

## Getting Started

1. Open the initiative’s `ideas.md`, choose or create a **project** row, and add your first idea with status `Backlog`. Create `initiatives/[Initiative Name]/[Project Name]/[Idea Name]/` when you start lifecycle artifacts.
2. Drop any relevant background documents into `/raw/`
3. Tell The Agent: *"Ingest the files in /raw for the [Initiative] wiki"* - or go straight to *"Take [Idea] to the Brief stage"*
