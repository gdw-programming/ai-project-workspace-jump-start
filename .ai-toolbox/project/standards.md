# Project Standards

Essential quality guidelines across project types.

## Universal Principles
1. **Clarity**: Code and documentation self-explanatory
2. **Consistency**: Follow established domain patterns
3. **Simplicity**: Prefer straightforward solutions
4. **Maintainability**: Consider future modifications

## File Organization
- Use descriptive names for files and directories
- Group related files logically
- Separate concerns (source, tests, docs, config)
- Follow domain conventions

## Documentation Requirements
- **README.md**: Purpose, usage, setup instructions
- **Code Comments**: Explain why, not what
- **Decision Records**: Document choices and rationale

## Version Control
- Use Git with descriptive commit messages
- Include appropriate .gitignore
- Never commit secrets or credentials
- Tag releases appropriately

## Quality Gates
- Establish validation appropriate for project type
- Use automated formatting where available
- Include basic testing where applicable
- All non-skipped tests must pass — or be documented as environment-gated with clear reason
- Review before committing

## Context Integration
- Load domain standards from `domains/{type}.md`
- Reference `patterns/` for implementation approaches
- Use `tools/` contexts for tool-specific configurations

---
*Adapt standards based on loaded domain contexts.*