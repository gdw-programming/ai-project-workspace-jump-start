# Project Information Directory

Essential project information stable across domains.

## Core Files
- **overview.md** - Project mission and goals
- **standards.md** - Universal quality guidelines

## Usage in Context Hierarchy
Load project contexts when:
- Establishing quality standards
- Defining project purpose, goals, constraints
- Making organizational decisions

## Context Loading Pattern
```
context.global.md → project/overview.md → project/standards.md
```

Combine with domain contexts:
```
project/standards.md + domains/{type}.md → complete standards
```

---
*See [docs/Project Context.md](../docs/Project%20Context.md) for usage guidance.*