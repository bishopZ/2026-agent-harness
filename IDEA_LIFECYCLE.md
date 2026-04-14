# Idea Lifecycle

This document defines every stage an idea moves through - from raw capture to active growth. Each stage includes a description, what the Agent needs to begin, what the Agent will produce, and the approval gate criteria before moving on.

For system context, see `SYSTEM_OVERVIEW.md`. For **Initiative priority** (tier points), see `DASHBOARD.md`. For combined score (tier + project + idea + staleness), tie-breakers, and picking the next idea, see `PRIORITIZATION.md`. For the rest of the dashboard and approval queue, see `DASHBOARD.md`. For each initiative’s ideas, see that initiative’s `ideas.md`.

**The wiki relationship.** Each initiative has a persistent wiki organized by domain (identity, customers, market, etc.) that accumulates knowledge over time. Lifecycle stages don't operate in isolation - knowledge-intensive stages both draw from and contribute to the initiative wiki. Stage artifacts (`01_brief.md`, `02_market_research.md`, etc.) under `initiatives/[Initiative Name]/[Project Name]/[Idea Name]/` are the formal deliverables for a specific idea; the wiki is the broader, growing knowledge base for the entire initiative. When the Agent produces a stage artifact, it also updates relevant wiki pages and logs the activity.

---

## Stage Map

```
Backlog → Brief → Pressure Test → Research → PRD → Design → Build → Evaluation → Launch → Marketing → Growth
```

At any point, an idea may move to `On Hold` or `Dropped`. While waiting on you after a stage or elaboration draft, the idea uses `In Review` (see **At every approval gate** below).

---

## Wiki domains by initiative type

This document often names `**customers/`** and `**market/`** because those folders match a **business** wiki (e.g. My Company). On a **personal brand** wiki, use `**audience/`** anywhere this doc says `**customers/`** (or "customers / audience" below). The stages and artifacts are the same.

When an idea is tied to something you sell or ship, also load and update `**offerings/**` with `**identity/**` and `**market/**` (or the creative equivalents below).

**Creative projects (e.g. a novel)** use `identity/`, `characters/`, `world/`, `plot/`, `craft/`, and `publishing/` (see `SYSTEM_OVERVIEW.md`). Map lifecycle hooks to those folders like this:


| This document names                            | Typical home in a creative wiki                                                                                  |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `customers/`, reader or audience discovery     | `publishing/` (target reader, discovery notes); sometimes `characters/` when the focus is who inhabits the story |
| `market/`, landscape, competitors              | `publishing/` (comp titles, positioning); `craft/` (influences, analogous works)                                 |
| `strategy/`                                    | `publishing/` (query, marketing, long-term publishing bets); `plot/` (structure and story-priority decisions)    |
| `operations/` (tools, process, how build runs) | `craft/` (writing process, tools); `publishing/` for submission or production workflow                           |


During **Marketing**, wiki updates emphasize initiative-wide messaging, channel, and competitive notes derived from the pack. During **Growth**, "all domains" means every folder for that initiative type (for a novel, all six creative domains).

---

## Stage 0 - Idea Capture (Backlog)

**What it is:** A raw idea has been named and added to the initiative’s idea list. No work has been done yet.

**To enter this stage:**

- Give the idea a name
- Optionally write one or two sentences describing it
- Add it to that initiative’s `ideas.md` under the correct **project** with status `Backlog`

**What The Agent does:** Nothing yet. This stage is owned entirely by you.

**Artifact:** An entry in that initiative’s `ideas.md`.

**To advance:** Tell The Agent to take the idea to the `Brief` stage.

---

## Stage 1 - Brief

**What it is:** A concise framing document that defines the idea clearly enough to decide whether it deserves further investment. This is a thinking tool, not a commitment.

**To enter this stage:**

- The idea has a name and at least a rough description

**What The Agent will produce (`01_brief.md`):**

- **One-liner** - a single sentence describing what this is
- **Problem statement** - what problem or opportunity this addresses, and for whom
- **Hypothesis** - what we believe to be true, and what we're betting on
- **Target audience** - who this is primarily for
- **Why now** - what makes this the right moment to pursue
- **Success criteria** - how we would know this worked (specific, measurable where possible)
- **Out of scope** - what this explicitly does not try to solve
- **Rough effort estimate** - ballpark: days / weeks / months, and what kind of resources
- **Open questions** - unknowns that need to be resolved before or during research
- **Recommendation** - The Agent's initial read: is this worth pursuing further, and why?

**Wiki domains to load:** `identity/` (for brand voice and positioning), `customers/` or `audience/` (for existing persona knowledge). The Agent will check these before drafting rather than starting from zero.

**Wiki update:** The brief's target audience and problem framing will be checked against and may update the relevant domain pages.

**Approval gate:** Review the brief. Ask: Is the problem real? Is the audience clear? Are the success criteria meaningful? Do the open questions feel answerable? Approve to advance to Research, or ask for revisions.

---

## Stage 2 - Research

**What it is:** A two-part investigation that pressure-tests the brief and informs the PRD. Part 1 is desk research (market landscape, competitors, existing data). Part 2 is primary research - real conversations with real people who have the problem.

**To enter this stage:**

- An approved `01_brief.md` exists

---

### Part 1 - Market Research

**What The Agent will produce (`02_market_research.md`):**

- **Competitive landscape** - who else is doing this (or something close), at what scale, with what strengths and weaknesses
- **Market size & dynamics** - estimated addressable audience or market, growth trends, tailwinds or headwinds
- **User pain points** - what real users say about existing solutions (from reviews, forums, interviews, public research)
- **Gaps and opportunities** - where existing solutions fall short, and where this idea could differentiate
- **Analogous markets or models** - similar problems solved in adjacent domains worth learning from
- **Key risks** - market, timing, and competitive risks identified at this stage
- **Research synthesis** - a 3–5 sentence summary of what the research reveals about the opportunity

**Wiki domains to load:** `market/` (existing competitor and landscape pages). The Agent will check these first and update them with new findings.

**Wiki update:** This is the most wiki-intensive stage for market knowledge. The Agent will create or update pages across the `market/`, `customers/`, and `strategy/` domains - competitor profiles, market sizing, user pain point summaries - and flag any contradictions with existing pages.

---

### Part 2 - Customer Discovery

**What it is:** Direct conversations with real people who have the problem. The goal is 10 conversations before writing the PRD. Ten is the sweet spot - patterns don't emerge reliably with fewer than 5, and more than 20 yields diminishing returns before taking action.

This is the most important research you can do. Desk research tells you what's out there. Customer conversations tell you what's true for real humans.

**Are you pre-product or post-product?**

- **Pre-product (validating):** Focus on whether the problem is real and painful. Questions center on current behavior, past attempts, and willingness to pay.
- **Post-product (acquiring):** Focus on fit and what would make someone try the solution. Questions center on specific situations and decision criteria.

**What The Agent will help you produce:**

#### The Finder - Who to reach

The Agent will help identify 10–20 specific people to reach out to. Not target segments - actual humans with names and profiles. Output includes:

- LinkedIn search strategy (keywords + filters)
- Relevant Reddit communities or thread types
- Other platforms where this person is active
- Signals that someone is worth reaching out to (recent activity, evidence of the problem)

#### The Opener - What to say

The Agent will draft personalized messages under 100 words using one of three frames:


| Frame                                                                                                          | Best for                                     |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| **Research Frame** - "I'm studying [problem]. Would you share your experience?"                                | People who've publicly described the problem |
| **Shared Struggle Frame** - "Your post hit close to home. I've experienced the same thing. Can we swap notes?" | People in similar situations to you          |
| **Value-First Frame** - Lead with something useful, then ask for time                                          | Busy people, influencers                     |


Rules for every message: specific to the person, under 100 words, frames as research not sales, makes it easy to say yes or no.

#### The Guide - What to ask

Use these 12 questions across a 30-minute conversation. Listen 80% of the time. Ask "why" up to five times to get beneath surface answers. Get specific - "tell me about the last time" beats "how do you usually." Never mention your solution until asked.

**Opening (get them talking):**

1. "Can you walk me through how you currently handle [problem area]?"
2. "What does a typical week look like when you're dealing with [problem]?"

**Pain Discovery (find the real problem):**

1. "What's the most frustrating part of that?"
2. "When was the last time [problem] cost you time, money, or opportunity?"
3. "What have you tried before? What happened?"

**Solution Exploration (don't pitch, probe):**

1. "If you could wave a magic wand, what would be different?"
2. "What would 'good enough' look like?"
3. "What would make you switch from your current approach?"

**Willingness to Pay (only if the conversation is going well):**

1. "How much is this problem costing you right now?"
2. "Would you pay to solve this? What's it worth to you?"
3. "What would you need to see before you'd try something new?"

**Meta (always valuable):**

1. "Who else should I talk to about this?"

**After each conversation:** Complete the post-call reflection within 30 minutes - memory decays fast. Capture: 2–3 sentence summary, hypothesis check (confirmed / challenged / wrong), key insights, the single most important takeaway, problem validation score (1–5), and honest assessment of whether they'd pay.

#### The Synthesizer - What you learned

After 5 conversations, check for emerging patterns. After 10, The Agent will run a full synthesis:

- Pattern summary - what did most people say?
- Customer segments - do distinct groups emerge?
- Problem validation - evidence for and against
- Unexpected insights - what surprised you?
- Key quotes - organized by theme
- Feature priorities - what to build first
- Messaging insights - language that resonates
- Gaps - what you still don't know

**The decision framework:**


| What you found                       | Signal    | Action                                        |
| ------------------------------------ | --------- | --------------------------------------------- |
| Problem is real + people will pay    | Strong    | **Build** - proceed to PRD                    |
| People will pay + problem is unclear | Dangerous | Find the real problem first                   |
| Problem is real + people won't pay   | Hobby     | Find different customers or a different model |
| Neither                              | Clear     | Stop - find a different problem               |


**What The Agent will produce (`02b_customer_discovery.md`):**
A synthesis document with all findings, key quotes, the decision framework outcome, and recommended next steps. This also feeds into the wiki's `customers/` domain.

**Wiki domains to load:** `customers/` or `audience/` (existing persona pages).

**Wiki update:** Conversation notes, synthesis, persona updates, and key quotes all go into the `customers/` or `audience/` domain. The synthesis page becomes a living reference for all future ideas in this initiative.

---

**Approval gate (Research):** Review both the market research and customer discovery. Ask: Is the opportunity real and differentiated? Do real humans confirm the problem? Are the risks manageable? Does the decision framework signal Build? Approve to advance to PRD, or send back for more research on specific questions.

---

## Stage 3 - PRD (Product Requirements Document)

**What it is:** The detailed specification for what will be built or done. This is the contract between the idea and the execution team. It is written after Research - never before - because it should reflect what real customers actually need, not what we assumed.

**To enter this stage:**

- Approved `01_brief.md`, `02_market_research.md`, and `02b_customer_discovery.md` exist (or research has been waived with good reason)

**What The Agent will produce (`03_prd.md`):**

- **Executive summary** - what this is and why it's being built
- **Goals and non-goals** - explicit statement of what success looks like and what is out of scope
- **User personas** - 1–3 specific, named user types drawn from customer discovery conversations
- **User stories** - "As a [persona], I want to [action] so that [outcome]" for all key interactions
- **Functional requirements** - what the system/product/initiative must do, numbered and prioritized (P0, P1, P2)
- **Non-functional requirements** - performance, reliability, security, accessibility, or other quality constraints
- **Acceptance criteria** - specific, testable conditions that define "done" for each requirement
- **Dependencies and assumptions** - what this relies on being true or in place
- **Open questions** - unresolved decisions that need to be made before or during build
- **Timeline and milestones** - suggested phasing with rough dates or durations
- **Success metrics** - how this will be measured post-launch

**Wiki domains to load:** `customers/` (personas, discovery synthesis), `market/` (competitive context), `identity/` (brand and positioning). The Agent draws on all three when writing personas and requirements.

**Wiki update:** Finalized personas and success metrics are filed back into the `customers/` domain as reference pages for future ideas in this initiative.

**Approval gate:** Review the PRD carefully. Ask: Are all requirements clear and testable? Are priorities correct? Are there missing user stories? Are the success metrics the right ones? This is the last gate before significant effort is invested. Approve to advance to Design, or revise.

---

## Stage 4 - Design

**What it is:** The technical and structural blueprint for how this will be built or executed. For software, this is architecture and flows. For non-software initiatives, this is the execution plan and structure.

**To enter this stage:**

- An approved `03_prd.md` exists

**What The Agent will produce (`04_design.md`):**

- **Approach summary** - the overall approach chosen and why (vs. alternatives considered)
- **Architecture or structure** - how the pieces fit together (systems, components, teams, processes)
- **User or process flows** - step-by-step walkthroughs of key interactions or workflows
- **Technical stack or tooling** - what will be used to build this and why
- **Data model or information architecture** - how information is structured and stored
- **Interfaces and integrations** - what this connects to, and how
- **Build phases** - how the build will be broken into chunks with milestones
- **Risks and mitigations** - technical or execution risks and how they'll be managed
- **Alternatives considered** - what else was evaluated and why it was set aside

**Wiki domains to load:** `operations/` (tools, processes, existing infrastructure).

**Approval gate:** Review the design. Ask: Is the approach sound? Are the build phases reasonable? Are risks well understood? Are there missing integrations or edge cases? Approve to advance to Build, or send back for revisions.

---

## Stage 5 - Build

**What it is:** Active construction of the idea - writing code, drafting content, building systems, or executing plans. This stage may have multiple sub-milestones.

**To enter this stage:**

- An approved `04_design.md` exists

**How Build works:**
Build is the longest stage and is often broken into sub-milestones defined in the design document. The Agent will:

1. Execute the first build milestone
2. Produce output (code, documents, assets, etc.) and a status summary
3. Wait for approval before moving to the next milestone

Each milestone approval functions as a mini gate. You can redirect, pause, or adjust scope at any milestone.

**Artifacts:** Vary by initiative - source code, content files, configured systems, written materials, etc. Process and working files go in the `05_build/` folder under `initiatives/[Initiative Name]/[Project Name]/[Idea Name]/`. When the build produces a finished deliverable (a document, report, asset, or other tangible output), place it in `initiatives/[Initiative Name]/[Project Name]/[Idea Name]/outputs/` rather than in `sources/`. The `outputs/` folder is for things the idea produced; `sources/` is for documents you brought in. Link to output files from the Done row in `ideas.md` when the idea completes.

**Wiki update:** Key technical decisions, architectural choices, and lessons from the build are captured in the `operations/` domain.

**Approval gate:** When all build milestones are complete, The Agent will present a build summary and recommend advancing to Evaluation. Review and approve to continue.

---

## Stage 6 - Evaluation

**What it is:** Validation that what was built works as intended and is ready for release. This includes testing, review against acceptance criteria, and a go/no-go decision.

**To enter this stage:**

- Build is complete and all artifacts are in place

**What The Agent will produce (`06_evaluation.md`):**

- **Evaluation approach** - how the output was tested or reviewed
- **Acceptance criteria review** - each criterion from the PRD, and whether it was met
- **Issues found** - bugs, gaps, or quality problems identified, with severity ratings
- **Remediation plan** - how issues will be addressed before launch
- **Pre-launch checklist** - all items that must be complete before going live
- **Go / No-go recommendation** - The Agent's assessment with rationale

**Approval gate:** Review the evaluation. Are all P0 acceptance criteria met? Are the remaining issues acceptable? Is the pre-launch checklist complete? Approve to advance to Launch, or send back to Build to address critical issues.

---

## Stage 7 - Launch

**What it is:** Taking the idea to market - shipping the product, publishing the content, announcing the initiative, or activating the plan.

**To enter this stage:**

- Evaluation is approved and the pre-launch checklist is complete

**What The Agent will produce (`07_launch_plan.md`):**

- **Launch objectives** - what a successful **release moment** looks like (ship day and immediate aftermath)
- **Target audience and channels** - who is being reached for the **initial** announcement (high level)
- **Launch timeline** - sequenced activities with owners and dates for go-live
- **Messaging and positioning** - **minimum** narrative and copy required to flip the switch (sustained campaign messaging, channel depth, and post queue live in `08_marketing_pack.md`)
- **Launch assets** - **blocking** list: content, copy, or materials that must exist before go-live (The Agent can produce this minimum set)
- **Rollout plan** - phased or full launch, and how it's being managed
- **Monitoring plan** - what's being watched in the first hours/days after launch
- **Rollback or contingency plan** - what happens if something goes wrong

**Wiki domains to load:** `identity/` (brand voice and messaging), `customers/` (personas), `strategy/` (goals and positioning).

**Approval gate:** Review the launch plan. Is the minimum messaging sufficient for go-live? Is the rollout sound? Approve to execute the launch, or revise the plan.

**To advance:** After go-live matches the plan (or you note exceptions in that initiative’s `ideas.md`), tell The Agent to take the idea to **Marketing** for the post-launch marketing pack.

---

## Stage 8 - Marketing

**What it is:** After go-live, a structured **post-launch acquisition and awareness** pass. The Agent produces a full marketing execution pack—plan, copy, channel recommendations, and a posting checklist—so **you only publish** (paste, schedule, upload). The Agent does not post on your behalf without explicit permission (see `SYSTEM_OVERVIEW.md` **Operating Principles**).

**To enter this stage:**

- `07_launch_plan.md` is approved and go-live is complete as defined in that plan (or you have recorded in **Notes** that you want the pack drafted ahead of go-live)

**What The Agent will produce (`08_marketing_pack.md`):**

- **Executive summary and goals** - what this push achieves; tie to PRD success metrics where relevant
- **Positioning and competitive angle for this release** - stage-specific; draws on wiki `market/` without repeating full early-stage research
- **Channel plan** - recommended channels with rationale, priority order, and cadence
- **Voice and company image for this push** - short guardrails; align with wiki `identity/`
- **Social posts** - table: platform, post type, copy, suggested media, CTA, optional hashtags (no live posting actions)
- **Blog / longform** - titles, outlines or drafts, SEO notes if useful
- **Paid advertising** - campaign skeleton, audiences, angles, example copy, budget bands as assumptions (no buying, placing, or operating ad accounts)
- **Guerrilla or unconventional tactics** - ideas with effort and risk notes
- **Posting checklist** - ordered steps for you: what to paste where and in what order
- **Materials index** - links to sections above; list what you must supply (e.g. screenshots) vs. what the pack already contains

**Wiki domains to load:** `identity/`, `customers/` or `audience/`, `market/`, `strategy/` (and for creative initiatives, `publishing/` per [Wiki domains by initiative type](#wiki-domains-by-initiative-type)).

**Wiki update:** File durable messaging, channel, and competitive learnings that should outlive this idea. Do not duplicate the entire pack into the wiki unless it becomes initiative-wide reference.

**Approval gate:** Does the plan, channel mix, and tone match the initiative? Are you willing to execute the posting checklist yourself? Approve to advance to **Growth** (and start or continue `09_growth_log.md`), or request revisions.

---

## Stage 9 - Growth

**What it is:** Ongoing **product and user-base** work after the marketing pack is approved: metrics, feedback, feature and improvement iteration, and scaling. This stage is ongoing and cyclical. The first “big push” materials live in `08_marketing_pack.md`; Growth focuses on learning, product levers, and durable growth—not on drafting the initial post-launch campaign from scratch.

**To enter this stage:**

- `08_marketing_pack.md` is approved (or you explicitly waive Marketing per **Notes** and record the rationale)

**What The Agent will produce (maintained in `09_growth_log.md`):**

- **Launch and marketing retrospective** - what happened at go-live and during the first push vs. expectations; pull lessons from `08_marketing_pack.md` execution when relevant
- **Early metrics** - first data against success criteria
- **User feedback summary** - what real users are saying
- **Product and growth levers** - highest-leverage improvements to the offering, onboarding, retention, or distribution (beyond the prepared campaign)
- **Iteration backlog** - new ideas or improvements generated from real-world use
- **Growth experiments** - specific hypotheses to test (often product- or funnel-shaped), with expected outcomes; campaign learnings from the marketing pack may seed experiments here
- **Scaling plan** - when and how to increase investment if signals are positive

**Customer discovery in Growth:** Real-world use generates new questions. Use the Outreach Engine framework (Finder, Opener, Guide, Synthesizer) to run fresh conversation rounds focused on retention, expansion, or new segments. Post-product outreach focuses on fit and switching criteria rather than problem validation.

**Wiki domains to load and update:** All domains may be updated during Growth. User feedback updates `customers/`. Competitive responses update `market/`. Lessons learned update `strategy/` and `operations/`. New ideas generated should be added to that initiative’s `ideas.md` as `Backlog` entries under the right **project**.

**How Growth works:**
Growth is the only stage that loops. Each growth experiment can be treated as a mini-lifecycle of its own (brief → build → evaluate). Smaller experiments may use that short path on purpose. Larger bets should re-enter at Brief or Research so the full pipeline stays honest. Significant new directions may become entirely new rows in `ideas.md`.

**This stage has no terminal approval gate.** It continues until the initiative is retired, the idea is folded into something larger, or is deliberately wound down.

---

## Moving to On Hold or Dropped

An idea can move to either of these states from any stage.

**On Hold:** The idea is paused. Add a note in that initiative’s `ideas.md` with the reason and date. Resume at any time by telling The Agent to pick it back up.

**Dropped:** The idea is killed. Move it to the **Dropped** section in `ideas.md` with the reason. Dropped ideas stay on file for reference. They may be relevant later or inform future decisions.

---

## Stage Summary Table


| Stage             | Status Label   | Key Artifact                                          | Wiki Domains                                                                          | Approval Question                               |
| ----------------- | -------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------- | ----------------------------------------------- |
| 0 – Capture       | `Backlog`      | Entry in initiative `ideas.md`                        | -                                                                                     | N/A - owned by you                              |
| 1 – Brief         | `Brief`        | `01_brief.md`                                         | identity, customers / audience                                                        | Is this worth pressure-testing (or waived)?     |
| 2 – Pressure Test | `PressureTest` | `02_pressure_test.md`                                 | market, customers / audience, offerings, identity (+ `[USER.md](USER.md)`)            | Are we honest about risks and next experiments? |
| 3 – Research      | `Research`     | `02_market_research.md` + `02b_customer_discovery.md` | market, customers / audience                                                          | Is the opportunity real + do people confirm it? |
| 4 – PRD           | `PRD`          | `03_prd.md`                                           | customers / audience, market, identity (+ offerings when relevant)                    | Is this ready to build?                         |
| 5 – Design        | `Design`       | `04_design.md`                                        | operations                                                                            | Is the approach sound?                          |
| 6 – Build         | `Build`        | `05_build/` folder + `outputs/` for finished deliverables | operations                                                                            | Is the build complete?                          |
| 7 – Evaluation    | `Evaluation`   | `06_evaluation.md`                                    | -                                                                                     | Is this ready to ship?                          |
| 8 – Launch        | `Launch`       | `07_launch_plan.md`                                   | identity, customers / audience, strategy                                              | Is this ready to go live?                       |
| 9 – Marketing     | `Marketing`    | `08_marketing_pack.md`                                | identity, customers / audience, market, strategy (+ publishing for creative)         | Ready to execute the checklist yourself?        |
| 10 – Growth       | `Growth`       | `09_growth_log.md`                                    | all domains (see [Wiki domains by initiative type](#wiki-domains-by-initiative-type)) | Ongoing - no terminal gate                      |


`In Review` is not a numbered stage. It marks a **waiting state** between stages when deliverables are ready and you have not approved the next step. **Elaboration** for thin ideas uses the same approval pattern and may occur before Stage 1.

Personal brand initiatives use `audience/` instead of `customers/`. Creative initiatives map columns to their wiki as described in that section.

---

## Advanced techniques (optional prompts)

Use these at checkpoints when stakes are high or analysis feels too comfortable.

**Adversarial prompting.** After a draft, ask for the strongest case **against** the plan. Example: “What would a skeptical investor say is wrong? What are we missing or overweighting?”

**Persona shifting.** Ask for the same artifact through two or three lenses (for example bootstrap founder, experienced buyer, well-funded competitor).

**Evidence grounding.** Tag claims as `DATA`, `INFERENCE`, `ASSUMPTION`, or `SPECULATION` (see `SYSTEM_OVERVIEW.md` **Operating Principles**).

**Iterative deepening.** When a single point drives the decision, ask what would make it true or false, what evidence to collect, and what second-order effects follow.

**Synthesis checkpoints.** Before leaving a major section, capture 3–5 bullets that must carry forward so the next step does not lose the thread.