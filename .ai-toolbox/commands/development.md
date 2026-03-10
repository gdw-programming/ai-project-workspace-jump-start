# Development Workflow Commands

General development patterns that work across project types.

## Initialize Project
**Purpose**: Set up basic project structure
**Pattern**: Follow patterns/setup.md workflow
**Context**: patterns/setup.md + domains/{type}.md + tools/ contexts as needed
**Example**: Create directory structure, initialize version control, add documentation

## Setup Quality Gates
**Purpose**: Establish basic quality controls
**Pattern**: Add appropriate linting, formatting, testing for project type
**Context**: domains/{type}.md + tools/ contexts as needed
**Example**: ESLint for JS, Pylint for Python, etc.

## Document Project
**Purpose**: Create appropriate documentation
**Pattern**: README + domain-specific docs
**Context**: patterns/setup.md + project/standards.md
**Example**: Purpose, installation, usage, contribution guidelines

## Organize Structure
**Purpose**: Create logical directory organization
**Pattern**: Standard patterns for project type
**Context**: domains/{type}.md + patterns/setup.md
**Example**: src/, docs/, tests/ with appropriate subdirectories

---
*Adapt patterns based on loaded domain contexts*