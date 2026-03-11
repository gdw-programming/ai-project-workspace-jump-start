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
3. **Domain**: domains/ (research.md example provided) + patterns/ (setup.md example provided) + tools/ (git.md example provided)
4. **Project**: project/ (pre-configured stubs — populate with your project details)

## Standard Loading Paths
*Organized by logical importance and application order*

**Core Context**: context.global.md + context.local.md (auto-merged)
**Project Status**: context.global.md → context.state.md
**Initialization**: context.global.md → commands/initialization.md

### Loading Sequence
1. **Core**: context.global.md + context.local.md (auto-merged)
2. **Operational**: context.state.md + available commands/
3. **Domain**: domains/ + patterns/ + tools/
4. **Project**: project/ (overview.md, standards.md — populate with your project details)

*Additional loading paths available as modules are configured*

## Available Contexts

### Level 2 (Operational)
- `context.state.md` - current project status
- `context.backlog.md` - project backlog and recently completed work

### Level 3 (Domain)
- `domains/` - domain-specific contexts (research.md example provided)
- `patterns/` - reusable patterns (setup.md example provided)
- `tools/` - tool-specific contexts (git.md example provided)

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
- **Backlog Auto-Management**: Mirror all completed items to context.state.md; age out Recently Completed entries per criteria defined in context.backlog.md; completed items must exist in both files
- **Contributor Attribution**: Always use the Contributor Name from context.local.md User Preferences when recording completed items in context.backlog.md and context.state.md — if not set, prompt the user for their name before recording
- **File Reference Standards**: Never use Markdown links to files that have not yet been committed — use plain text references only; Markdown links to uncommitted files create broken documentation
- **Path Validation**: Ensure all context file paths work for end users
- **Documentation Sync**: Auto-sync between ../README.md and ./README.md when changing linked contexts or project status
- **Auto-Sync Targets are Dependencies**: root README.md, context.state.md, and context.backlog.md must stay in sync with committed content at all times — if any is out of sync, fix it immediately as a dependency, not a future task
- **State Consistency**: Sync status across README.md, context.state.md, and other contexts
- **Current State Only**: context.state.md reflects present state — no references to superseded decisions or outdated status; Recently Completed Work is an approved duplication (mirrored from context.backlog.md)
- **Agent Agnostic**: No agent/user references in context files except context.local.md personalization file
- **Passive Updates**: All context file and documentation updates automatically synchronized by processing agents

### Documentation Standards
- **Documentation Separation**: Root README = project content, .ai-toolbox/README.md = context system documentation
- **Auto-Sync Documentation**: Update ../README.md project status section from context.state.md
- **Project State Language**: Use "ready to initialize project" or current project state, not development language
- **Technical Terms Exception**: Allow specific technical terms like GitHub's "Use this template" button, API names, and platform-specific features that have established meanings
- **Markdown Links**: All file references in documentation (README files, docs/) must use proper Markdown link syntax with URL-encoded spaces — `[Display Text](path/to/file.md)` — bare path references like `` `./.ai-toolbox/file.md` `` do not create clickable links
- **Context Framing**: tools/, domains/, and patterns/ use team/project framing ("your team's conventions", "your project's standards") — context.local.md is the only file that uses personal framing ("your preferences", "your environment")

### Operational Behavior
- **Local Context Maintenance**: Auto-update environment basics and workspace structure in context.local.md
- **Tool Discovery Tracking**: When a tool, runtime, or capability is discovered or found missing during any session, record it in the appropriate location — machine-specific tools (shell type, OS utilities, local runtimes, PDF readers, available commands) go in context.local.md Available Tools; project-wide tool conventions (build tools, test frameworks, deployment targets) go in tools/ contexts; if a needed tool is unavailable, record the absence and the alternative used
- **Tool Resolution Loop**: Before attempting any task that requires a specific tool or capability — check context.local.md Available Tools first; if the tool is not recorded, prompt the user before assuming it is available or choosing an alternative; once resolved, record the result (available or unavailable + alternative) before proceeding
- **Gitignored File Editing**: Allow editing of gitignored files when they are part of system functionality (e.g., context.local.md, user preferences)
- **Minimal Context**: Create only necessary contexts for project use, avoid unnecessary complexity
- **Local Context Scope**: context.local.md contains only machine-specific and personal preferences — things that vary by individual user or machine; project decisions (backlog criteria, review process, team standards, documentation approach) belong in their authoritative project files, not context.local.md
- **Minimal Loading**: Load only required contexts
- **Gitignore Awareness**: Respect .gitignore patterns for file usage in project structure, but reference or use ignored files when contextually relevant

## Version Control Integration
- **User Exclusions**: context.local.md, .sandbox/, temp/ excluded via .gitignore
- **Project Files**: All project infrastructure committed and versioned
- **Reference Usage**: Can examine ignored files (node_modules, build outputs) for context without including in commits

---
*Keep this file compact and machine-readable. See `./README.md` for human documentation.*