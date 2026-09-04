# Fix Security Advisories

**Aliases**: `fix-security-advisories`
**Purpose**: Apply non-breaking security fixes through project package manager.
**Pattern**: Re-read workspace state, detect package manager, load `tools/package-managers/README.md` and matching implementation, apply non-breaking fixes, validate against project policy, hand off result for change-set review.
**Context**: `context.global.md` + `context.local.md` + `project/standards.md` + `tools/package-managers/README.md` + `tools/package-managers/{manager}.md`
**Example**: For npm project, load `tools/package-managers/npm.md` and run audit-fix without `--force`.

Stateless: re-read package metadata, lockfiles, workspace changes, branch state, and available tools at start of invocation. If manager is unsupported, multiple managers exist, none detectable, or validation policy missing, ask user for clarification. Do not infer manager priority or policy from session history.

First supported implementation is npm. Add future implementations as `tools/package-managers/{manager}.md` and register when available.