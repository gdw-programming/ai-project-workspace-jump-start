# Command Context Directory

One command per file. Command definitions are authoritative for display names and aliases; this index is for discovery.

## System
- **[Project Initialization Command](initialization.md)** — alias: `initialization` — Full project setup workflow (auto-triggered when context.local.md is missing)

## Context Management
- **[List Commands](list-commands.md)** — alias: `list-commands` — List all available commands
- **[Load Context Chain](load-context-chain.md)** — alias: `load-context-chain` — Load contexts following hierarchy for specific task
- **[Validate Context Chain](validate-context-chain.md)** — alias: `validate-context-chain` — Check context references and consistency
- **[Compact Context](compact-context.md)** — alias: `compact-context` — Reduce natural-language context while preserving meaning and capability
- **[Update Work Context](update-work-context.md)** — alias: `update-work-context` — Update work tracking and backlog
- **[Add Domain Context](add-domain-context.md)** — alias: `add-domain-context` — Create new domain-specific context

## Development Workflow
- **[Initialize Project](initialize-project.md)** — alias: `initialize-project` — Set up basic project structure
- **[Organize Structure](organize-structure.md)** — alias: `organize-structure` — Create logical directory organization
- **[Setup Quality Gates](setup-quality-gates.md)** — alias: `setup-quality-gates` — Establish basic quality controls
- **[Fix Security Advisories](fix-security-advisories.md)** — alias: `fix-security-advisories` — Apply non-breaking security fixes through package manager
- **[Document Project](document-project.md)** — alias: `document-project` — Create appropriate documentation
- **[Review Change Set](review-change-set.md)** — alias: `review-change-set` — Verify change set is consistent and ready to record
- **[Describe Change Set](describe-change-set.md)** — alias: `describe-change-set` — Generate change set summary for recording

## Project Management
- **[Define Project Scope](define-project-scope.md)** — alias: `define-project-scope` — Establish project boundaries and goals
- **[Track Progress](track-progress.md)** — alias: `track-progress` — Monitor project status and milestones
- **[Maintain Standards](maintain-standards.md)** — alias: `maintain-standards` — Ensure consistent quality
- **[Plan Next Phase](plan-next-phase.md)** — alias: `plan-next-phase` — Identify and prepare for upcoming work

## Usage Pattern
Load commands as part of context hierarchy:
```
context.global.md → commands/{command-name}.md
```

Match user request against display name or alias before treating as general task. If no exact match, offer near-match suggestions from this index. Ask user to choose if multiple candidates remain. Sync index when commands are added, renamed, or removed.

## Command Style
Commands document:
- **Purpose**: What it accomplishes
- **Pattern**: General approach
- **Context**: Required context loading
- **Example**: Basic usage

---
*See [docs/Commands.md](../docs/Commands.md) for usage guidance.*