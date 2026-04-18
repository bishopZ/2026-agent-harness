# Public launch copy pack

Use this file as the source of truth for bishopz.com, social posts, and GitHub. Punctuation follows your house rules, no em dashes, no semicolons.

Canonical repository: https://github.com/bishopZ/2026-agent-harness

---

## 1. Website article (bishopz.com)

**Suggested title:** The agent harness is the operating system, the agent is the application

**Suggested subtitle:** Why I open sourced a Markdown-native harness for ideas, memory, gates, and integrity

### The missing layer

Most public discussion about AI-assisted work still centers on models and prompts, or on starter code you can clone and ship. Those pieces matter. They are not the full stack.

If you put a capable model in front of a repository, you still need an answer to the boring questions. Where does context live between sessions, who can advance work, how do you pick the next task, and how do you detect drift between what files claim and what is true on disk. Those answers are not the model weights. They are infrastructure.

Industry vocabulary has caught up with that split. People call the non-model machinery around an LLM an **agent harness**, the orchestration loop, tools, memory, context management, persistence, error handling, and guardrails. A common shorthand from practitioners is easy to remember, if you are not the model, you are the harness.

There is a second confusion worth clearing early. When someone says they built an agent, they often built a harness and pointed a model at it. The **agent** is the emergent behavior, goal directed, tool using, self correcting in the best case. The **harness** is what makes that behavior repeatable instead of accidental.

### Harness as operating system, agent as application

The metaphor I use is simple. The harness is the **operating system**. The agent is the **application** that runs inside it.

An OS owns scheduling, memory, permissions, and recovery. An application owns user-visible outcomes when those services are reliable. If your harness cannot store durable memory, enforce checkpoints, score what to do next, or repair small inconsistencies, you do not have a stable place to run applications. You have a demo loop.

This matters for how we evaluate software in the agent era. A repository that only shows application code can still hide a brittle harness, ad hoc context, no provenance for claims, no gates, no prioritization policy. Conversely, a harness-first repository can look “non technical” because it is mostly Markdown and process. That is a feature if your goal is clarity, auditability, and low operational surface area.

When you review a team’s work in 2026 and beyond, ask where the harness lives. If it only exists in chat logs and tribal prompts, you do not yet have an inspectable system. If it lives in files with roles, invariants, and skills that encode behavior, you can reason about change the same way you reason about code review. That shift is not about replacing engineering judgment. It is about making the operating assumptions legible.

### Contrast with a boilerplate

I also maintain a 2026-oriented boilerplate for a TypeScript and React web application, batteries included, tests, auth patterns, and AI-friendly project docs. That work answers a specific question, how do I start shipping an app with good defaults.

The **2026 Agent Harness** answers a different question, how do I run a serious agent loop around real initiatives without pretending Markdown is a runtime. There is no package install, no server, no build step. The product is the workflow and file contract, plus the skills that teach an agent how to behave.

If the boilerplate is a fast car, the harness is the road system, the signage, and the maintenance schedule. You need both kinds of work at different times.

### Feature deep dive, memory with knowledge management

**OS responsibility:** durable memory subsystem and provenance.

The harness gives each initiative a **wiki**, a persistent knowledge base the agent maintains as it works. That is where synthesis lands, where cross references accumulate, and where future sessions can reuse structured context without re-deriving it from chat history.

Ingestion is explicit. You drop files into `raw/`, run the **update** skill, the agent reads, summarizes into the wiki, then files the originals under `sources/` as **immutable** inputs. Generated deliverables live under `outputs/`. The separation is intentional. You can always tell what you brought in versus what the system produced.

That pattern is the same epistemic discipline good teams want in research and product work, signal with a chain of custody, not a blur of “the model said it once in a thread.”

### Feature deep dive, full idea lifecycle management

**OS responsibility:** process lifecycle, stage contracts, and artifacts.

Every idea follows one pipeline, backlog through brief, pressure test, research, PRD, design, build, evaluation, launch, marketing, and growth. Each stage has a defined artifact and a defined purpose. For example, pressure test exists to stress assumptions before research deepens. Research is split so desk work and customer discovery do not collapse into a vague “look into it” step.

The harness encodes **order** and **definition of done** per stage. That is how you turn emergent creativity into something a team, or future you, can audit.

### Feature deep dive, human-in-the-loop gating

**OS responsibility:** permissions, checkpoints, and policy enforcement.

The harness is not autopilot for irreversible decisions. The agent produces work, then stops at gates. `DASHBOARD.md` includes an approval queue. You review, you approve with notes, you redirect, you pause, or you drop. The default protocol in the system docs is explicit, summarize, plan, wait for approval, execute, summarize.

Call that friction if you want. In production it is **governance**. It is how you keep autonomy from turning into silent compounding errors.

### Feature deep dive, automatic prioritization

**OS responsibility:** scheduler and fairness.

When you run **next-idea**, the agent selects the highest scoring eligible idea using a documented combination, initiative tier, staleness so neglected areas do not starve, project priority, and per-idea priority. That is a policy you can argue with and change, not a vibe.

If you run agents on a schedule in the cloud, this layer is what keeps the loop pointed at the right work without constant manual steering.

### Feature deep dive, self-healing

**OS responsibility:** integrity checks and repair.

Long running agent systems drift. Links rot, rows disagree with files, queues get out of sync. The monthly **health-check** skill is a deliberate pass that reconciles dashboard state, ideas tables, and disk, applies obvious fixes, and surfaces what still needs a human.

That is the harness admitting that reliability is a process, not a one-time prompt.

### Who this is for

This harness is for individuals and small teams who want a serious operating loop around initiatives, business, personal brand, creative work, without adding another services graph. It is for people who are happy to let an agent execute, but want durable memory, explicit gates, and a paper trail.

It is not for you if you want a hosted SaaS with buttons, or if you dislike maintaining Markdown as the source of truth.

### How to adopt

Fork or clone [https://github.com/bishopZ/2026-agent-harness](https://github.com/bishopZ/2026-agent-harness). If you use cloud agents on private material, keep your fork private until you are comfortable with what is inside. Run the **bootstrap** skill, populate initiatives, ideas, and sources, then use **next-idea** on a cadence that matches your budget and risk tolerance.

The license is MIT.

### Why I published it

I care about being clear in public about how I think agent systems should be operated, not only which models I use. The harness is where accountability lives, memory, gates, scheduling, integrity. Publishing the full file contract is a way to teach, to invite correction, and to show the kind of end to end thinking I want to bring to a team building real products in the agent era.

---

## 2. Reddit

https://www.reddit.com/r/AskVibecoders/s/HNzCqeRk9H

### Variant A, general technical (r/programming, r/ExperiencedDevs tone)

I published a harness-first repo for running an agent loop on top of Markdown, MIT, no services, no install step.

A harness is the non-model infrastructure around an LLM, orchestration, tools, memory, persistence, errors, guardrails. I think of it like an OS. The agent is the application behavior that only stays coherent when scheduling, memory, checkpoints, and integrity passes exist.

The repo is here: https://github.com/bishopZ/2026-agent-harness

What it actually does:

- Memory with knowledge management, per-initiative wiki, immutable `sources/`, generated `outputs/`, `raw/` inbox plus an **update** skill
- Full idea lifecycle management, one pipeline from backlog through growth, staged artifacts instead of ad hoc docs
- Human-in-the-loop gating, dashboard approval queue, explicit plan and approval protocol before execution
- Automatic prioritization, documented scoring for **next-idea**, tier plus staleness plus project and idea priority
- Self-healing, a monthly **health-check** skill to reconcile links, queues, and disk

Why Markdown. Auditable contracts beat mystery state in chat logs when you want repeatability.

I am the author, Bishop Zareh, same handle as the GitHub org. If you try it, issues and forks are welcome. I am especially curious what breaks in real teams, and what policies you would change first.

### Variant B, ML and local agent tone (r/MachineLearning, r/LocalLLaMA style)

Topic, what sits around the model when you run agents for weeks, not minutes.

I shipped a small public harness that treats the repo as the OS and the agent as the app layer behavior. It is Markdown-native, skills-driven, MIT, no hosted runtime.

https://github.com/bishopZ/2026-agent-harness

Capabilities map cleanly to harness responsibilities, durable wiki memory with immutable sources, a fixed lifecycle pipeline with artifacts, human gates and an approval queue, deterministic prioritization for scheduled **next-idea** runs, and a periodic integrity pass.

If you experiment with local or cloud agents, the interesting unit of work is often not the next clever prompt, it is the file contract that keeps context and policy stable across sessions.

Disclosure, I wrote it. Feedback welcome.

---

## 3. Facebook (low technical)

I published a free “flight deck” for big ideas on GitHub. Think of it like a checklist and filing system for projects, plus a very thorough research librarian that has to stop at your desk before anything important moves forward.

It is all documents, no new app to learn, no server. The computer helps move work along, you stay in charge of what actually advances.

If you want to peek, it lives here, no pressure: https://github.com/bishopZ/2026-agent-harness

---

## 4. LinkedIn

We talk a lot about models. We talk a lot about starter repos. We still under-discuss the operating layer that makes agent behavior reliable, durable memory, explicit gates, a scheduling policy, and periodic integrity checks.

I open sourced **2026 Agent Harness** as a concrete file contract for that layer. Markdown is the system of record. Skills teach the agent how to move ideas through a full lifecycle, write to a per-initiative wiki, respect human approvals, pick the next eligible idea with a documented score, and run a monthly reconciliation pass so links and queues stay honest.

If I were hiring for agent-native product work, I would look for people who can describe their harness the same way they describe their architecture, where truth lives, what advances without humans, and how drift is detected.

What is the first policy you would not ship without, memory, gates, scheduling, or integrity passes?

Repo: https://github.com/bishopZ/2026-agent-harness

---

## 5. GitHub repository description (350 character maximum)

Character counts are for the one-line strings below, re-count if you edit wording.

**Option A (definition-forward), 210 characters**

Markdown-native agent harness, wiki memory with immutable sources, full idea lifecycle from backlog through growth, human approval gates, scored next-idea prioritization, monthly health-check. MIT. No services.

**Option B (outcome-forward), 159 characters**

Move ideas from backlog to growth with human gates, a per-initiative wiki, scored next work, and integrity checks. Markdown system of record, MIT, no services.

**Option C (metaphor-forward), 178 characters**

Treat your repo as the OS for agent work. Durable wiki memory, lifecycle artifacts, approval gates, prioritization policy, self-healing checks. Markdown-native, MIT, no services.

**Recommended:** Option A for search clarity, Option C if you want the metaphor in the one-line field.

---

## 6. Optional README lead (single added sentence)

Placed after the five feature bullets, before the existing paragraph that begins “A structured knowledge management system…”.

Proposed sentence:

Together these form the harness, the operating system for the work. The agent is the emergent execution behavior that runs inside this structure when you follow the documented skills and file rules.

(Applied in README.md if you keep this file in sync with the repo.)
