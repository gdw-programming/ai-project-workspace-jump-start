---
type: ai-toolbox-backlog
title: "Branch Protection Rule (Opt-In)"
status: pending
phase: 2
depends-on: 1, 2, 4, 5
date-added: 2026-09-02
---

# Branch Protection Rule (Opt-In)

## Problem
A prior downstream project hardened its own Branch Protection rule after finding the original conditional wording ("When the user requests changes while on main/master branch, create a feature branch before proceeding") too passive — the branch creation step was often missed after plan approval. This base template has no existing Branch Protection rule at all — only a blank "Branching strategy" stub in `tools/git.md`. Adding it as a hard global rule would conflict with the existing Workflow Agnostic rule (no hardcoded git workflow in context files).

## Decision
Not a mandatory `context.global.md` rule. Instead: opt-in, asked during project setup.

## Hardened rule text (use verbatim as the opt-in text if accepted)
> **Branch Protection**: All code changes must land on a feature branch — never directly on main/master. Determine the correct branch during planning: if the work continues an existing feature branch, identify it and confirm; if on main/master at implementation start, the first action before any file edit is to create a new branch per `tools/git.md` conventions. Post-plan, verify the active branch before proceeding. This is especially important for private repositories where branch protection rules may not be configured — this rule is the only safeguard against committing directly to main.

Key properties of this wording: branch determination belongs in the planning phase, not as a post-plan afterthought; "first action before any file edit" gives explicit ordering when on main at implementation start; the private-repo rationale makes the rule self-explaining without extra context.

## Change
- Add an opt-in question to `commands/initialization.md` User Preference Collection (project-wide subsection, alongside project tracking preferences): ask whether the project wants enforced feature-branch-only workflow (never commit directly to main/master).
- If yes: populate `tools/git.md` "Branching strategy" line with the hardened rule text above.
- If no/unspecified: leave the existing stub placeholder untouched.
- No rule is added to `context.global.md`.

## Files to touch
- `.ai-toolbox/commands/initialization.md` (User Preference Collection)
- `.ai-toolbox/tools/git.md` (Branching strategy line, conditionally populated)
