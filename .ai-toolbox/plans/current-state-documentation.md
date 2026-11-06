# Current-State Documentation and Compatibility Notes Plan

**Status**: Planned
**Scope**: Keep comments and documentation focused on current behavior while allowing actionable compatibility guidance for existing objects and data.

## Intake Assessment

| Intake finding | Applicability and current state | Disposition |
|---|---|---|
| Dropped approaches are undocumented | The Present-Tense Voice rule in `context.global.md` limits change-referencing language but does not explicitly exclude approaches tried and dropped before commitment. Readers of current state need the resulting behavior, not uncommitted experiment history. | Add a clear rule against documenting dropped approaches; allow verified platform facts to be recorded as current facts in the relevant domain context. |
| Compatibility notes for earlier-version objects | The current rule has no exception for actionable guidance about objects or data created under earlier versions. This need is common across project types. | Add a narrow exception for describing current effects and necessary user actions, not the history of the change. |

## Planned Work

1. Extend Present-Tense Voice in `context.global.md` to prohibit documenting approaches tried and dropped before commitment in code comments, documentation, or changelogs.
2. Preserve the narrow platform-fact exception: record a verified fact in the relevant domain context as a current-state fact, not as experiment history.
3. Add a compatibility exception allowing comments and documentation to explain how the current version affects earlier-version objects or data and what action is needed, when that guidance helps a user or developer act on existing objects.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- Comments, documentation, and changelogs do not recount approaches tried and dropped before commitment.
- Relevant domain contexts may state verified platform facts as current facts, without experiment history.
- Compatibility guidance may describe current effects on earlier-version objects or data and the action needed, without narrating the change's history.

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
