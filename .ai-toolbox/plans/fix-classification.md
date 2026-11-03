# Fix Classification Plan

**Status**: Planned
**Scope**: Apply one project-agnostic meaning for `fix` / Fixed across Git and change-set descriptions.

## Intake Assessment

The existing Updated and Fixed categories in `commands/describe-change-set.md` already separate feature-driven work from pre-existing defects. The missing piece is a reusable Git convention for commit, PR, and changelog wording. The intake's test against `main` is too repository-specific; use the project's pre-change committed baseline instead.

## Planned Work

1. Add a concise Team Convention to `tools/git.md`: use `fix` / Fixed only for a defect present in the project's pre-change baseline; corrections to unmerged work are part of that feature or change. Avoid assuming a branch name or release workflow.
2. Align `commands/describe-change-set.md` and any existing changelog guidance with that convention by referencing the shared definition, not duplicating it.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- Commit, PR, and changelog terminology uses `fix` / Fixed only for defects that predate the current work in the project's baseline.
- Corrections made while implementing unmerged work are described as part of the feature or change.
- Guidance works with differing default-branch names and project release practices.

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
