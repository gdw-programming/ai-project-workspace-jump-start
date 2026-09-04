# Context Compaction

Reusable approach for reducing natural-language context without losing meaning, structure, or operational capability.

## Scope
Apply to Markdown and natural-language context files. In mixed-content files, compact prose only. Code, configuration, commands, and structured data are read-only unless explicitly targeted.

## Preserve Exactly
- Fenced and indented code blocks
- Inline code, URLs, Markdown links, and file paths
- Commands, environment variables, technical terms, proper nouns, dates, versions, numeric values
- YAML frontmatter
- Headings, section order, bullet hierarchy, numbered lists, table structure
- Requirements, exceptions, decision criteria, workflows, capability descriptions

## Compact
- Remove filler, pleasantries, hedging, throat-clearing, repeated conclusions
- Replace verbose phrases with direct wording
- Merge bullets expressing same requirement
- Keep minimum examples needed to establish pattern
- Prefer plain concise prose over stylized shorthand

## Safety Gate
1. Identify file purpose and required capabilities.
2. Mark protected regions and exact tokens.
3. Produce focused diff.
4. Verify references, requirements, exceptions, workflow steps remain present.
5. Reject if meaning, capability, structure, or exact tokens change unintentionally.
6. Keep recoverable original outside context discovery path until accepted.

Never compact backup files. If validation fails, leave source unchanged or restore accepted original. Do not repeat full-file compaction after failed validation; make a targeted correction or stop.

## Ongoing Use
Apply when authoring new context and during maintenance. Use `commands/compact-context.md` for explicit pass.
