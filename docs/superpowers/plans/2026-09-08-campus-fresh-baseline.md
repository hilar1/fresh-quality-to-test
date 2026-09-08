# Campus Fresh Baseline Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a clean Git repository at `E:\project\softtest project` containing only the DailyFresh application baseline and project provenance, ready for three students to improve through independent commits.

**Architecture:** Preserve the original Django application boundaries so later changes remain easy to compare with the imported baseline. Remove every prior testing artifact and machine-specific file, then record the source and known startup limitations without claiming the baseline is already compatible with a current runtime.

**Tech Stack:** Git, GitHub, Python, Django, SQLite for later local development

**Spec:** `docs/superpowers/specs/2026-09-08-campus-fresh-baseline-design.md`

## Global Constraints

- The destination is exactly `E:\project\softtest project`.
- Treat `E:\project\soft_test` as read-only reference material and never modify, delete, rename or format any file under it.
- The GitHub repository name is `campus-fresh-quality-lab` unless that name is unavailable.
- GitHub visibility is private by default.
- Do not copy prior test code, reports, spreadsheets, presentations, videos, virtual environments, databases, IDE settings or temporary files.
- Preserve the original application source as the initial baseline; do not silently fix defects during import.
- Record the original project URL found in the source and the fact that the imported snapshot came from a prior course reference package.
- Do not generate module-one test cases or automated tests.

---

### Task 1: Create the clean local baseline

**Files:**
- Create: `E:\project\softtest project\apps/**`
- Create: `E:\project\softtest project\daily_fresh_demo/**`
- Create: `E:\project\softtest project\templates/**`
- Create: `E:\project\softtest project\static/**`
- Create: `E:\project\softtest project\sql/**`
- Create: `E:\project\softtest project\manage.py`
- Create: `E:\project\softtest project\requirements.txt`

**Interfaces:**
- Consumes: source snapshot under `E:\project\soft_test\daily-fresh-master\daily-fresh-master`
- Produces: a clean source tree without prior `tests.py` files or machine state

- [ ] **Step 1: Verify that the destination is absent or empty**

Run `Get-ChildItem -Force -LiteralPath 'E:/project/softtest project'` if it exists. Stop rather than overwrite unrelated files.

- [ ] **Step 2: Create the destination and copy the allowlisted source paths**

Copy only `apps`, `daily_fresh_demo`, `templates`, `static`, `sql`, `manage.py`, `requirements.txt`, and the original README for provenance review.

- [ ] **Step 3: Remove excluded files from the staged copy**

Remove all `tests.py`, `__pycache__`, `*.pyc`, `.venv`, `.idea`, `db.sqlite3`, Office documents and prior delivery artifacts. Confirm no excluded names remain.

- [ ] **Step 4: Verify the copied source inventory**

Compare the allowlisted directories with the source and confirm that application files other than the explicitly excluded test files are present.

### Task 2: Add repository metadata and provenance

**Files:**
- Create: `E:\project\softtest project\.gitignore`
- Create: `E:\project\softtest project\README.md`
- Create: `E:\project\softtest project\NOTICE.md`
- Create: `E:\project\softtest project\docs\superpowers\specs\2026-09-08-campus-fresh-baseline-design.md`
- Create: `E:\project\softtest project\docs\superpowers\plans\2026-09-08-campus-fresh-baseline.md`

**Interfaces:**
- Consumes: the clean source tree from Task 1
- Produces: explicit provenance, current baseline status and collaboration rules

- [ ] **Step 1: Write `.gitignore`**

Ignore Python caches, local virtual environments, SQLite databases, IDE state, secrets, logs, coverage outputs, generated reports and Office temporary files.

- [ ] **Step 2: Replace the inherited README**

State the course-project purpose, baseline scope, three business domains, current compatibility status and next steps. Do not copy claims from the prior report.

- [ ] **Step 3: Write `NOTICE.md`**

Record `https://github.com/weilanhanf/daily_fresh_demo` as the apparent upstream link found in the template footer. State that the local snapshot came from a prior course reference package and that its exact upstream commit is unknown.

- [ ] **Step 4: Copy the approved design and execution plan**

Keep both documents in the repository so future commits can be assessed against the agreed boundary.

### Task 3: Initialize and verify Git history

**Files:**
- Create: `E:\project\softtest project\.git/**`

**Interfaces:**
- Consumes: repository contents from Tasks 1 and 2
- Produces: branch `main`, baseline commit and tag `baseline-v0.1`

- [ ] **Step 1: Initialize Git on `main`**

Run `git init -b main` in the exact destination.

- [ ] **Step 2: Inspect staged scope before committing**

Run `git status --short` and confirm no prior reports, tests, databases or virtual environments appear.

- [ ] **Step 3: Create the baseline commit**

Commit with message `chore: import DailyFresh application baseline` using the current user's configured Git identity.

- [ ] **Step 4: Tag the baseline**

Create annotated tag `baseline-v0.1` with message `Imported application baseline before team quality improvements`.

- [ ] **Step 5: Verify history and ignored files**

Run `git log --oneline --decorate -3`, `git status --short`, and an ignored-file scan.

### Task 4: Create and connect the GitHub repository

**Files:**
- Modify: `E:\project\softtest project\.git\config`

**Interfaces:**
- Consumes: verified local `main` branch and baseline tag
- Produces: private GitHub repository with `origin`, pushed `main`, and pushed `baseline-v0.1`

- [ ] **Step 1: Create the private GitHub repository**

Use the currently signed-in GitHub account. Create `campus-fresh-quality-lab` without generated README, license or `.gitignore` because the local repository already owns those files.

- [ ] **Step 2: Add `origin`**

Use the exact clone URL returned by GitHub and run `git remote add origin <clone-url>`.

- [ ] **Step 3: Push branch and tag**

Run `git push -u origin main` and `git push origin baseline-v0.1`.

- [ ] **Step 4: Verify remote state**

Confirm `git remote -v`, the upstream branch, the remote repository visibility and the presence of the baseline tag.
