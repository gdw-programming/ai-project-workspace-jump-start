# Upstream-Note Accountability Plan

**Status**: Planned
**Scope**: Make required upstream-note planning and review checks explicit and verifiable.

## Intake Assessment

| Finding | Applicability | Disposition |
|---|---|---|
| Upstream-notes feature | The notes directory, gitignore exception, README, initialization setup, global rule, and review checklist are already present. | Improve only the planning and checklist wording; do not recreate the feature or copy the obsolete combined `commands/development.md` layout from the intake. |

## Planned Work

1. Refine the upstream-notes rule in `context.global.md` so planning explicitly scans existing notes and lists each relevant note to create or update as a plan item, while retaining the existing requirement to capture template-agnostic findings.
2. Expand the `commands/review-change-set.md` checklist so it verifies that new or updated findings are captured and that revising a previously sent finding sets `date-updated` and `status: needs-resend`.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- Planning identifies relevant upstream findings and records their capture or revision as explicit plan items.
- Review checks that findings are captured and that revised sent findings have the required metadata.
