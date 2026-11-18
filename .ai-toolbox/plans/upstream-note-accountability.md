# Upstream-Note Accountability and Planning Plan

**Status**: Planned
**Scope**: Make upstream-note assessment during planning, review, and manual sending explicit and verifiable without recreating the existing feature or requiring a particular toolchain.

## Intake Assessment

| Intake finding | Applicability and current state | Disposition |
|---|---|---|
| `ai-toolbox--branch-protection.md` | Feature-branch-only protection is already an optional project choice in initialization. A universal branch rule would override project policy. | Covered; keep branch policy optional and do not impose a branch name or strategy. The upstream-note accountability recommendations are covered by this plan. |
| `ai-toolbox--change-set-categories.md` | `commands/describe-change-set.md` already includes feature-driven synchronization in `Updated` and a test for distinguishing `Fixed`. | Covered by the existing descriptions and the Fix Classification plan; do not duplicate category definitions. |
| `ai-toolbox--compatibility-notes.md` | The compatibility principle applies across project types and concerns the Present-Tense Voice rule. | Include in the Current-State Documentation plan. |
| `ai-toolbox--documentation-continuous-improvement.md` | Feedback-driven improvement of project documentation applies across project types. `project/standards.md` currently lists document types but not this maintenance expectation. | Add a dedicated Documentation Continuous Improvement plan. |
| `ai-toolbox--dropped-approaches-undocumented.md` | The principle applies across project types and concerns the Present-Tense Voice rule. | Include in the Current-State Documentation plan. |
| `ai-toolbox--fix-classification.md` | The baseline distinction applies generally, but the intake's `main` assumption does not. | Improve the existing Fix Classification plan using the project's pre-change committed baseline. |
| `ai-toolbox--fix-security-advisories.md` | `commands/fix-security-advisories.md` defines a package-manager-neutral workflow, with npm-specific behavior isolated in `tools/package-managers/npm.md`. | Covered generically; do not import the intake's npm-only branch name, PR labels, audit-list maintenance, or validation commands. |
| `ai-toolbox--link-staged-files.md` | `context.global.md` defines which files should be linked and allows same-change-set targets; `commands/review-change-set.md` checks target availability and reference type. | Covered; no plan item needed. |
| `ai-toolbox--multi-pr-releases.md` | The label-driven version-bump flow and release-wide PR coordination are not part of this workspace system. | Exclude the release-specific workflow. |
| `ai-toolbox--release-tag-workflow.md` | The proposed workflow depends on a downstream version-bump pipeline and package-version semantics. | Exclude; it is not an agnostic context-system improvement. |
| `ai-toolbox--update-changelog-bump-branch.md` | The proposed command depends on a downstream release branch, version-bump PR, and changelog process not present here. | Exclude the release-specific workflow. |
| `ai-toolbox--upstream-notes-feature.md` | The notes directory, metadata, initialization behavior, global rule, and review checklist already exist. The process command also requires intake assessment and plan maintenance. | Do not recreate the feature; improve planning and review accountability as described below. |
| `ai-toolbox--upstream-notes-send-command.md` | The concern about accurate status metadata and confirming what was actually sent applies generally. The proposed Node/npm script and archive workflow do not fit a toolchain-agnostic system. | Add safe, manual send and status-update guidance to the existing upstream-notes README; do not add a scripted command. |

## Planned Work

1. Clarify the `context.global.md` Upstream Notes rule so planning assesses existing notes against proposed work and names each applicable note creation or revision as an explicit plan item.
2. Strengthen the `commands/review-change-set.md` checklist to require an explicit upstream-note disposition for every change set, verify applicable findings are captured, and confirm that revising a previously sent finding sets `date-updated` and `status: needs-resend`.
3. Extend `.ai-toolbox/upstream-notes/README.md` with a safe manual send sequence: identify the notes being sent, do not mark them sent before the user confirms what was actually sent, update only the selected note's metadata, and verify the marked notes match the confirmed send. Preserve `date-updated` when recording a send.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- Planning assesses existing upstream notes and makes each applicable capture or revision an explicit plan item.
- Review explicitly accounts for upstream notes on every change set, verifies applicable findings are captured, and checks resend metadata for revised sent findings.
- The README provides a toolchain-agnostic manual send process that does not mark notes sent before confirmation and keeps recorded metadata aligned with the confirmed send.

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
