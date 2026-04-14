---
name: health-check
description: >-
  Weekly initiative health check: sync DASHBOARD.md with ideas.md,
  approval queue, and links; flag row vs artifact drift; optional one-line wiki
  summary on the top-tier initiative log.
---

Run the **weekly initiative health check** from this repo’s process docs.

Do not use Trello. Use only files in this repo.
Treat [SYSTEM_OVERVIEW.md](SYSTEM_OVERVIEW.md) as the source of truth for process.
Use valid idea **statuses** and **priority** labels from SYSTEM_OVERVIEW.md.

## When to use

User asks for a weekly health check, initiative health pass, tracker sync review, or “run health-check.”

## Steps

1. Read [DASHBOARD.md](DASHBOARD.md) in full, especially **Initiatives** and **Awaiting your approval**.

2. **Initiatives table:** Check tier order, **What** blurbs, and **Last initiative work** dates against recent work. Update when clearly stale.

3. **Approval queue:** For each row, open that initiative’s `ideas.md` and confirm the **Idea** name matches, **Status** is **`In Review`**, and **Notes / next action** aligns with the queue row. Scan for **`In Review`** ideas missing a queue row (or document an exception in Notes).

4. **Which `ideas.md` to read:** Use the tracker’s rule. Open `ideas.md` for an initiative if it has a queue row **or** any idea whose status is not **`Backlog`**, **`Done`**, or **`Dropped`**.

5. **Links:** Follow artifact links from the tracker and `ideas.md`. Fix broken paths (for example after folder renames). **Idea** folder names under `projects/` must match the **Idea** column in that initiative’s `ideas.md` exactly (see SYSTEM_OVERVIEW.md **Naming Conventions**). Confirm each row in **Active Projects** has **Priority** (default missing row to **Medium** in scoring per PRIORITIZATION.md, but the column should be set for clarity).

6. **Row vs artifacts:** If **Status** and files disagree (late stage in the row but an earlier artifact missing or `status: Draft` in front matter), either fix **metadata** after you are sure, or flag it in chat. For artifact order and phase rules, see [../next-idea/SKILL.md](../next-idea/SKILL.md). Do not substitute this pass for completing a lifecycle stage.

7. **Deliverables**
   - Apply obvious fixes (broken links, misaligned queue vs **In Review**, stale **Last initiative work** when you can justify the date).
   - Give a short summary in chat: what you checked, what you changed, what still needs your attention.

8. **No standalone health report file.** Do not create a new markdown file whose only job is to summarize this pass. Updates belong in existing tracker, `ideas.md`, and wiki files.

9. **Wiki log (optional, one entry max):** If there is a durable process lesson, append **at most one** dated block to **`wiki/log.md` of the initiative in the first row of the Initiatives table** (highest tier). Use `## [YYYY-MM-DD] lint | health check summary` and keep the body to about three to six lines. You may mention other initiatives in that blurb. If nothing worth keeping, skip the log.

## Definition of done

1. Tracker and touched `ideas.md` rows reflect the same approval and link reality you verified.
2. Chat includes a concise summary of changes and any follow-ups for you.
3. At most one short **lint | health check summary** on the top-tier initiative’s `wiki/log.md`, or none.
