# npm Security Advisories

**Pattern**: Follow [README.md](README.md), using npm commands and audit output.

## Procedure

1. Run `npm audit` and review the output. Note advisories with `fixAvailable: true`, advisories whose fix requires `--force` and a breaking change, and advisories with `fixAvailable: false`.
2. Create the branch `chore/security-audit-fix` according to the project's Git workflow.
3. Run `npm audit fix` without `--force`. This applies non-breaking fixes only.
4. Review the result and confirm which advisories were resolved. Do not run `npm audit fix --force` for remaining breaking-change or unfixable advisories. Unfixable transitive vulnerabilities require the project's documented audit-gate policy; stop and ask when that policy is absent.
5. Run the project's build, package, lint, and test commands in the order and form defined by its project standards. Stop and ask when required validation commands are not defined.
6. If validation passes, hand off to the user for Review Change Set and Describe Change Set.
7. If validation fails, diagnose the dependency change and any runtime API incompatibility before investigating application code. The audit fix should not intentionally change runtime behavior, but a transitive dependency update can expose an API change.

## Outcome

- Use `version:patch` when one or more vulnerabilities were resolved.
- Use `none` when the lockfile is unchanged because no fixable advisories existed.