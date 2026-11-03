# Current-State Documentation Plan

**Status**: Planned
**Scope**: Keep committed code comments and documentation focused on current behavior.

## Intake Assessment

The Present-Tense Voice rule in `context.global.md` already limits change-referencing language but does not explicitly exclude approaches that were tried and dropped before commitment. This is broadly applicable: readers of committed state need the resulting behavior, not a history of uncommitted experiments.

## Planned Work

1. Extend Present-Tense Voice in `context.global.md` to prohibit documenting approaches tried and dropped before commitment in code comments, documentation, or changelogs.
2. State the narrow exception: a verified platform fact may be recorded as a plain current-state fact in the relevant domain context; describe the resulting behavior elsewhere.

## Implementation Workflow

Before implementing this plan, use Git to create a dedicated branch for the work, following `tools/git.md` and applicable project policy. Verify the active branch and use Git status/diffs to track implementation changes. Follow the project and contributor Git permissions.

## Completion Criteria

- Current-state documentation and comments do not explain behavior by recounting discarded, uncommitted approaches.
- Verified platform facts remain eligible for relevant context when phrased as current facts rather than experiment history.
