# AI Project Workspace - System Development Context

**SYSTEM DEVELOPMENT ROOT CONTEXT**: Entry point for AI agents when improving this workspace system. Removed during project initialization.

## System Development Mode
- **Purpose**: Working ON this workspace system, not USING it for a project
- **State**: Workspace system development
- **Context Hierarchy**: context.development.md → context.global.md → operational contexts
- **Scope**: System architecture, documentation, and context improvements
- **Context Placement**: System-development-only rules belong in this file. File is deleted at initialization. Durable rules for project users belong in `context.global.md`.
- **User-Mode File Protection**: `tools/`, `domains/`, `project/`, `STATUS.md`, `BACKLOG.md`, `CHANGELOG.md` are for project users — do not add system dev progress notes or tracking. Use Upcoming Work section.
- **Upstream-Note Override**: Upstream-note capture applies to downstream projects sending findings to this system. Not required when this repository is upstream workspace source.

## Context
Two distinct contexts:
1. **System Development Context**: Entry point override in front of `context.global.md`. Developing workspace system for users.
2. **User Project Context**: User uses `context.global.md` as primary entry point. Initialization command deletes this file.

## System Development Language Rules

### User-Facing Language Standards
- **System References**: Use "workspace system" or "this system" instead of "template"
- **User Perspective**: Write documentation as if user already has operational system
- **Ready State Language**: "ready to initialize project", "operational", "available"
- **Avoid Development Language**: No "building", "creating", or "developing" references in user documentation
- **Clean Separation**: System infrastructure vs user project content clearly distinguished

### Documentation in Development Mode
- **User Documentation Standards**: Write documentation for system users (not system developers)
- **Getting Started Focus**: User onboarding to use system
- **Local Context Guidance**: Help users customize minimal personal preferences in context.local.md
- **Implementation Guides**: Explain system usage patterns, not architecture
- **Minimal Context Enforcement**: Ensure context.local.md remains minimal
- **docs/ Scope**: `.ai-toolbox/docs/` describes current system features, setup, architecture, usage; no past-iteration references
- **AI Toolbox Docs Format**: Each guide in `.ai-toolbox/docs/` follows: common prompts first, what-belongs table, worked example with link, how-to for adding new items
- **Contributor Scope**: `CONTRIBUTING.md` covers contributing to system (fork → change → PR)

## System Content Eligibility Rules
Items added to workspace system must satisfy at least one criterion:
1. **Generic Functionality**: Provides value to future projects regardless of domain or stack
2. **How-To Documentation**: Teaches users how to add, extend, or build features in system

Items supporting only system development process do not qualify.

## Upcoming Work
*Forward-looking only. Remove items when complete — do not mark or annotate.*

*(no active work scheduled)*

### Optional Enhancements
*(no optional enhancements pending)*

## System Development Loading Paths
When working on system features:
→ context.development.md (entry) → context.global.md → domains/ and tools/ as needed

## System Development Lifecycle Management
Deleted during project initialization to ensure clean user experience with context.global.md as primary entry point.

---

### Continue Context Loading
**Next**: Load context.global.md for project-focused routing and operational contexts