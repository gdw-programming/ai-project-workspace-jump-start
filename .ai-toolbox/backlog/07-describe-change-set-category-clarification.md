---
type: ai-toolbox-backlog
title: "Describe Change Set — Updated vs Fixed Category Clarification"
status: pending
phase: 2
depends-on: 1, 2, 4, 5
date-added: 2026-09-02
---

# Describe Change Set — Updated vs Fixed Category Clarification

## Problem
The current `Fixed` category definition ("existing files where content was incorrect or broken — not routine sync lag") is ambiguous in practice. During feature development, files are routinely updated to stay synchronized with the feature being built — renamed functions, stale comments, updated references, label changes. These are consequences of the feature, not pre-existing failures. Miscategorizing them as `Fixed` misrepresents the change set.

## Change
Update the `Describe Change Set` categories in `commands/describe-change-set.md` to make this distinction explicit:
- **Updated** — includes all files that changed as part of building the feature, including synchronization work driven by the feature: renamed functions updated wherever referenced, comments corrected because the code they described changed, stale API references updated to reflect the new API. These are part of the feature work.
- **Fixed** — applies only to bugs or failures in previously committed code, independent of the current feature. A fix corrects something that was wrong before the current work started and would remain wrong if the feature were reverted. If the file would not have needed changing without the current feature, it is Updated, not Fixed.

The current wording "not routine sync lag" attempts to draw this line but is too vague — the "would this file need changing without this feature?" test is clearer.

## Files to touch
- `.ai-toolbox/commands/describe-change-set.md` (Categories section)
