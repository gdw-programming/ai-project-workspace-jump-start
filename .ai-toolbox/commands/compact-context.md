# Compact Context

**Purpose**: Reduce natural-language context while preserving purpose, capabilities, structure, and exact operational content
**Pattern**: Apply `patterns/context-compaction.md`
**Context**: `context.global.md` + target context file + relevant linked contexts
**Trigger**: User requests context compaction, or a planned maintenance sweep selects a target file

## Process

1. Confirm the target is a natural-language context file. Skip code, configuration, structured data, and backup files unless explicitly included by the user.
2. Read the target and its relevant linked contexts to identify purpose, capabilities, requirements, exceptions, and references.
3. Preserve protected regions and exact tokens defined by `patterns/context-compaction.md`.
4. Create a recoverable original outside the context discovery path.
5. Propose a focused diff that removes filler, hedging, repetition, and verbose phrasing while retaining plain readable prose.
6. Validate that headings, hierarchy, frontmatter, links, paths, commands, requirements, exceptions, and capabilities remain intact.
7. Apply only a validated change. If validation fails, leave the source unchanged or restore the accepted original, then report the failure.
8. Report the target, what was removed, what was preserved, validation results, and backup location.

## Boundaries

- Do not remove information merely because it is verbose; retain information required for the system's purpose or capabilities.
- Do not convert context into Caveman-style fragments when that would reduce readability or interpretation reliability.
- Do not compact the entire toolbox implicitly. Use an explicit target list for maintenance sweeps.
- Do not treat token reduction alone as success; semantic and operational preservation are required.
