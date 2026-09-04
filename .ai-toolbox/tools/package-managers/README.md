# Package-Manager Security Tooling

## Workflow

1. Detect the package manager from the current project state, using package-manager metadata and lockfiles as evidence.
2. If multiple package managers are present, or no supported manager is identifiable, ask the project user which manager governs the project before acting.
3. Load the matching implementation in this directory and run its audit command.
4. Apply only non-breaking security fixes. Do not apply an option that intentionally introduces breaking dependency changes.
5. Review the audit result and record which advisories were resolved, which require breaking changes, and which remain unfixable.
6. Load the project's standards and quality-gate context before validating. Do not invent audit acceptance rules or build, package, lint, or test commands when project policy does not define them.
7. Run the project's required validation commands. Diagnose dependency or runtime API failures before investigating application code.
8. Hand off a passing change for the project's change-set review and description workflows.

## Outcome

- Use `version:patch` when one or more security vulnerabilities are resolved.
- Use `none` when the lockfile is unchanged because no fixable advisories exist.

Implementations are added as `tools/package-managers/{manager}.md`. This file defines the shared pattern; manager-specific files define commands and output interpretation.