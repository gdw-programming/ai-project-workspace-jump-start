# Commands — Usage Guide

The `commands/` directory provides operation patterns for common tasks. Command contexts tell AI agents how to approach specific types of work — purpose, a general approach, required context, and an example.

## Common Prompts

### Load a command context
> "Load the review-change-set command for this session."

> "I need to organize my project structure — load the relevant command context."

### Add a command pattern
> "Add a command for [operation] to commands/ following the existing structure."

### Use a command for guidance
> "Based on the project management commands, how should I approach tracking progress?"

### Review available commands
> "What command contexts are available for the current task?"

---

## What's in commands/

One file per command. See [commands/README.md](../commands/README.md) for the full index grouped by category.

Key commands:

| File | Purpose |
|------|---------|
| [initialization.md](../commands/initialization.md) | Project setup — auto-triggered when context.local.md is missing |
| [review-change-set.md](../commands/review-change-set.md) | Verify a change set is consistent and ready to record |
| [describe-change-set.md](../commands/describe-change-set.md) | Generate a change set summary for recording |
| [update-work-context.md](../commands/update-work-context.md) | Update work tracking and backlog |
| [list-commands.md](../commands/list-commands.md) | List all available commands |

Commands provide patterns, not prescriptions. Adapt them to your project's workflow.

---

## Example: review-change-set.md

[commands/review-change-set.md](../commands/review-change-set.md) shows the structure. It defines purpose, approach, required context, and a checklist — all workflow-agnostic so it applies regardless of language or toolchain.

---

## Adding a New Command Pattern

1. Create `commands/{command-name}.md` with the standard structure (Purpose, Pattern, Context, Example)
2. Add it to [commands/README.md](../commands/README.md) under the appropriate category

**Prompt to add a command**:
> "Add a command for [operation] to commands/ following the existing structure."

---

*Load command contexts when you want structured guidance for a specific type of operation. Commands work best when combined with the relevant domain and tool contexts.*
