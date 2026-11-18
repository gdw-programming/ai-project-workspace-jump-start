# Documentation Continuous Improvement Plan

**Status**: Planned
**Scope**: Establish a project-wide expectation to improve the relevant documentation when project work or feedback reveals it is wrong, unclear, or incomplete, without duplicating context-specific correction rules.

## Intake Assessment

| Intake finding | Applicability and current state | Disposition |
|---|---|---|
| `ai-toolbox--documentation-continuous-improvement.md` | The expectation applies across project types. `project/standards.md` currently lists documentation deliverables but does not state how project documentation is maintained. `context.global.md` Correction Integration covers corrections to agent context, not project documentation generally. | Add a concise Documentation Requirements item to `project/standards.md`. Make same-change-set correction the norm when practical, not an absolute requirement that expands unrelated work. |

## Planned Work

1. Add a Documentation Continuous Improvement requirement to `project/standards.md`: use project work and reviewer, stakeholder, or user feedback to identify documentation that is wrong, unclear, or incomplete; update the relevant document in the same change set when practical.
2. Keep the guidance focused on documentation maintenance and distinct from `context.global.md` Correction Integration, which applies to corrections of agent context.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- `project/standards.md` directs contributors to improve the relevant project documentation when work or feedback reveals incorrect, unclear, or missing information.
- The guidance recommends making the documentation correction in the same change set when practical and does not duplicate or broaden the agent-context Correction Integration rule.

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
