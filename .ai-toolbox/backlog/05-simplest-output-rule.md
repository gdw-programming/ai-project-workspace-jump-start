---
type: ai-toolbox-backlog
title: "Simplest-Output Rule (Ponytail-derived)"
status: pending
phase: 1
depends-on: ~
date-added: 2026-09-02
---

# Simplest-Output Rule

## Problem
No standing rule pushes toward the simplest solution before adding new rules, files, or commands to the toolbox — or before an agent proposes a solution to a user's request.

## Source
Reviewed [Ponytail](https://github.com/DietrichGebert/ponytail): before writing code, stop at the first rung that holds — does it need to exist? already in the codebase? stdlib? native platform feature? installed dependency? one line? only then the minimum that works.

## Change
Add `.ai-toolbox/patterns/simplest-output.md`: a generalized decision ladder adapted for context/documentation authoring and for answering user requests generally —
1. Does this need to exist at all?
2. Is it already covered by an existing rule/file?
3. Does an existing convention or tool already solve it?
4. Only then add the minimum new rule/file/command.

Reference this pattern from `context.global.md`'s Context Placement rule and Operational Behavior section.

## Files to touch
- `.ai-toolbox/patterns/simplest-output.md` (new)
- `.ai-toolbox/context.global.md` (Context Placement, Operational Behavior)
- `.ai-toolbox/README.md` (Sources and Credits section)

## Notes
This is a decision-making rule, not a one-time edit — it should be applied by every future backlog item, and folded into the Phase 4 sweep for existing content. After implementation, update the Sources and Credits section in `.ai-toolbox/README.md` with the documented source and adaptation.
