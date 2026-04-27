---
name: remove-project
description: >-
  Remove a project from an initiative. If ideas exist, offers three options for
  each: archive the idea folder, move it to another project, or delete it.
  Cleans up ideas.md, the project folder on disk, the tracker, and the wiki log.
  Use when the user wants to remove, retire, close, or dissolve a project.
---

# Remove Project

Use this skill when the user wants to **remove a named project** from an initiative. This covers the project row in **Active Projects**, the **## Project:** section in `ideas.md`, and the folder at `initiatives/[Initiative]/[Project Name]/` (a direct child of the initiative, per `SYSTEM_OVERVIEW.md`).

Treat this as the project-level closure/removal workflow.

Do not use Trello. Use only files in this repo.

Follow `SYSTEM_OVERVIEW.md` (archive rules, naming conventions), and the target initiative's `ideas.md`.

## Inputs

Resolve from the user and files:

- **Initiative** - which `initiatives/[Initiative Name]/` folder. Ask once if ambiguous.
- **Project name** - must match an existing row in **## Projects** exactly.

Do not proceed if the project name does not exist in the initiative's `ideas.md`.

## Step 1 - Read and report

Before making any changes:

1. Open `initiatives/[Initiative]/ideas.md`.
2. Find the **## Project: [Name]** section.
3. Count how many ideas are in it. Separate them into:
   - **Active ideas** - any row whose Status is not `Done` or `Dropped` (includes `Backlog`, `Brief`, `In Review`, `On Hold`, etc.).
  - **Completed or dropped ideas** - rows with Status `Done` or `Dropped`. These should already be recorded in `history/done-history.md` or `history/dropped-history.md` and require no further action.
4. Check whether `initiatives/[Initiative]/[Project Name]/` exists on disk and whether it contains any idea subfolders with lifecycle artifacts.

## Step 2 - Handle ideas (stop and ask if any active ideas exist)

If there are **no active ideas** in the project, skip to Step 3.

If there are **active ideas**, stop and present the following options to the user before touching any files. List each active idea by name and ask the user to choose one of the three options **per idea** (or one choice applied to all if they prefer):

---

**Option A - Archive**
Move the idea's lifecycle folder (if it exists) to `archive/` and record it in `history/dropped-history.md`. This is the same flow as the **drop-idea** skill. You will need a short reason for the dropped-history record.

**Option B - Move to another project**
Reassign the idea row to a different active project in the same initiative. If the idea has a lifecycle folder under `initiatives/[Initiative]/[Old Project]/[Idea]/`, move it to `initiatives/[Initiative]/[New Project]/[Idea]/`. The idea stays active and its status is unchanged.

**Option C - Delete**
Remove the idea row and its lifecycle folder entirely, with no archive record. Use only when the user explicitly confirms they want no record kept.

---

Present these options clearly and wait for the user's response. Do not proceed until you have a choice for every active idea.

## Step 3 - Execute idea disposition

Apply each choice in the order the user gave them.

### Option A - Archive (drop-idea flow)

For each idea the user wants to archive:

1. Follow the full **drop-idea** workflow (see `skills/drop-idea/SKILL.md`) for each idea individually. Use the project removal as the reason if the user does not supply a specific one.
2. Move the idea's lifecycle folder to an `archive/` bundle at the repo root. Include the `outputs/` subfolder in the move - finished deliverables travel with the work that produced them.
3. Record the idea in `history/dropped-history.md` (keep `ideas.md` as link-only for dropped history).
4. Remove any **Awaiting your approval** row for it in `DASHBOARD.md`.

### Option B - Move to another project

For each idea the user wants to move:

1. Confirm the destination project exists in the same initiative (it must already be in **Active Projects**). If it does not exist, offer to create it with the **add-project** skill first.
2. Move the idea row from the **## Project: [Old]** section to the **## Project: [New]** section in `ideas.md`. Keep all column values (Status, Priority, Last updated, Notes) intact. Update **Last updated** to today.
3. If a `initiatives/[Initiative]/[Old Project]/[Idea]/` folder exists, move it to `initiatives/[Initiative]/[New Project]/[Idea]/` using a git-aware move (`git mv`) to preserve history.
4. Update any links in `ideas.md`, `DASHBOARD.md`, or wiki files that referenced the old folder path.

### Option C - Delete

For each idea the user wants to delete:

1. Confirm once more that the user wants no record. State clearly in chat that this cannot be undone via the skill.
2. Remove the idea row from `ideas.md`.
3. Delete the `initiatives/[Initiative]/[Project]/[Idea]/` folder if it exists.
4. Remove any **Awaiting your approval** row for it in `DASHBOARD.md`.

## Step 4 - Remove the project

Once all ideas are resolved:

1. Remove the **## Project: [Name]** section from `ideas.md`. If it still has placeholder rows (empty or `*(Add ideas here)*`), remove those too.
2. Remove the project row from **## Projects**.
3. Add a row to **## Closed Projects** at the bottom of `ideas.md` with:
   - Project name
   - Today's date
   - A short closure summary (outcome and/or reason)
   - Ask the user for wording if it is not obvious.
4. If the initiative uses a project-level history file, append the same closure record in `history/`.
5. Remove or archive `initiatives/[Initiative]/[Project Name]/`:
   - If it is now empty (only `.gitkeep`, `00-how-to-use.md`, `repo/` placeholder, or no files), delete it entirely.
   - If any files remain (for example a `sources/` or `outputs/` subfolder the user wants to keep), ask the user whether to move those files elsewhere or leave the folder without a project row.
6. Remove `00-how-to-use.md` in that project folder when the folder is being deleted.

## Step 5 - Wiki and tracker hygiene

1. **DASHBOARD.md** - Confirm all **Awaiting your approval** rows tied to this project are cleared. Update **Last initiative work** to today if this session involved substantive changes.
2. **wiki/log.md** - Append a dated entry: `## [YYYY-MM-DD] update | Project [Name] removed`. In the body, note what happened to each idea (archived, moved, deleted) and confirm the folder is gone.
3. **wiki/index.md** - Remove or update any cross-reference entries that pointed at pages or artifacts under the removed project. Do not delete wiki pages; retire obsolete ones to `wiki/.archive/` per `SYSTEM_OVERVIEW.md`.

## Completion summary (return to user)

- Initiative and project name removed.
- What happened to each idea (archived to path / moved to project / deleted).
- Files and folders touched or removed (list them).
- Confirmation that the tracker approval queue is clean.
- Any wiki updates made.

## Guardrails

- Never remove the **General** project from an initiative without explicit confirmation. It is the default bucket and removing it can leave ungrouped ideas with no home.
- Do not silently delete idea folders. Always present Option A / B / C for active ideas and wait for the user's choice.
- Do not delete wiki pages. Retire obsolete pages to `wiki/.archive/` only.
- `ideas.md` **## Done** and **## Dropped** sections should remain link-only pointers to history files. Record idea-level history in `history/done-history.md` and `history/dropped-history.md`. The **## Closed Projects** table is updated in Step 4 when the project is closed.
- Keep **Project** and folder names aligned at all times. If a move is partial (for example disk folder moved but table row not yet updated), finish the table update before summarizing.
