# AI Project Workspace - System Development Context

**SYSTEM DEVELOPMENT ROOT CONTEXT**: Primary entry point for AI agents when improving this AI project workspace system. This file will be removed during project initialization.

## System Development Mode
- **Purpose**: Working ON this project workspace system, not USING it for a specific project
- **State**: Project workspace system development (not project usage)
- **Context Hierarchy**: This file → context.global.md → operational contexts
- **Scope**: System architecture, documentation, and context improvements
- **Context Placement**: Anything that applies only while working ON the workspace system — and is not relevant to project users — belongs in this file. This file is deleted at initialization, so anything here must be safe to lose from the project user's perspective. If a rule or principle is useful to project users, it belongs in `context.global.md` or another surviving context file instead.
- **User-Mode File Protection**: `tools/`, `domains/`, `project/`, `STATUS.md`, `BACKLOG.md`, and `CHANGELOG.md` are written for project users — do not add system development state, progress notes, or temporary tracking to these files. Any system-dev-only content in these files becomes a trace visible to project users. Use this file's Upcoming Work section for all system development tracking.

## Context (documentation for user's and AI's benefit)
*The context struggle is real*

There are two distinct contexts at play here:
1. **System Development Context**: This file's context development override in front of the context.global.md.
- We are developing a boilerplate system for a user to use to start and build their own distinct project from.
- This file overrides (yet uses) the boilerplate context to ensure it self-follows the rules.

2. **User Project Context**: User using the system with context.global.md as the primary entry point for their project-focused context and operational contexts.
- The user will initialize their own project using the provided initialization command, which will delete this file.
- The user will then use this base system and enhance it as their project's needs evolve.
- The boilerplate system must feel like it belongs to the user and their project so it should not self-reference as a "template" or "boilerplate" in user-facing documentation or contexts.

## System Development Language Rules
*Critical: Applied to ALL documentation and context files during system development*

### User-Facing Language Standards
- **System References**: Use "workspace system" or "this system" instead of "template"
- **User Perspective**: Write documentation as if user already has operational system
- **Ready State Language**: "ready to initialize project", "operational", "available"
- **Avoid Development Language**: No "building", "creating", or "developing" references in user documentation
- **Clean Separation**: System infrastructure vs user project content clearly distinguished

### Documentation in Development Mode
*Global documentation rules apply. These are development-mode-specific additions.*
*This is the ONLY context file authorized to contain user documentation guidance*
- **User Documentation Standards**: How to write documentation for system users (not system developers)
- **Getting Started Focus**: User onboarding to use the system, not system development
- **Local Context Guidance**: Help users customize their minimal personal preferences in context.local.md
- **Implementation Guides**: Explain system usage patterns, not system architecture
- **Minimal Context Enforcement**: Ensure context.local.md remains minimal with only essential user preferences
- **docs/ Scope**: `.ai-toolbox/docs/` describes the system as it currently stands — its features, setup, architecture, and usage; no past-iteration references
- **AI Toolbox Docs Format**: Each guide in `.ai-toolbox/docs/` follows: common prompts first, what-belongs table, worked example with link to the example file, how-to for adding new items
- **Contributor Scope**: `CONTRIBUTING.md` covers contributing to the system (fork → change → PR) — it does not describe project development workflows


## System Content Eligibility Rules
*Applied when adding or modifying any file in the system during this boilerplate system's development or enhancement*

Any item added to the workspace system must satisfy at least one of these criteria:

1. **Generic Functionality**: Provides value to any future project regardless of domain, language, or workflow — not specific to this system's own development or opinionated by any projected use of this system.
2. **How-To Documentation**: Teaches users how to add, extend, or build features within the system for use in their own current project

Items that exist solely to support this system's own development process do not qualify and must not be committed to the base system.

## Upcoming Work
*Forward-looking only. No history. Remove items when complete — do not mark or annotate them.*
*`STATUS.md`, `BACKLOG.md`, and `CHANGELOG.md` are not used to track system development progress — they represent the initial delivered state that project users inherit and evolve. System development progress lives only in this section.*
*Detailed context for each active item below lives in `backlog/`; remove its file when the item is complete. Move any durable user-facing guidance to the appropriate system documentation before removal.*

**Phase 1 — Foundation** (no dependencies; later phases build on these)
- Source attribution and credits — backlog/11-source-attribution-and-credits.md

**Phase 2 — Command Hygiene** (depends on Phase 1)
- Change-set commands statelessness, including existing-command review and new-command creation assessment — backlog/06-change-set-commands-statelessness.md
- Describe Change Set: Updated vs Fixed clarification — backlog/07-describe-change-set-category-clarification.md
- Branch Protection rule (opt-in) — backlog/08-branch-protection-opt-in.md
- Portable command discovery and invocation — backlog/12-portable-command-discovery-and-invocation.md
- Brain-first planning and research — backlog/13-brain-first-planning-and-research.md

**Phase 3 — New Features** (depends on Phase 1; independent of Phase 2)
- Upstream Notes system — backlog/09-upstream-notes-system.md
- Package-manager security tooling — backlog/10-package-manager-security-tooling.md

**Phase 4 — Toolbox-wide Optimization Sweep** (after Phases 1-3 land)
- Apply the token-conservation and simplest-output rules retroactively across every existing `.ai-toolbox` file, including everything added above, while preserving the information required for the system's purpose and capabilities. Continue applying both rules to every new context addition during project growth — no dedicated backlog file

### Optional Enhancements
*Not scheduled — consider for future branches*

*(no optional enhancements pending)*

## System Development Loading Paths

When working on system features:
→ context.development.md (entry) → context.global.md → domains/ and tools/ as needed

*System development paths are defined here, not in `context.global.md`. Project users never see this file; all their loading paths are in `context.global.md`.*

## System Development Lifecycle Management
**This context file gets deleted during project initialization** - ensures clean user experience with context.global.md as primary entry point.

**Purpose**: Contains ONLY system development processing rules - nothing essential to system operation when deleted.

---

### Continue Context Loading
**Next**: Load context.global.md for project-focused routing and operational contexts