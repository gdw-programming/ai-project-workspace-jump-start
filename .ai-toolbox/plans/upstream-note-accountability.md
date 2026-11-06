# Upstream-Note Accountability and Planning Plan

**Status**: Planned
**Scope**: Make upstream-note assessment during planning and required review checks explicit and verifiable without recreating the existing feature.

## Intake Assessment

| Intake finding | Applicability and current state | Disposition |
|---|---|---|
| `ai-toolbox--branch-protection.md` | The initialization workflow already offers feature-branch-only protection as a project choice. | Covered; do not impose a universal branch name or branching policy. |
| `ai-toolbox--change-set-categories.md` | `commands/describe-change-set.md` already distinguishes feature-related updates from independent defects. | Covered there; the separate Git baseline convention remains in the Fix Classification plan. |
| `ai-toolbox--compatibility-notes.md` | The compatibility principle applies across project types and concerns the existing Present-Tense Voice rule. | Include in the Current-State Documentation plan. |
| `ai-toolbox--dropped-approaches-undocumented.md` | The principle applies across project types and concerns the existing Present-Tense Voice rule. | Include in the Current-State Documentation plan. |
| `ai-toolbox--fix-classification.md` | The baseline distinction applies generally, but the intake's `main` assumption does not. | Improve the existing Fix Classification plan using the project's pre-change committed baseline. |
| `ai-toolbox--fix-security-advisories.md` | The workspace already has a package-manager-neutral command and an npm implementation. The proposed branch, PR-label, and validation rules are npm/release-policy-specific. | Covered at the generic level; do not import downstream branch names, PR labels, or project-specific validation. |
| `ai-toolbox--link-staged-files.md` | `context.global.md` already limits links to committed or same-staged targets, links reader-facing documentation, and names code files by path. | Covered; no plan item needed. |
| `ai-toolbox--multi-pr-releases.md` | The label-driven version-bump and PR release model is not part of this workspace's general system. | Exclude the release-specific workflow. |
| `ai-toolbox--release-tag-workflow.md` | The proposed workflow depends on a downstream version-bump pipeline and package-version semantics. | Exclude; it is not an agnostic context-system improvement. |
| `ai-toolbox--update-changelog-bump-branch.md` | The proposed command depends on a downstream release branch and changelog process not present here. | Exclude the release-specific workflow. |
| `ai-toolbox--upstream-notes-feature.md` | The directory guidance, global rule, initialization behavior, and review checklist already exist. | Improve only the planning and checklist requirements below; do not recreate the feature or copy the obsolete combined `commands/development.md` layout. |

## Planned Work

1. Clarify the `context.global.md` Upstream Notes rule so planning assesses existing notes against the proposed work and names each applicable note creation or update as an explicit plan item.
2. Strengthen the `commands/review-change-set.md` checklist to require an explicit upstream-note disposition for every change set, verify that applicable findings are captured, and confirm that revising a previously sent finding sets `date-updated` and `status: needs-resend`.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- Planning assesses existing upstream notes and makes each applicable capture or revision an explicit plan item.
- Review explicitly accounts for upstream notes on every change set, verifies applicable findings are captured, and checks resend metadata for revised sent findings.

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
