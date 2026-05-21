# Load Context Chain

**Purpose**: Load contexts following hierarchy for specific task
**Pattern**: Start with global routing, add contexts as needed
**Context**: Always start with context.global.md
**Example**:
```
Load: context.global.md → context.local.md → domains/research.md
```
