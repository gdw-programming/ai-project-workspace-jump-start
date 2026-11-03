# Documentation Reference Policy Plan

**Status**: Planned
**Scope**: Define useful, reliable file references in documentation and change-set review.

## Intake Assessment

| Finding | Applicability | Disposition |
|---|---|---|
| Link staged documentation files | Applies to any project with Markdown documentation and staged changes. | Address in this plan. |
| Branch protection | The initialization flow already offers an explicit project choice and supplies planning-time branch determination when enabled. | Keep branch enforcement configurable; a mandatory feature-branch policy is not suitable for every project. |
| Updated vs. Fixed categories | `commands/describe-change-set.md` already distinguishes feature-driven edits from pre-existing defects. | No category rewrite needed; the separate Git/change-history terminology gap is covered by `fix-classification.md`. |
| Security-advisory workflow | The command and package-manager guidance already provide a manager-neutral, policy-aware entry point and npm implementation. | No further template work; do not import downstream-specific branch names, validation commands, or labels. |
| Multi-PR release guidance | Depends on a label-driven version-bump release workflow, which this workspace does not provide. | Not generally applicable without adopting that optional release model; do not add its conventions to the generic system. |
| Release tags | Depends on the absent version-bump workflow and npm release behavior. | Not generally applicable without an adopted release workflow; do not prescribe npm tags to all projects. |
| Changelog on an open bump PR | Depends on the absent version-bump branch and release process. | Not generally applicable without an adopted release workflow; do not add project-specific branch logic. |
| Upstream-note accountability | The folder, gitignore exception, README, initialization setup, global rule, and review checklist already exist. | The planning/review improvement is covered by `upstream-note-accountability.md`. |
| Dropped approaches in documentation | Applies to any project using this context system. | The present-state writing improvement is covered by `current-state-documentation.md`. |
| `fix` classification across Git and history | `describe-change-set.md` already has a useful pre-existing-defect test, but `tools/git.md` has no shared convention for commit/PR/changelog wording. | Address in `fix-classification.md`, without assuming a `main` branch or a particular release model. |

## Planned Work

1. Replace the conflicting file-reference rules in `context.global.md` with a reader-oriented rule: link documentation readers are likely to follow, name source/config/script/test files by repository-relative path, and link only to files committed already or included in the same staged change set and not being deleted.
2. Update the Markdown Links rule to defer to File Reference Standards, and add the same target-availability and reference-type checks to `commands/review-change-set.md`.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- References to new documentation staged with the change can be linked; links to new untracked or gitignored documentation, planned-but-not-yet-created files, and deleted targets remain disallowed.
- Documentation guides link to other documentation but identify code and configuration by repository-relative path.
- Review guidance checks both reference type and whether linked targets are part of the change.
