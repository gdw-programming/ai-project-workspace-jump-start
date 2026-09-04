# Fix Security Advisories

**Aliases**: `fix-security-advisories`
**Purpose**: Apply non-breaking security fixes through the project's package manager
**Pattern**: Re-read current workspace state, detect the package manager, load `tools/package-managers/README.md` and the matching implementation, apply only non-breaking fixes, validate against project policy, and hand off the result for change-set review
**Context**: context.global.md + context.local.md + project/standards.md + tools/package-managers/README.md + tools/package-managers/{manager}.md
**Example**: With an npm project, load `tools/package-managers/npm.md` and run its audit-fix procedure without `--force`.

This command is stateless: re-read the current package metadata, lockfiles, workspace changes, branch state, and available tools at the start of every invocation. If the manager is unsupported, multiple managers are present, no manager is detectable, or required project audit and validation policy is missing, stop and ask the project user for clarification. Do not infer a manager priority or validation policy from session history.

The first supported implementation is npm. Add future implementations as `tools/package-managers/{manager}.md` and register them only when available.