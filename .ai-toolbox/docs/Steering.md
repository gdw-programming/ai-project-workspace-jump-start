# Steering Context

Use the steering context when a request does not clearly map to one context area.

## Common Prompts

### Find relevant context
> "Load `.ai-toolbox/context.steering.md` and identify the context files relevant to [request]."

### Add a routing entry
> "Update `.ai-toolbox/context.steering.md` with keywords for [topic] and its target context."

### Review routing
> "Check the steering index for the contexts relevant to [request]."

## What Belongs in the Steering Index

| Entry | Purpose |
| --- | --- |
| Keywords or topics | Terms an agent can match to a request |
| Target context | Directory or file to load after the match |
| Routing coverage | Common topics that need a predictable context path |

Keep the index terse. Detailed rules and explanations belong in the target context or its human-facing guide.

## Example

[context.steering.md](../context.steering.md) maps topics such as project scope, reusable patterns, tools, and operations to the context area that should be loaded.

## Add or Update an Entry

1. Add a concise keyword or topic phrase to the table in [context.steering.md](../context.steering.md).
2. Point it to an existing directory or file under `domains/`, `patterns/`, `tools/`, `project/`, or `commands/`.
3. Keep overlapping entries consistent and remove entries whose target no longer exists.
4. Use the index only when routing is unclear; it is not part of the always-loaded Core context.

---

Load the target context after the steering index identifies the relevant area.
