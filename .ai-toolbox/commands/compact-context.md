# Compact Context

**Aliases**: `compact-context`
**Purpose**: Reduce natural-language context while preserving purpose, capabilities, structure, and operational content
**Pattern**: Apply `patterns/context-compaction.md`
**Context**: `context.global.md` + target context file + linked contexts
**Trigger**: User request or planned maintenance sweep

## Process
1. Confirm target is natural-language context file. Skip code, config, data, and backup files unless explicitly requested.
2. Read target and linked contexts to identify purpose, capabilities, requirements, exceptions, references.
3. Preserve protected regions and exact tokens per `patterns/context-compaction.md`.
4. Create recoverable original outside context discovery path.
5. Propose focused diff removing filler, hedging, repetition, verbose phrasing while retaining plain readable prose.
6. Validate headings, hierarchy, frontmatter, links, paths, commands, requirements, exceptions, capabilities remain intact.
7. Apply validated change. If validation fails, leave source unchanged or restore original, then report failure.
8. Report target, removed items, preserved items, validation results, backup location.

## Boundaries
- Do not remove information required for system purpose or capabilities.
- Do not convert context into Caveman-style fragments when that reduces readability or interpretation reliability.
- Do not compact toolbox implicitly; use explicit target list.
- Semantic and operational preservation required; token reduction alone is not success.
