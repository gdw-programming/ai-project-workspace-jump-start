---
type: ai-toolbox-backlog
title: "Change-Set Commands Statelessness"
status: pending
phase: 2
depends-on: 1, 2, 4, 5
date-added: 2026-09-02
---

# Change-Set Commands Statelessness

## Problem
`Review Change Set` and `Describe Change Set` can be run multiple times in a session. Manual user actions between runs (file edits, staging changes) must always be picked up — the commands must not rely on what was true earlier in the session.

## Change
Update `commands/review-change-set.md` and `commands/describe-change-set.md` to explicitly require re-reading current git/workspace state at command start every time — no session-memory reliance. Call out that manual user edits or staging changes made between agent turns must be reflected immediately. Evaluate every existing command for whether it needs the same stateless behavior, and assess that need whenever a new command is created.

## Files to touch
- `.ai-toolbox/commands/review-change-set.md`
- `.ai-toolbox/commands/describe-change-set.md`
- `.ai-toolbox/docs/Commands.md` (command authoring guidance)

## Notes
Ties to the existing Workspace State Awareness rule in `context.global.md` — reference it rather than duplicate it. The command authoring guidance must make statelessness evaluation part of both existing-command review and new-command creation; implement that guidance in `docs/Commands.md` as part of this item.
