# Git Version Control Context

Context for Git usage. Document team conventions here so AI agents apply them.

## Team Conventions
- **Branching strategy**: *(e.g., trunk-based, feature branches)*
- **Fix classification**: Use `fix` only for defects already present in the project's pre-change committed baseline; corrections to unmerged work are part of that feature or change.
- **Commit message format**: *(e.g., conventional commits, freeform)*
- **Review process**: *(e.g., pull requests, direct commits)*
- **Merge approach**: *(e.g., squash, merge commit, rebase)*

## Configuration
- `.gitignore` patterns in use
- Git hooks configured (if any)
- Repository-specific settings

## Integration Points
- [patterns/setup.md](../patterns/setup.md) — for version-controlled project initialization
- `domains/*.md` — for domain-specific version control patterns

---
*Load when version control context is relevant.*