# Context Compaction

Reusable approach for reducing natural-language context without losing meaning, structure, or operational capability.

## Scope

Apply to Markdown and other natural-language context files. In mixed-content files, compact prose only. Treat code, configuration, commands, and structured data as read-only unless the task explicitly targets them.

## Preserve Exactly

- Fenced and indented code blocks
- Inline code, URLs, Markdown links, and file paths
- Commands, environment variables, technical terms, proper nouns, dates, versions, and numeric values
- YAML frontmatter
- Headings, section order, bullet hierarchy, numbered lists, and table structure
- Requirements, exceptions, decision criteria, workflows, and capability descriptions

## Compact

- Remove filler, pleasantries, hedging, throat-clearing, and repeated conclusions
- Replace verbose phrases with direct wording
- Merge bullets that express the same requirement
- Keep the smallest number of examples needed to establish a pattern
- Prefer plain concise prose over stylized shorthand

## Safety Gate

Before applying a compaction:

1. Identify the file's purpose and required capabilities.
2. Mark protected regions and exact tokens.
3. Produce a focused diff rather than rewriting the whole file.
4. Verify references, requirements, exceptions, and workflow steps remain present.
5. Reject the result if meaning, capability, structure, or exact tokens change unintentionally.
6. Keep a recoverable original outside the context discovery path until the result is accepted.

Never compact a backup file. If validation fails, leave the source unchanged or restore the accepted original. Do not repeat full-file compaction after a failed validation; make a targeted correction or stop.

## Ongoing Use

Apply this pattern when authoring new context and during maintenance. Use `commands/compact-context.md` for an explicit compaction pass.
