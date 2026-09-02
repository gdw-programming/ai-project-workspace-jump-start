---
type: ai-toolbox-backlog
title: "Package-Manager Security Tooling"
status: pending
phase: 3
depends-on: 1, 2, 4, 5
date-added: 2026-09-02
---

# Package-Manager Security Tooling

## Problem
Security vulnerabilities reported by `npm audit` are addressable independently of any package update cycle, but a prior downstream project had no single repeatable procedure for it — the only reference was an inline step inside an unrelated bulk-dependency-update command. That downstream workflow is npm-specific; the base template must stay package-manager agnostic (System Content Eligibility Rules), so the npm-specific version cannot be added as-is to `commands/`.

## Decision
Generalize a parent pattern, then write an npm-specific implementation under a new `tools/package-managers/` folder.

## Change
- Add `tools/package-managers/README.md`: the generalized pattern — run an audit, apply only non-breaking fixes, validate (build/lint/test), label the PR based on outcome — independent of any specific package manager.
- Add `tools/package-managers/npm.md`: the npm-specific implementation:
  1. Run `npm audit` — review the output; note which advisories have `fixAvailable: true` (non-breaking), which require `--force` (breaking), and which are unfixable (`fixAvailable: false`)
  2. Create branch: `git checkout -b chore/security-audit-fix`
  3. Run `npm audit fix` (no `--force`) — resolves only non-breaking advisories; does not touch breaking-change-required or unfixable vulnerabilities
  4. Review output — confirm which advisories were resolved; unfixable transitive vulnerabilities are acceptable per project audit-gate policy; do not proceed with `--force` for remaining items
  5. Validate: run the project's build, package, lint, and test commands
  6. If validation passes, hand off to the user — Review Change Set and Describe Change Set are the user's responsibility
  7. If validation fails: diagnose the failure before investigating application code — `npm audit fix` should not affect runtime behavior; a failure likely indicates a transitive dependency changed a runtime API
  - PR label: `version:patch` if one or more security vulnerabilities were resolved; `none` if the lockfile was unchanged (no fixable advisories existed)
- Add a generic `commands/fix-security-advisories.md`: detects the project's package manager and follows the matching file under `tools/package-managers/` (starting with npm; other package managers added the same way later).

## Files to touch
- `.ai-toolbox/tools/package-managers/README.md` (new)
- `.ai-toolbox/tools/package-managers/npm.md` (new)
- `.ai-toolbox/commands/fix-security-advisories.md` (new)
