# Review Change Set

**Purpose**: Verify a change set is consistent, correct, and ready to record
**Pattern**: Review all version-controlled files in the current change set (exclude gitignored and intentionally untracked files) against established context rules. When issues are found, apply judgment on scope: make small corrections directly (broken links, stale references, isolated wording fixes, single-file line-level changes) then report what was changed for user review; for large issues (structural changes, multi-file impact, or anything requiring a design decision) report the issue and ask the user whether to proceed before acting. After all fixes are applied, re-read changed files to verify no fix introduced a new inconsistency. Report the final review outcome. The user may then stage the fixes and request another review pass to confirm the change set is clean.
**Context**: context.global.md + ../STATUS.md + all version-controlled files in the current change set
**Checklist**:
- Logical consistency, clarity, and alignment with project workflow goals; no rule or constraint conflicts with an existing rule in another context file
- Compliance with all context and documentation rules (DRY, Minimal Context, Workflow Agnostic, Reference Validation, Language Standards, Markdown Links, Context Framing)
- All file references and links are correct and point to existing files
- Workspace tree in STATUS.md and README files reflect all files in this change set — treat them as current
- BACKLOG.md and CHANGELOG.md are current (if the project uses built-in tracking files) — any project deliverable items completed in this change set are recorded with contributor name and date; context system maintenance is not recorded; age-out criteria in BACKLOG.md has been applied and stale entries removed
- Auto-sync targets are consistent with current content — root README.md always; STATUS.md, BACKLOG.md, CHANGELOG.md only if the project uses built-in tracking files — fix any out-of-sync targets immediately as a dependency
- Staged/unstaged cross-check: any reference in a staged file to another file (import, path, link) must resolve against staged content — an unstaged file referenced by committed code will break anyone pulling the branch
- Dependent context files updated: all context files (domains/, tools/, commands/, context.*.md) that reference deleted or renamed code, APIs, or file paths are updated in this change set
- Knowledge capture: identify any framework behavior, fragile patterns, or tool internals discovered during this work — verify they are captured in the appropriate context files per the Knowledge Capture rule before closing
- No non-productive content: remove any files or sections that serve no ongoing operational purpose - initialization summaries, one-time status dumps, redundant checklists, or content that duplicates what a live context file already provides authoritatively
