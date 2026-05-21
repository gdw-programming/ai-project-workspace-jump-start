# Review Change Set

**Purpose**: Verify a change set is consistent, correct, and ready to record
**Pattern**: Review all version-controlled files in the current change set (exclude gitignored and intentionally untracked files) against established context rules, fix all issues found, re-read changed files to verify no fix introduced a new inconsistency, then report
**Context**: context.global.md + ../STATUS.md + all version-controlled files in the current change set
**Checklist**:
- Logical consistency, clarity, and alignment with project workflow goals; no rule or constraint conflicts with an existing rule in another context file
- Compliance with all context and documentation rules (DRY, Minimal Context, Workflow Agnostic, Reference Validation, Language Standards, Markdown Links, Context Framing)
- All file references and links are correct and point to existing files
- Workspace tree in STATUS.md and README files reflect all files in this change set — treat them as current
- BACKLOG.md and CHANGELOG.md are current — any project deliverable items completed in this change set are recorded with contributor name and date; context system maintenance is not recorded; age-out criteria in BACKLOG.md has been applied and stale entries removed
- Auto-sync targets (root README.md, STATUS.md, BACKLOG.md, CHANGELOG.md) are consistent with current content — if out of sync, fix immediately as a dependency
- Staged/unstaged cross-check: any reference in a staged file to another file (import, path, link) must resolve against staged content — an unstaged file referenced by committed code will break anyone pulling the branch
- Dependent context files updated: all context files (domains/, tools/, commands/, context.*.md) that reference deleted or renamed code, APIs, or file paths are updated in this change set
- Knowledge capture: identify any framework behavior, fragile patterns, or tool internals discovered during this work — verify they are captured in the appropriate context files per the Knowledge Capture rule before closing
- No non-productive content: remove any files or sections that serve no ongoing operational purpose - initialization summaries, one-time status dumps, redundant checklists, or content that duplicates what a live context file already provides authoritatively
