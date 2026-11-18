# Review Change Set

**Aliases**: `review-change-set`
**Purpose**: Verify change set is consistent, correct, and ready to record.
**Pattern**: Review all version-controlled files in change set against context rules. Stateless: re-read git/workspace state directly at command start every run. Reflect user edits, staging changes, branch state, or file updates immediately. Check if unstaged edited files are required by staged files — if so, ask user if exclusion is intentional and confirm commit works without it. Perform synchronization edits (tree listings, auto-sync targets) during review. Apply scope judgment: fix small issues directly (links, stale references, single-file line edits, sync drift); report large issues (structural, multi-file, design decisions) and ask user before acting. Re-read changed files after fixes to confirm consistency. Report final outcome. (See `context.global.md` Workspace State Awareness rule).
**Context**: `context.global.md` + `../STATUS.md` + version-controlled files in change set

## Checklist
- **Stateless execution**: re-read git/workspace state at command start every run; do not reuse turn results.
- **User manual actions included**: reflect file edits, staged/unstaged changes, branch changes discovered since previous run.
- **Unstaged-file dependency check**: check if unstaged edited files are required by staged files; ask user if exclusion is intentional.
- **Logical consistency & rule compliance**: no rule conflicts across contexts; enforce DRY, Minimal Context, Workflow Agnostic, Reference Validation, Language Standards, Markdown Links, File Reference Standards, Context Framing.
- **Reference validation**: file references and links resolve, except permitted plain-text planned, deleted, or local targets under File Reference Standards and Shared File Dependencies.
- **Reference type & target availability**: documentation files are linked; source, config, script, and test files use repository-relative plain-text paths; linked targets are committed or in the same staged change set and not being deleted (no links to untracked, gitignored, planned, or deleted files).
- **Shared file dependencies**: inspect linked and plain-text file and directory paths in changed version-controlled content, including staged and unstaged versions when applicable. Check concrete paths against Git's tracked and ignore status (for example, `git check-ignore -v -- <path>`); tracked files are not ignored even when patterns match, and non-ignored planned paths need not exist yet. Apply Shared File Dependencies to every changed file and Shared Plan References to plans intended for version control. Report violations; replace dependencies on ignored contributor files with shared information, or document legitimate local setup or inputs and missing-file behavior. Remove ignored paths from shared plans or carry their relevant findings into the plan without local paths. If Git status or applicable ignore rules cannot be verified, report the check as unresolved and the review as not ready. When staged and working-tree ignore rules differ, verify against the corresponding state or report the check as unresolved.
- **Workspace tree sync**: update tree/directory listings in `STATUS.md`, `README` files to reflect change set files.
- **Backlog & Changelog sync**: `BACKLOG.md` and `CHANGELOG.md` current (if using built-in tracking); record completed deliverables with contributor name and date; apply age-out criteria.
- **Auto-sync target consistency**: sync root `README.md` (always), `STATUS.md`, `BACKLOG.md`, `CHANGELOG.md` (if used) as dependencies.
- **Staged/unstaged cross-check**: references in staged files to other files must resolve against staged content.
- **Dependent context files updated**: update context files referencing deleted/renamed code, APIs, or paths.
- **Knowledge capture**: verify framework behaviors, fragile patterns, tool internals are recorded in context files.
- **Upstream notes**: state an explicit upstream-note disposition for every change set (captured, revised, or none applicable, with reason); verify applicable template-agnostic findings are captured in `.ai-toolbox/upstream-notes/`; for each revised previously sent finding, confirm `date-updated` is set and `status: needs-resend`.
- **No non-productive content**: remove files/sections serving no ongoing operational purpose.
