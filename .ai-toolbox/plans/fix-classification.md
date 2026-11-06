# Fix Classification Plan

**Status**: Planned
**Scope**: Define `fix` / Fixed consistently across Git and change-set descriptions without assuming a branch name, default branch, or release workflow.

## Intake Assessment

| Intake finding | Applicability and current state | Disposition |
|---|---|---|
| Fix classification | The intake's distinction applies generally. `commands/describe-change-set.md` already separates feature-driven updates from independent defects, but `tools/git.md` has no shared baseline convention. | Add the convention to Git guidance and reference it from existing change-set guidance. Use the project's pre-change committed baseline, not a hard-coded `main` branch. |
| Change-set categories | The current `Updated` and `Fixed` definitions already cover the proposed file-classification test. | Preserve and align those definitions; do not duplicate them as a competing rule. |

## Planned Work

1. Add a concise Team Convention to `tools/git.md`: use `fix` / Fixed only for a defect present in the project's pre-change committed baseline; corrections to unmerged work are part of that feature or change. Do not prescribe a branch name, default branch, or release process.
2. Align `commands/describe-change-set.md` and any existing changelog guidance with that shared definition by reference, retaining the file-level test for deciding between `Updated` and `Fixed` rather than duplicating or weakening the rule.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- Git, change-set, and any existing changelog guidance use `fix` / Fixed only for defects present in the pre-change committed baseline.
- Corrections made while implementing unmerged work are described as part of that feature or change.
- Guidance works without assuming a particular default-branch name or release workflow and does not duplicate the file-level category definitions.

## Plan Completion Workflow

1. Execute plan — Agent
2. Test (if applicable) — Agent
3. Verify plan execution — Developer
4. Remove plan files — Agent
5. Remove plan from `context.development.md` — Agent
6. Update references — Agent
7. Validate plan completion — Developer
8. Run Review Change Set — Developer
9. Run Describe Change Set — Developer
10. Record and submit the change — Developer

The agent stops after step 2 and continues with step 4 only after the developer confirms step 3.
