# Context Global Routing

**AI Agent Entry Point**: Start here for all context loading. `context.local.md` automatically merged.

`.ai-toolbox` is the project's portable brain: its persistent memory and context make project knowledge travel across agents, tools, sessions, and contributors. Load the relevant context before acting so this shared project knowledge remains the basis for decisions.

**Local Context Required**: `context.local.md` is machine-specific and gitignored — each contributor creates their own. If it doesn't exist, follow `./commands/initialization.md` to create it before proceeding. Its absence means only that this contributor hasn't created their personal context file — not that the project itself is uninitialized; collaborators cloning an established project will not have this file.

## Definitions
- **Project**: The current project using this context management system
- **Context System**: The hierarchical context management structure within the project
- **Root README**: `../README.md` (project-level documentation)
- **System README**: `./README.md` (context system documentation)

## Hierarchy Levels
1. **Core**: context.global.md + context.local.md (auto-merged, generated if missing)
2. **Operational**: available commands/ + project tracking files (STATUS.md, BACKLOG.md, CHANGELOG.md — pre-configured templates, configured during initialization)
3. **Domain**: domains/ (research.md example provided) + patterns/ (setup.md example provided) + tools/ (git.md example provided)
4. **Project**: project/ (pre-configured stubs — populate with your project details)

## Standard Loading Paths
*Organized by logical importance and application order*

**Core Context**: context.global.md + context.local.md (auto-merged)
**Project Status**: context.global.md → ../STATUS.md
**Initialization**: context.global.md → commands/initialization.md
**Unclear Routing**: context.global.md → context.steering.md (on demand)

### Loading Sequence
1. **Core**: context.global.md + context.local.md (auto-merged)
2. **Operational**: available commands/ + project tracking files (STATUS.md, BACKLOG.md, CHANGELOG.md — load if configured for use)
3. **Domain**: domains/ + patterns/ + tools/
4. **Project**: project/ (overview.md, standards.md — populate with your project details)

*Additional loading paths available as modules are configured*

## Available Contexts

### Level 2 (Operational)
**Project Tracking Files** — pre-configured templates. Use as-is, adapt the format, or replace with preferred tools (GitHub Issues, Jira, Notion, etc.) — configure your approach during initialization.
- `../STATUS.md` - project status (phase, capabilities, workspace structure)
- `../BACKLOG.md` - project backlog and recently completed work
- `../CHANGELOG.md` - project history and completed deliverables

### Level 3 (Domain)
- `domains/` - domain-specific contexts (research.md example provided)
- `patterns/` - reusable patterns (setup.md example provided)
- `tools/` - tool-specific contexts (git.md example provided)

*Additional operational commands available in commands/ directory*

## Maintenance Rules
*Organized by logical importance and application order*

### Critical System Rules (Always Applied First)
- **Global Rule Authority**: `context.global.md` is the mandatory, always-enforced center for project-wide rules; every session must treat its Maintenance Rules as binding constraints and check them before acting. Apply the `Rule Compliance Gate` and `Correction Integration` rules when evaluating or refining those constraints.
- **Initialization Check**: If context.local.md missing, initiate project setup workflow before proceeding
- **AI Agent Discipline**: Always follow maintenance rules - automatic rule application required, not optional
- **AI-Optimized Content**: `.ai-toolbox` content (excluding `docs/`) is structured for AI processing and understanding — not for human readers. Human-friendly documentation for the context system lives in `.ai-toolbox/docs/`. Human-facing project status, history, and planning documents (`STATUS.md`, `BACKLOG.md`, `CHANGELOG.md`) live at the project root outside `.ai-toolbox`.
- **Project Memory Authority**: `.ai-toolbox` is the project's persistent memory and preferences for cross-agent and cross-tool collaboration. All project-specific findings, domain knowledge, preferences, and work context belong here — not in external agent memory systems, session notes, or out-of-repo tools. Context files are the shared, version-controlled source of truth.
- **DRY Enforcement**: Detect and eliminate information duplication across all context files
- **Reference Validation**: Verify all context references before changes
- **Cross-Reference Validation**: Ensure all file paths and references work
- **Workflow Agnostic**: No references to specific user workflows (git staging, commit patterns, etc.) in context files or documentation - let users choose their own workflow preferences
- **Context Organization**: Keep all context files organized by logical importance and application order - most critical rules first, supporting details last
- **Human Reading Order**: Organize all content — commands, rules, and reference material — in the logical sequence a human reader would encounter it: prerequisites before dependent items, operations in the order they would naturally be used, edge cases and exceptions after the main rules they qualify

### Content Management Rules
- **Auto-Sync Targets are Dependencies**: root README.md must stay in sync with committed content at all times. Project tracking files (STATUS.md, BACKLOG.md, CHANGELOG.md) apply only if the project is configured to use them — if any in-use file is out of sync, fix it immediately as a dependency, not a future task
- **State Consistency**: Sync status across README.md, STATUS.md, and other contexts
- **Backlog Auto-Management**: If using the built-in BACKLOG.md and CHANGELOG.md: mirror all completed items to CHANGELOG.md; age out Recently Completed entries in BACKLOG.md per criteria defined in BACKLOG.md; completed items must exist in both BACKLOG.md and CHANGELOG.md until aged out. In all cases: Recently Completed tracks project deliverables and features only — context system maintenance (updating rules, adding context files, adjusting documentation structure) is not recorded; "completed" means verified working and user-confirmed — code written does not qualify
- **Contributor Attribution**: When recording completed items in project tracking files (BACKLOG.md, CHANGELOG.md): always use the Contributor Name from context.local.md User Preferences — if not set, prompt the user for their name before recording
- **Documentation Sync**: Auto-sync between ../README.md and ./README.md when changing linked contexts or project status
- **File Reference Standards**: Never use Markdown links to files that have not yet been committed — use plain text references only; Markdown links to uncommitted files create broken documentation
- **Path Validation**: Ensure all context file paths work for end users
- **Agent Agnostic**: No agent/user references in context files except context.local.md personalization file
- **Passive Updates**: All context file and documentation updates automatically synchronized by processing agents

### Documentation Standards
- **Documentation Separation**: Root README = project content, .ai-toolbox/README.md = context system documentation
- **Context Framing**: tools/, domains/, and patterns/ use team/project framing ("your team's conventions", "your project's standards") — context.local.md is the only file that uses personal framing ("your preferences", "your environment")
- **Markdown Links**: All file references in documentation (README files, docs/) must use proper Markdown link syntax with URL-encoded spaces — `[Display Text](path/to/file.md)` — bare path references like `` `./.ai-toolbox/file.md` `` do not create clickable links
- **Auto-Sync Documentation**: Update ../README.md project status section from STATUS.md
- **Project State Language**: Use "ready to initialize project" or current project state, not development language
- **Technical Terms Exception**: Allow specific technical terms like GitHub's "Use this template" button, API names, and platform-specific features that have established meanings
- **Documentation Location Map**: Four distinct audiences, each with a designated location — (1) **AI agents**: `.ai-toolbox/` (excluding `.ai-toolbox/docs/`) — context rules, domain knowledge, commands, patterns, tools; content here is structured for AI processing, not human readers; (2) **Project status and history**: `STATUS.md`, `BACKLOG.md`, `CHANGELOG.md` at the project root — pre-configured project tracking templates; use as-is, adapt, or replace with preferred external tools — configured during initialization; (3) **Developers building with this project**: `README.md` is the first-contact entry point, `/docs/` is human-facing project documentation (setup, architecture, testing, contributing), `.ai-toolbox/docs/` is human-readable guidance on how to use the AI context system to assist development — what help is available, how to leverage it, and how to extend it for the project; (4) **End-users of the finished product**: structure is the developer's choice — this template does not own that space. Additional documentation structure beyond `README.md` is the developer's decision
- **Present-Tense Voice**: All documentation describes current state — do not use change-referencing language ("fixed", "improved", "enhanced", "updated", "now", "added") outside of changelogs; changelogs are the only sanctioned location for documenting what changed
- **Progressive Disclosure**: Structure human-facing documents in reader-need order — (1) one-sentence description of what it is, (2) direct usage steps or command, (3) only necessary detail for correct usage, (4) background and reference content last or in a linked document; if a document feels like it needs a summary or TL;DR, restructure it instead

### Operational Behavior
- **Clarify Before Acting**: Before taking action on any request, verify the loaded context is sufficient to proceed with confidence. If the request is ambiguous, the scope is unclear, or required information is missing, ask targeted questions before proceeding — do not assume, infer, or proceed on best guesses. Ask for the minimum information needed; prefer specific questions with examples or options over open-ended prompts. When clarification reveals project-level information or decisions, capture them in the appropriate context file — session responses are not a substitute for persistent context.
- **Rule Compliance Gate**: Before executing any action, verify it is consistent with the rules in the loaded context. If an action would violate an established rule or if the user's request conflicts with context rules, do not proceed silently — identify the applicable rule, explain the conflict, and ask for explicit permission to deviate or for guidance to resolve it. If uncertain whether an action falls within established rules, ask rather than assume.
- **Correction Integration**: When the user corrects the agent or reminds it of a rule, preference, or how they want something done, immediately update the appropriate `.ai-toolbox` context file to enforce the correction — do not rely on session memory or assume retention across sessions. `.ai-toolbox` is the primary and authoritative source of direction; all corrections and refinements belong here to persist across sessions, agents, and collaborators. Treat every user correction as a signal that the context system is incomplete and must be updated before proceeding.
- **Workspace State Awareness**: Not all workspace changes are agent-initiated — users may manually edit files, stage changes, run commands, or install tools independently between agent interactions. Before responding to any request that depends on the current state of the workspace (staged files, file content, available tools, active branch, etc.), read the current state directly rather than relying on session memory. Do not deny or fail a request based on assumed state; verify first. When a user-initiated change is discovered (e.g., a new tool recorded in context.local.md, a manually staged file), incorporate it immediately without requiring reinitialization.
- **Tool Resolution Loop**: Before attempting any task that requires a specific tool or capability — check context.local.md Available Tools first; if the tool is not recorded, prompt the user before assuming it is available or choosing an alternative; once resolved, record the result (available or unavailable + alternative) before proceeding; if the user reports a recorded status is incorrect, re-verify via shell and update the record before continuing
- **Tool Discovery Tracking**: At the end of every session, verify that all tools, runtimes, and capabilities used are recorded in context.local.md Available Tools — add any that are missing before closing. When a tool is used or found missing mid-session, record it immediately rather than waiting. Machine-specific tools (shell type, OS utilities, local runtimes, PDF readers, available commands) go in context.local.md Available Tools; project-wide tool conventions (build tools, test frameworks, deployment targets) go in tools/ contexts; if a needed tool is unavailable, record the absence and the alternative used
- **Local Context Scope**: context.local.md is for machine-specific and personal preferences only — things that vary by individual contributor or machine (OS, shell, editor, contributor name, communication style). Any decision that affects all contributors or the project as a whole must be stored in a source-controlled file (project/, tools/, domains/, context.global.md, or project root files) — never in context.local.md; project decisions stored only in context.local.md are invisible to other contributors and agents and will be lost when context.local.md is regenerated
- **Local Context Authority**: Preferences in context.local.md govern how the agent engages — pacing, communication style, approval gates — not whether the context system evolves or stays accurate. A local preference that would prevent the context system from being updated, kept in sync, or progressed must be flagged to the user as a conflict rather than silently honored; the system's health takes precedence over process preferences
- **Context Placement**: When adding to or updating the context system, use the first matching location — user/machine-specific tools, environment, or personal work-style preferences → `context.local.md`; domain knowledge, framework behavior, or domain-specific conventions → `domains/{name}.md`; reusable approaches that apply across domains → `patterns/`; tool behavior, conventions, or CI/CD workflows → `tools/{name}.md`; project facts, scope, stakeholders, or quality standards → `project/overview.md` or `project/standards.md`; system-wide behaviors, maintenance rules, or routing logic → `context.global.md`. If routing is unclear, load `context.steering.md` on demand before proposing a location.
- **Local Context Maintenance**: Auto-update environment basics and workspace structure in context.local.md
- **Command Execution**: When the user invokes a named command, read its definition from the commands/ directory and execute every step as written — do not answer from session memory or skip steps because the answer seems known. Session context may be incomplete or stale; the command definition is authoritative.
- **Knowledge Capture**: Any framework behavior, environment pattern, tool behavior, or non-obvious constraint discovered during a session must be captured in the appropriate context file (`domains/`, `tools/`, or `patterns/`) before the session ends. If a behavior is unverified, record it in the relevant context file marked as unverified rather than omitting it. Framework/library behavior → domain contexts; fragile vs. stable patterns → `patterns/`; tool-specific behavior → `tools/`. Review Change Set enforces this as a pre-commit checklist item.
- **External Memory Scope**: `.ai-toolbox` is the project's persistent memory — project-specific findings, domain knowledge, preferences, and work context belong here, not in external agent memory systems (Copilot memory, session notes, out-of-repo tools). External agent memory is for personal preferences and session-portable agent identity only. Context files are the shared, version-controlled source of truth for all collaborators and agents working on the project.
- **Learn Before Acting**: For any external, third-party, or poorly-documented environment or API, do not guess at behavior, selectors, timing, or structure. If the required interaction is not documented in the relevant context file, stop and ask the user — do not attempt, fail, and then capture. The correct sequence is: consult context → if undocumented, ask → validate with user → act → capture.
- **Minimal Context**: Create only necessary contexts for project use, avoid unnecessary complexity
- **Minimal Loading**: Load only required contexts
- **Gitignored and Untracked File Editing**: Context system files (e.g., context.local.md) may be edited automatically even though they are gitignored. All other gitignored or untracked files — including `.sandbox/` and other personal reference directories — are read-only by default; edit only when the user explicitly instructs an edit to that specific file. Untracked changes are invisible in source control and can be missed during review.
- **Gitignore Awareness**: Respect .gitignore patterns for file usage in project structure, but reference or use ignored files when contextually relevant

## Version Control Integration
- **User Exclusions**: `context.local.md` (covered by `*.local.*` in .gitignore), `.sandbox/` (gitignored), `temp/` excluded via .gitignore
- **Project Files**: All project infrastructure committed and versioned
- **Reference Usage**: Can examine ignored files (node_modules, build outputs) for context without including in commits

---
*Keep this file compact and machine-readable. See `./README.md` for human documentation.*