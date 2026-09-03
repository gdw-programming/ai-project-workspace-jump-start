# Command Context Directory

One command per file. Load by name when needed.

## System
- **[initialization.md](initialization.md)** — Full project setup workflow (auto-triggered when context.local.md is missing)

## Context Management
- **[list-commands.md](list-commands.md)** — List all available commands
- **[load-context-chain.md](load-context-chain.md)** — Load contexts following hierarchy for specific task
- **[validate-context-chain.md](validate-context-chain.md)** — Check context references and consistency
- **[compact-context.md](compact-context.md)** — Reduce natural-language context while preserving meaning and capability
- **[update-work-context.md](update-work-context.md)** — Update work tracking and backlog
- **[add-domain-context.md](add-domain-context.md)** — Create new domain-specific context

## Development Workflow
- **[initialize-project.md](initialize-project.md)** — Set up basic project structure
- **[organize-structure.md](organize-structure.md)** — Create logical directory organization
- **[setup-quality-gates.md](setup-quality-gates.md)** — Establish basic quality controls
- **[document-project.md](document-project.md)** — Create appropriate documentation
- **[review-change-set.md](review-change-set.md)** — Verify a change set is consistent and ready to record
- **[describe-change-set.md](describe-change-set.md)** — Generate a change set summary for recording

## Project Management
- **[define-project-scope.md](define-project-scope.md)** — Establish project boundaries and goals
- **[track-progress.md](track-progress.md)** — Monitor project status and milestones
- **[maintain-standards.md](maintain-standards.md)** — Ensure consistent quality
- **[plan-next-phase.md](plan-next-phase.md)** — Identify and prepare for upcoming work

## Usage Pattern
Load commands as part of context hierarchy:
```
context.global.md → commands/{command-name}.md
```

## Command Style
Commands are documented as:
- **Purpose**: What it accomplishes
- **Pattern**: General approach
- **Context**: Required context loading
- **Example**: Basic usage

Focus on patterns rather than specific implementations.

---
*See [docs/Commands.md](../docs/Commands.md) for prompt examples and usage guidance.*