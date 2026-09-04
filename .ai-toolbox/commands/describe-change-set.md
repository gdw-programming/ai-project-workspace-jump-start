# Describe Change Set

**Aliases**: `describe-change-set`
**Purpose**: Generate descriptive summary of current change set for recording (commit message, PR description, changelog entry).
**Precondition**: All files intended for commit must be staged before running (`git diff --cached` reflects staged content). If unstaged edits exist, ask user whether to describe staged change set or stage files first. If user confirms file is intentionally unstaged, user must explicitly confirm commit excludes it and final commit works without it. Do not describe from session memory. Refresh git/workspace state directly on invocation.
**Pattern**: Retrieve version-controlled files in change set (exclude gitignored/untracked files). Refresh staged status and re-read staged diff before summarizing. Reflect user workspace modifications immediately. For each file, run `git diff --cached` against committed version and describe diff contents only — do not describe session editing steps. Do not use conversational session terms ("Phase 3", "this session"). Produce self-contained output covering ALL files in change set in plain text format below.
**Context**: context.global.md + version-controlled files in change set + prior recorded history
**Output format** (plain text, copy-paste ready):
```
[Short one-line description]

Created:
-- [filename]: [what it is]

Integrated into:
-- [filename]: [what was wired in]

Updated:
-- [filename]: [what changed]

Deleted:
-- [filename]: [what was removed]

Fixed:
-- [filename]: [what was corrected]
```
**Categories**:
- **Created** — new files with no prior recorded history
- **Integrated into** — existing files modified only to wire in new files from change set
- **Updated** — existing files with substantive content changes, including work performed during the current feature or workflow: renamed functions updated wherever referenced, stale comments corrected because the code they described changed, outdated references synchronized, formatting corrected, compaction edits, and auto-sync target updates (`README.md`, `STATUS.md`, `BACKLOG.md`, `CHANGELOG.md`). These changes belong here even when they correct an inconsistency; they are part of the current work.
- **Deleted** — files removed as part of the current workflow or feature, including cleanup, dependency removals, refactor deletions, and completed backlog items. A deleted file is not `Fixed` merely because its removal corrected an inconsistency.
- **Fixed** — existing files where content was incorrect or broken in previously committed code, independent of the current feature or workflow. The defect must have existed before the current work began and would remain incorrect if the current work were reverted. Use the test: would this file need changing without this feature or workflow action? If not, it is `Updated` or `Deleted`, not `Fixed`. Never use `Fixed` for files or edits created, corrected, or synchronized during the current session or feature work.

Omit any category with no files.
