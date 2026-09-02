---
type: ai-toolbox-backlog
title: "Token-Conservation Rule (Caveman-derived)"
status: pending
phase: 1
depends-on: ~
date-added: 2026-09-02
---

# Token-Conservation Rule

## Problem
Context files accumulate verbose phrasing over time, which costs tokens on every load. There's no standing rule requiring terse, non-redundant content.

## Source
Reviewed [Caveman](https://github.com/JuliusBrussee/caveman): cuts filler/prose from agent output while never touching code, commands, file paths, or exact error messages. Applies the same idea to written context content, not just conversational replies.

## Change
Add a Documentation Standard in `context.global.md` requiring terse, non-redundant phrasing across all `.ai-toolbox` content: cut filler/throat-clearing prose, but preserve exact code, paths, rule names, and commands verbatim. This rule governs all content authored from this point forward, including items developed later in this backlog.

## Files to touch
- `.ai-toolbox/context.global.md` (Documentation Standards section)

## Notes
This rule feeds Phase 4 (Toolbox-wide Optimization Sweep) — once added, sweep existing files to apply it retroactively.
