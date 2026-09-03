---
type: ai-toolbox-backlog
title: "Brain-First Planning and Research"
status: pending
phase: 2
depends-on: 12
date-added: 2026-09-03
---

# Brain-First Planning and Research

## Problem
The system stores project intent, decisions, constraints, standards, status, backlog, and history, but it does not require planning and research workflows to consult that knowledge before asking for context or looking outside the repository. Agents may therefore repeat research, overlook existing decisions, or ask users for information already captured in the project brain.

## Change
- Add a global rule requiring agents to consult relevant repository context before asking clarification questions or conducting external research.
- Define the default planning and research order: `context.global.md` → `context.steering.md` → relevant `project/`, `domains/`, `patterns/`, `tools/`, commands, status, backlog, and history.
- Treat existing project decisions, constraints, standards, and recorded knowledge as authoritative unless the user explicitly changes them.
- Make external research a fallback when the project brain does not contain enough information.
- Require new decisions, validated discoveries, and reusable project knowledge to be captured in the appropriate brain location.
- Update planning and research command guidance to follow this order.

## Files to touch
- `.ai-toolbox/context.global.md` (brain-first planning and research rule)
- `.ai-toolbox/context.steering.md` (planning and research routing entries, if needed)
- `.ai-toolbox/commands/plan-next-phase.md` (brain-first planning workflow)
- `.ai-toolbox/domains/research.md` (brain-first research workflow)

## Notes
This item defines consultation order and knowledge capture. It complements Steering, which identifies likely context locations, and Portable Command Discovery, which resolves explicit command requests.