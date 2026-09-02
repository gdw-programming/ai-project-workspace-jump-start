---
type: ai-toolbox-backlog
title: "Steering Context File"
status: pending
phase: 1
depends-on: ~
date-added: 2026-09-02
---

# Steering Context File

## Problem
Finding the right domain/pattern/tool/project context for a given user request currently requires scanning several directories. There is no single index to shorten that path.

## Change
- Create `.ai-toolbox/context.steering.md`: a lightweight, on-demand keyword/topic → target-file index covering `domains/`, `patterns/`, `tools/`, `project/`, `commands/`.
- Decision: loaded on demand only — NOT part of always-loaded Core context (context.global.md + context.local.md).
- Reference it from `context.global.md`'s Context Placement rule and Standard Loading Paths as the fallback lookup when routing is unclear.
- Add a new `docs/Steering.md` human guide explaining the file's purpose and how to extend it.
- Update the `.ai-toolbox/README.md` structure diagram to include the new file.

## Files to touch
- `.ai-toolbox/context.steering.md` (new)
- `.ai-toolbox/docs/Steering.md` (new)
- `.ai-toolbox/context.global.md` (Context Placement rule, Standard Loading Paths)
- `.ai-toolbox/README.md` (structure diagram)

## Notes
Keep the index itself terse (table format) — it's a lookup aid, not documentation prose.
