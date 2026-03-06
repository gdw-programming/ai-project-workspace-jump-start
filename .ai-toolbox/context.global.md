# Context Global Routing

**AI Agent Entry Point**: Start here for all context loading. `context.local.md` automatically merged.

**Initialization Required**: If `context.local.md` doesn't exist, this is a new project - follow initialization workflow in `./commands/initialization.md`.

## Definitions
- **Project**: The current project using this context management system
- **Context System**: The hierarchical context management structure within the project
- **Root README**: `../README.md` (project-level documentation)
- **System README**: `./README.md` (context system documentation)

## Hierarchy Levels
1. **Core**: context.global.md + context.local.md (auto-merged, generated if missing)
2. **Operational**: context.state.md + available commands/
3. **Domain**: [domains/, patterns/, tools/ - under development]
4. **Project**: [project/ - under development]

## Standard Loading Paths
*Organized by logical importance and application order*

**Core Context**: context.global.md + context.local.md (auto-merged)
**Project Status**: context.global.md → context.state.md
**Initialization**: context.global.md → commands/initialization.md

### Hierarchical Loading
1. **Core**: context.global.md + context.local.md (auto-merged)
2. **Operational**: context.state.md + available commands/
3. **Domain**: domains/, patterns/, tools/ (under development)
4. **Project**: project/ modules (under development)

*Additional loading paths available as context modules are completed*

## Available Contexts

### Level 2 (Operational)
- `context.state.md` - current project status

### Level 3-4 (Domain & Project)
*The following context modules are under development:*
- `domains/` - domain-specific contexts
- `patterns/` - reusable patterns
- `tools/` - tool-specific contexts 
- `project/` - project essentials

*Additional operational commands available in commands/ directory*

## Maintenance Rules
*Organized by logical importance and application order*

### Critical System Rules (Always Applied First)
- **Context Organization**: Keep all context files organized by logical importance and application order - most critical rules first, supporting details last
- **AI Agent Discipline**: Always follow maintenance rules - automatic rule application required, not optional
- **Workflow Agnostic**: No references to specific user workflows (git staging, commit patterns, etc.) in context files or documentation - let users choose their own workflow preferences
- **Initialization Check**: If context.local.md missing, initiate project setup workflow before proceeding
- **DRY Enforcement**: Detect and eliminate information duplication across all context files
- **Reference Validation**: Verify all context references before changes
- **Cross-Reference Validation**: Ensure all file paths and references work

### Content Management Rules
- **File Reference Standards**: Note to user when referencing uncommitted files to help prevent broken links
- **Path Validation**: Ensure all context file paths work for end users
- **Documentation Sync**: Auto-sync between ../README.md and ./README.md when changing linked contexts or project status
- **State Consistency**: Sync status across README.md, context.state.md, and other contexts
- **Current State Only**: context.state.md contains no historical references  
- **Agent Agnostic**: No agent/user references in context files except context.local.md personalization file
- **Passive Updates**: All context file and documentation updates automatically synchronized by processing agents

### Documentation Standards
- **Documentation Separation**: Root README = project content, .ai-toolbox/README.md = context system documentation
- **Auto-Sync Documentation**: Update ../README.md project status section from context.state.md
- **Project State Language**: Use "ready to initialize project" or current project state, not development language
- **Technical Terms Exception**: Allow specific technical terms like GitHub's "Use this template" button, API names, and platform-specific features that have established meanings

### Operational Behavior
- **Local Context Maintenance**: Auto-update environment basics and workspace structure in context.local.md
- **Gitignored File Editing**: Allow editing of gitignored files when they are part of system functionality (e.g., context.local.md, user preferences)
- **Minimal Context**: Create only necessary contexts for project use, avoid unnecessary complexity
- **Minimal Loading**: Load only required contexts
- **Gitignore Awareness**: Respect .gitignore patterns for file usage in project structure, but reference or use ignored files when contextually relevant

## Version Control Integration
- **User Exclusions**: context.local.md, .sandbox/, temp/ excluded via .gitignore
- **Project Files**: All project infrastructure committed and versioned
- **Reference Usage**: Can examine ignored files (node_modules, build outputs) for context without including in commits

---
*Keep this file compact and machine-readable. See `./README.md` for human documentation.*