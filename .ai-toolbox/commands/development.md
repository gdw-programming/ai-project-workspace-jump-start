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

## Describe Change Set
**Purpose**: Generate a descriptive summary of the current change set suitable for recording (commit message, PR description, changelog entry, etc.)
**Pattern**: Identify each version-controlled file in the change set (exclude gitignored and intentionally untracked files), determine its category based on prior history, and produce a concise plain text summary (no markdown formatting) with a one-line title and categorized file list
**Context**: context.global.md + all version-controlled files in the current change set + their prior recorded history
**Categories**:
- **Created** — new files with no prior recorded history
- **Integrated into** — existing files modified only to wire in new files from this change set
- **Updated** — existing files with substantive content changes
- **Fixed** — existing files where something incorrect was corrected

Omit any category that has no files.

## Review Change Set
**Purpose**: Verify a change set is consistent, correct, and ready to record
**Pattern**: Review all version-controlled files in the current change set (exclude gitignored and intentionally untracked files) against established context rules, fix all issues found, re-read changed files to verify no fix introduced a new inconsistency, then report
**Context**: context.global.md + context.state.md + all version-controlled files in the current change set
**Checklist**:
- Logical consistency, clarity, and alignment with project workflow goals; no rule or constraint conflicts with an existing rule in another context file
- Compliance with all context and documentation rules (DRY, Minimal Context, Workflow Agnostic, Reference Validation, Language Standards, Markdown Links, Context Framing)
- All file references and links are correct and point to existing files
- Workspace trees and module listings in context.state.md and README files reflect all files in this change set — treat them as current
- Auto-sync targets (root README.md, context.state.md, context.backlog.md) are consistent with current content — if out of sync, fix immediately as a dependency

---
*Adapt patterns based on loaded domain contexts*