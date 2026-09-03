---
type: ai-toolbox-backlog
title: "Portable Command Discovery and Invocation"
status: pending
phase: 2
depends-on: 4, 5
date-added: 2026-09-03
---

# Portable Command Discovery and Invocation

## Problem
Users should be able to invoke a documented command with its name, such as `Review Change Set`, without explaining where the command lives or how the agent should find it. The current system does not define deterministic command recognition, so an agent may search broadly, request extra routing instructions, or substitute an invented workflow.

## Change
- Establish `commands/README.md` as the canonical command registry with each command's display name, aliases, and file path.
- Add a global invocation rule: when a user request matches a command name or alias, load the matching command definition and follow it before treating the request as a general task.
- Define exact-name matching before fuzzy interpretation.
- Define concise disambiguation when multiple commands match.
- Require the registry to be updated whenever a command is added, renamed, or removed.
- Keep discovery and invocation repository-based and portable; do not depend on agent-specific skills or hidden configuration.

## Files to touch
- `.ai-toolbox/context.global.md` (command invocation rule)
- `.ai-toolbox/commands/README.md` (canonical registry and aliases)
- `.ai-toolbox/docs/Commands.md` (user-facing command discovery and authoring guidance)
- `.ai-toolbox/commands/*.md` (add display names or aliases where required)

## Notes
This item complements the Steering context: Steering routes unclear topics to context areas, while this item resolves explicit operational command requests. Preserve the existing command definitions as the source of procedure; the registry only makes them discoverable.