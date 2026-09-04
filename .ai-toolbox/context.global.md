# Context Global Routing

**AI Agent Entry Point**: Start here for all context loading. `context.local.md` automatically merged.

`.ai-toolbox` is the project's portable brain: persistent memory and context across agents, tools, sessions, and contributors. Load relevant context before acting.

**Local Context Required**: `context.local.md` is machine-specific and gitignored. If missing, follow `./commands/initialization.md` to create it. Absence means contributor has not created personal context file, not that project is uninitialized.

## Definitions
- **Project**: Current project using this context system
- **Context System**: Hierarchical context management structure within project
- **Root README**: `../README.md` (project-level documentation)
- **System README**: `./README.md` (context system documentation)

## Hierarchy Levels
1. **Core**: context.global.md + context.local.md (auto-merged, generated if missing)
2. **Operational**: available commands/ + project tracking files (STATUS.md, BACKLOG.md, CHANGELOG.md — pre-configured templates, configured during initialization)
3. **Domain**: domains/ (research.md example provided) + patterns/ (setup.md example provided) + tools/ (git.md example provided)
4. **Project**: project/ (pre-configured stubs — populate with project details)

## Standard Loading Paths

**Core Context**: context.global.md + context.local.md (auto-merged)
**Project Status**: context.global.md → ../STATUS.md
**Initialization**: context.global.md → commands/initialization.md
**Unclear Routing**: context.global.md → context.steering.md (on demand)

### Loading Sequence
1. **Core**: context.global.md + context.local.md (auto-merged)
2. **Operational**: available commands/ + project tracking files (STATUS.md, BACKLOG.md, CHANGELOG.md — load if configured)
3. **Domain**: domains/ + patterns/ + tools/
4. **Project**: project/ (overview.md, standards.md — populate with project details)

## Available Contexts

### Level 2 (Operational)
**Project Tracking Files** — pre-configured templates. Use as-is, adapt, or replace with preferred external tools (GitHub Issues, Jira, Notion). Configure during initialization.
- `../STATUS.md` - project status (phase, capabilities, workspace structure)
- `../BACKLOG.md` - project backlog and recently completed work
- `../CHANGELOG.md` - project history and completed deliverables

### Level 3 (Domain)
- `domains/` - domain-specific contexts (research.md example provided)
- `patterns/` - reusable patterns (setup.md example provided)
- `tools/` - tool-specific contexts (git.md example provided)

*Operational commands available in commands/ directory.*

## Maintenance Rules

### Critical System Rules (Always Applied First)
- **Global Rule Authority**: `context.global.md` is mandatory center for project-wide rules. Treat Maintenance Rules as binding constraints and check before acting. Apply `Rule Compliance Gate` and `Correction Integration` when evaluating constraints.
- **Initialization Check**: If context.local.md missing, initiate project setup workflow before proceeding.
- **AI Agent Discipline**: Always follow maintenance rules — automatic rule application required.
- **AI-Optimized Content**: `.ai-toolbox` content (excluding `docs/`) is structured for AI processing. Human documentation for context system lives in `.ai-toolbox/docs/`. Human project tracking (`STATUS.md`, `BACKLOG.md`, `CHANGELOG.md`) lives at project root.
- **Project Memory Authority**: `.ai-toolbox` is persistent memory for cross-agent/tool collaboration. All project findings, domain knowledge, preferences, and work context belong here — not in external agent memory systems, session notes, or out-of-repo tools.
- **Source Attribution**: Record external sources in [Sources and Credits](./README.md#sources-and-credits) section of system README with link and concise description. Do not create duplicate registries.
- **DRY Enforcement**: Detect and eliminate information duplication across context files.
- **Reference Validation**: Verify all context references before changes.
- **Cross-Reference Validation**: Ensure all file paths and references work.
- **Workflow Agnostic**: No references to specific user workflows (git staging, commit patterns) in context files or documentation.
- **Context Organization**: Keep context files organized by logical importance — most critical rules first, supporting details last.
- **Human Reading Order**: Organize content in logical reader order: prerequisites first, operations in natural sequence, edge cases/exceptions last.

### Content Management Rules
- **Auto-Sync Targets are Dependencies**: root README.md must stay in sync with committed content. Project tracking files (STATUS.md, BACKLOG.md, CHANGELOG.md) apply if configured — if out of sync, fix immediately as a dependency.
- **State Consistency**: Sync status across README.md, STATUS.md, and other contexts.
- **Backlog Auto-Management**: If using built-in BACKLOG.md and CHANGELOG.md: mirror completed items to CHANGELOG.md; age out Recently Completed entries in BACKLOG.md per criteria. Recently Completed tracks deliverables and features only — context system maintenance is not recorded; "completed" means verified working and user-confirmed.
- **Contributor Attribution**: When recording completed items in project tracking files: use Contributor Name from context.local.md User Preferences. If not set, prompt user.
- **Documentation Sync**: Auto-sync between ../README.md and ./README.md when changing linked contexts or project status.
- **File Reference Standards**: Never use Markdown links to uncommitted files — use plain text references.
- **Path Validation**: Ensure all context file paths work for end users.
- **Agent Agnostic**: No agent/user references in context files except context.local.md.
- **Passive Updates**: All context file and documentation updates automatically synchronized by processing agents.

### Documentation Standards
- **Documentation Separation**: Root README = project content, .ai-toolbox/README.md = context system documentation.
- **Context Framing**: tools/, domains/, patterns/ use team/project framing; context.local.md uses personal framing.
- **Markdown Links**: All file references in documentation (README files, docs/) must use proper Markdown link syntax with URL-encoded spaces: `[Display Text](path/to/file.md)`. Bare paths do not create links.
- **Auto-Sync Documentation**: Update ../README.md project status section from STATUS.md.
- **Project State Language**: Use "ready to initialize project" or current project state, not development language.
- **Technical Terms Exception**: Allow specific technical terms (e.g. GitHub "Use this template" button, API names) with established meanings.
- **Documentation Location Map**: Four audiences: (1) **AI agents**: `.ai-toolbox/` (excluding `docs/`) — AI-structured context; (2) **Project tracking**: `STATUS.md`, `BACKLOG.md`, `CHANGELOG.md` at root; (3) **Developers**: `README.md` (entry point), `/docs/` (project docs), `.ai-toolbox/docs/` (AI context system guide); (4) **End-users**: developer's choice.
- **Present-Tense Voice**: All documentation describes current state — no change-referencing language ("fixed", "improved", "added") outside changelogs.
- **Progressive Disclosure**: Structure documents in reader-need order: (1) one-sentence summary, (2) direct steps/command, (3) necessary usage details, (4) reference/background. Restructure instead of adding TL;DR.
- **Token Conservation**: Keep `.ai-toolbox` content terse and non-redundant without removing required information; remove filler while preserving exact code, commands, file paths, rule names, and error messages verbatim.

### Operational Behavior
- **Clarify Before Acting**: Apply `patterns/simplest-output.md`, then verify context before acting. If request is ambiguous, ask targeted questions with specific options. Capture revealed decisions in appropriate context file.
- **Brain-First Planning and Research**: Consult brain in order: `context.global.md` -> `context.steering.md` -> relevant `project/`, `domains/`, `patterns/`, `tools/` contexts -> applicable commands -> status, backlog, history. Treat recorded decisions as authoritative. Use external research only when brain lacks info; capture new knowledge in brain.
- **Rule Compliance Gate**: Verify action matches context rules. If conflicting, explain conflict and ask permission to deviate.
- **Correction Integration**: When user corrects or reminds agent of a rule, immediately update appropriate `.ai-toolbox` context file. User corrections signal incomplete context.
- **Workspace State Awareness**: Check current workspace state directly before acting rather than relying on session memory. Incorporate user-initiated changes immediately.
- **Tool Resolution Loop**: Check context.local.md Available Tools first. If unrecorded, prompt user, then record result.
- **Tool Discovery Tracking**: At session end, verify all used tools/runtimes are recorded in context.local.md Available Tools. Machine-specific tools go in context.local.md; project-wide conventions go in `tools/`.
- **Local Context Scope**: context.local.md is for machine-specific/personal preferences only. Project-wide decisions belong in version-controlled context files.
- **Local Context Authority**: Preferences in context.local.md govern agent engagement pacing/style, not context system health. Context system maintenance overrides process preferences.
- **Context Placement**: Apply `patterns/simplest-output.md`. Match location: user/machine preferences → `context.local.md`; domain conventions → `domains/{name}.md`; reusable approaches → `patterns/`; tool/CI behavior → `tools/{name}.md`; project facts/standards → `project/`; system rules/routing → `context.global.md`. Load `context.steering.md` if routing is unclear.
- **Local Context Maintenance**: Auto-update environment basics and workspace structure in context.local.md.
- **Command Discovery and Execution**: Match top-level user commands against `commands/` names/aliases. For exact match, read definition and execute every step as written. If no exact match, suggest near matches or direct to `list-commands`. Selected suggestions require explicit exact request before execution.
- **Knowledge Capture**: Capture non-obvious framework, tool, or environment behavior in `domains/`, `tools/`, or `patterns/` before session ends.
- **External Memory Scope**: `.ai-toolbox` is persistent project memory. All project findings belong here, not in external agent memory systems.
- **Upstream Notes**: Scan `.ai-toolbox/upstream-notes/` during planning. If a finding is project-agnostic, record in `upstream-notes/` and list in plan. Upstream notes are required deliverables.
- **Learn Before Acting**: Do not guess undocumented external APIs/environments. Sequence: consult context → if undocumented, ask user → validate → act → capture.
- **Minimal Context**: Create only necessary contexts; avoid complexity.
- **Minimal Loading**: Load only required contexts.
- **Gitignored and Untracked File Editing**: Context system files (e.g., context.local.md) may be edited automatically. All other gitignored/untracked files are read-only unless user explicitly instructs edit.
- **Gitignore Awareness**: Respect .gitignore patterns, but reference ignored files when relevant.

## Version Control Integration
- **User Exclusions**: `context.local.md` (`*.local.*` in .gitignore), `.sandbox/`, `temp/` excluded via .gitignore.
- **Project Files**: All project infrastructure committed and versioned.
- **Reference Usage**: Can examine ignored files (node_modules, build outputs) for context.
- **Upstream Notes**: `.ai-toolbox/upstream-notes/` contains findings for upstream. `README.md` is committed; finding files are gitignored.

---
*Keep this file compact and machine-readable. See `./README.md` for human documentation.*