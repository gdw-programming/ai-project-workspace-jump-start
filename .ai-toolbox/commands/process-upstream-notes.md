# Process Upstream Notes

**Aliases**: `process-upstream-notes`
**Purpose**: Assess a replaced downstream-notes intake and turn applicable, unfinished workspace-system improvements into prioritized plans.
**Precondition**: `.ai-toolbox/context.development.md` exists. If it does not, stop; the project removed its system development files at initialization.
**Pattern**: Reload the current context and intake, assess each finding against the system as it exists now, create a Git branch before editing plans or upcoming work, update a one-to-one set of plans and upcoming-work items, then validate references and ordering.
**Context**: `context.global.md` + `context.steering.md` + `context.development.md` + `upstream-notes/README.md` + `.sandbox/intake/upstream-notes/` + `.ai-toolbox/plans/`
**Example**: “Process Upstream Notes” or “Run `process-upstream-notes`.”

## Procedure

1. Re-read current workspace state at the start of every run. Load the listed contexts, this command, the tracked upstream-notes README, every current intake note, every existing plan, and the Upcoming Work section. Check Git availability, current branch, and worktree state. Do not rely on prior runs or conversation history. Treat `.sandbox/intake/upstream-notes/` as read-only; it is user-provided input.
2. If the intake directory is missing or contains no finding files, stop without changing plans or Upcoming Work and report that there is no intake to process.
3. Before editing any plan or Upcoming Work content, use Git to create a dedicated branch for this intake according to `tools/git.md` and applicable project policy. If already on a branch explicitly dedicated to this intake, continue there. If local or project rules require permission that this invocation does not provide, or existing changes are unrelated or unclear, stop and ask before editing. Follow the project and contributor Git permissions for any further Git operations.
4. Assess each finding against the complete context system and current implementation. Classify it as:
   - generally applicable to projects using this system;
   - applicable only with a particular project type, stack, hosting service, release model, or workflow; or
   - already implemented, partially implemented, or not applicable.
   Verify implementation in the relevant contexts, commands, docs, and system structure. Do not import downstream-specific names, assumptions, policies, or automation into generic guidance. A finding with a reusable principle and project-specific implementation may be planned only for its agnostic principle.
5. Include unfinished, generally applicable work and worthwhile improvements to existing behavior. Do not schedule work that is already adequately implemented. Record concise dispositions for already-covered or inapplicable findings in the relevant plan when useful; exclude them from Upcoming Work.
6. Organize the remaining work into the smallest coherent plan files under `.ai-toolbox/plans/`. Reuse and improve relevant existing plans rather than creating duplicates. Each active plan file represents one upcoming work item; consolidate overlapping findings and plans where that makes the work clearer. Keep each plan actionable with scope, intake applicability decisions, planned changes, completion criteria, and a Git implementation workflow requiring a dedicated branch before implementation and Git-based change tracking.
7. Rewrite Upcoming Work in `context.development.md` in descending priority. Maintain exact one-to-one correspondence: every upcoming item points to one distinct active plan file, and every active plan file has exactly one upcoming item. Use reading order, top to bottom, to express priority and dependencies; do not number items. Place prerequisites before dependent work and state dependencies in the item when useful. Remove completed, duplicate, adequately implemented, or inapplicable work from Upcoming Work. Do not include optional enhancements as active work.
8. Give every upcoming item a concise outcome and a self-contained, pastable command that names its plan file and intended change. The statement must be executable without relying on this intake conversation and must direct the implementer to follow that plan's Git branch and change-tracking workflow.
9. Validate that all plan references resolve, priorities and dependencies follow top-to-bottom reading order, and no active plan is missing from or duplicated in Upcoming Work. Re-read the edited section and plans, then report a short summary of planned work, excluded/covered finding categories, and validation results.

## Constraints

- Follow `context.global.md` for rule authority, context placement, workflow agnosticism, minimal content, and workspace-state awareness.
- This command plans work; do not implement the upstream findings themselves.
- Do not edit the intake, unrelated project files, or user content.
- Preserve useful decisions in existing plans when revising or consolidating them.
- If an intake finding conflicts with the context system, record the conflict and resolve it using the Rule Compliance Gate; do not silently override an established rule.
