# Context Management Commands

Operations for managing the hierarchical context system.

## Load Context Chain
**Purpose**: Load contexts following hierarchy for specific task
**Pattern**: Start with global routing, add contexts as needed
**Context**: Always start with context.global.md
**Example**: 
```
Load: context.global.md → context.local.md → domains/research.md
```

## Update Work Context
**Purpose**: Update current work tracking and backlog
**Pattern**: Add, update, or complete items in context.backlog.md
**Context**: context.backlog.md + context.state.md
**Example**: Add backlog items, mark completions, adjust priorities

## Validate Context Chain
**Purpose**: Check context references and consistency
**Pattern**: Follow reference chains, verify files exist
**Context**: context.global.md + all referenced contexts
**Example**: Ensure no broken references, no duplicate info

## Add Domain Context
**Purpose**: Create new domain-specific context
**Pattern**: Create in domains/ with standard structure
**Context**: domains/README.md for patterns
**Example**: New domain for specific project type

---
*Focus on maintaining clean context hierarchy*