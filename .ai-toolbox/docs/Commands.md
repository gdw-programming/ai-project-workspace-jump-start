# Commands — Usage Guide

The `commands/` directory provides operation patterns for common tasks. Command contexts tell AI agents how to approach specific types of work — purpose, a general approach, required context, and an example.

## Common Prompts

### Load a command context
> "Load the review-change-set command for this session."

> "I need to organize my project structure — load the relevant command context."

### Invoke a named command
> "Review Change Set"

> "Run the `review-change-set` command."

Command names and aliases are matched exactly after normalizing case and surrounding whitespace. The agent loads the matching command definition and follows every step in it. A related command is never substituted.

When no exact match exists, the agent does not execute a command. It may offer a short list of near matches based on meaningful shared words from registered names and aliases. Select a suggestion by naming the exact command or alias. When multiple candidates remain, choose one explicitly. Use `list-commands` to view the complete registry.

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

1. Create `commands/{command-name}.md` with the standard structure (Purpose, Pattern, Context, Example), using its H1 as the display name and adding an `Aliases` field.
2. Add the display name, aliases, and file path to [commands/README.md](../commands/README.md) under the appropriate category.
3. Before finalizing the command, assess whether it depends on live workspace state, git state, staged files, branch status, tool availability, or user edits that may change between turns. If so, the command must explicitly instruct the agent to re-read current state at command start every run instead of relying on earlier session memory or prior outputs.
4. Review existing commands for the same statelessness requirement before accepting a new command as complete; if a command can be run multiple times in one session, it must be safe against stale state and must say so in its definition.

**Statelessness rule for command authoring**:
- Every existing command must be reviewed for whether it is stateful or stateless.
- If a command reads or interprets anything that can change between turns — workspace files, staging, branch state, tool availability, repo status, diff output, or user edits — it must re-read current state at the start of every invocation.
- New commands must be assessed the same way before they are added to the command set; if they depend on current state, the command definition must state that requirement explicitly and reference the Workspace State Awareness rule in [context.global.md](../context.global.md) instead of implying session continuity.

**Prompt to add a command**:
> "Add a command for [operation] to commands/ following the existing structure."

---

*Load command contexts when you want structured guidance for a specific type of operation. Commands work best when combined with the relevant domain and tool contexts.*
