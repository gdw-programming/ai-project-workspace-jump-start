# Describe Change Set

**Purpose**: Generate a descriptive summary of the current change set suitable for recording (commit message, PR description, changelog entry, etc.)
**Precondition**: All files intended for this commit must be staged before running this command — `git diff --cached` only reflects staged content. If there are unstaged edits that are not intentionally excluded, stop and ask the user whether they want the command to describe only the staged change set or whether the file should be staged before continuing. If the user confirms a file is intentionally left unstaged, the user must explicitly confirm that the commit is meant to exclude it and that the final commit still works without that file. Do not attempt to describe the change set from session memory. This command is stateless: every run starts by refreshing the current git/workspace state directly and discarding any assumptions from earlier turns.
**Pattern**: First retrieve the complete list of version-controlled files in the current change set (exclude gitignored and intentionally untracked files). Then, from the live repo state at command start, refresh the current staged/unstaged status and re-read the staged diff before summarizing. If user edits, staging changes, or other workspace modifications happened between turns, they must be reflected immediately in the output. For each file, run `git diff --cached` against the previously committed version and describe only what the diff shows — not what editing steps were taken during the session to produce it. If the diff shows rule A replaced by rule B, describe rule B's content relative to rule A; do not describe intermediate steps like "merged two rules." Do not use conversational session terms (e.g. "Phase 3", "this session", "as discussed") — the output must be self-contained and meaningful to anyone reading git history with no knowledge of the conversation. Produce output covering ALL files in the change set in the exact plain text format below. No markdown, no bold, no extra formatting. See the Workspace State Awareness rule in `context.global.md` for the root requirement.
**Context**: context.global.md + all version-controlled files in the current change set + their prior recorded history
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
- **Integrated into** — existing files modified only to wire in new files from this change set
- **Updated** — existing files with substantive content changes, including feature-driven synchronization work: renamed functions updated wherever referenced, stale comments corrected because the code they described changed, outdated API references updated to match the current implementation, auto-sync target updates (README.md, STATUS.md, BACKLOG.md, CHANGELOG.md) kept current as part of the change set. These are part of the feature work.
- **Deleted** — files removed as part of the development workflow or feature work, including cleanup, dependency removals, or file deletions required by a refactor. A deleted file is not a bug fix simply because the removal corrected inconsistency; if the file was removed because of the feature or workflow, it belongs here.
- **Fixed** — existing files where content was incorrect or broken in previously committed code, independent of the current feature. A fix corrects something that was wrong before the current work started and would remain wrong if the feature were reverted. Use the test: would this file need changing without this feature or workflow action? If not, it is Updated or Deleted, not Fixed.

Omit any category that has no files.
