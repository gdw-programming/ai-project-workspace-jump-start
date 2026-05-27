# Project Initialization Command

**Trigger**: When `context.local.md` is missing during context loading
**Purpose**: Complete workspace system setup to an operational project

## Detection Pattern

If loading `context.global.md` and `context.local.md` doesn't exist → initiate this workflow

## Initialization Sequence

### Project State Detection
Before proceeding, determine which setup mode applies by checking the following:

- Does `context.development.md` still exist?
- Does `project/overview.md` contain real project content or stub/placeholder text?
- Does `README.md` still contain the pre-initialization placeholder?

**First-time setup** — `context.development.md` exists and project files contain placeholder content:
Run the full sequence below.

**Returning contributor** — `context.development.md` has been deleted and project files are populated:
- Run: Environment Detection, personal items in User Preference Collection, Local Context Creation, Validation & Handoff, and AI Agent Setup
- Skip: project-wide User Preference Collection items, Project Customization, Version Control (except personal Git settings), and the shared-file Completion steps (Remove System Development Context, Reset Changelog, Update Root README)
- Before collecting personal preferences, read `project/overview.md`, `project/standards.md`, and relevant `tools/` contexts so established project conventions are understood and reflected in the contributor's local setup

### Environment Detection
**Auto-discover**:
- Operating system (Windows, macOS, Linux)
- Primary shell (Bash, PowerShell, Zsh)
- Workspace root path
- Current date/timezone

**Capability scan**:
- Git availability and configuration
- Code editors (VS Code, etc.)
- Runtime environments (Node.js, Python, Java)
- Package managers (npm, pip, gem)
- Development tools (Docker, databases)

### User Preference Collection
*Route decisions by scope: individual and machine-specific preferences go into context.local.md; project-wide decisions that affect all contributors must go into source-controlled files (project/, tools/, domains/, or project root files) — never in context.local.md.*

**Personal workflow preferences**:
- Contributor name — used to attribute completed work in backlog and state context
- Change management style (iterative vs. batch)
- Communication style with AI agents (e.g., verbose explanations vs. concise output)

**Project tracking preferences**:
- Ask which approach the user prefers for project tracking:
  - **Built-in files** (default): Use STATUS.md, BACKLOG.md, CHANGELOG.md as provided — AI agents maintain them automatically
  - **External tools**: GitHub Issues, Jira, Notion, Linear, or other preferred tools — built-in files can be removed or kept as lightweight mirrors
  - **Minimal**: README.md updates only — no separate tracking files
- Document the chosen approach in project/standards.md — this is a project-wide decision visible to all contributors
- If using built-in files:
  - Completed item age-out criteria (default applied if not specified: 30 days OR 3 newest per contributor, whichever comes first)
    - Option A: After N days
    - Option B: Keep only N newest per contributor
    - Option C: After N days OR keep only N newest per contributor, whichever comes first
  - Update the **Active criteria** line in BACKLOG.md with the chosen or default criteria
  - Inform user they can change this at any time — see [docs/Backlog.md](../docs/Backlog.md)

**Development environment preferences**:
- Personal/machine (store in context.local.md): preferred editor/IDE, terminal and shell preferences
- Project-wide (store in tools/ contexts): package manager, build tools, test frameworks, debugging toolchain — these apply to all contributors

**File system conventions** (project-wide — store in project/standards.md):
- Cross-platform path handling
- Text encoding
- Line ending management
- File naming conventions

**Personal tool configuration** (store in context.local.md):
- Git user configuration
- IDE/editor settings
- Shell aliases and shortcuts
- Environment variables

### Local Context Creation
*Minimal context following system rules*

**Generate context.local.md** with:
1. **Environment Basics** (auto-detected)
   - OS, shell, workspace root, current date
2. **Available Tools** (auto-detected)
   - Detected development tools and capabilities
3. **User Preferences Section** (user editable area)
   - Minimal personal settings
   - Clear USER EDITABLE SECTION markers to protect from automatic updates

**User Customization Setup**:
- Explain manual editing options
- Provide prompt-based update examples
- Ensure user understands this file is not in version control
- Guide user through personalizing their development preferences

**Integration**:
- Auto-merge with global routing for all context operations
- Validate context loading paths
- Initialize preference persistence system

### Project Customization
**Structure setup**:
- Create directories based on project type
- Initialize domain contexts if applicable — see [docs/Domains.md](../docs/Domains.md) for domain context patterns
- Apply reusable patterns if applicable — see [docs/Patterns.md](../docs/Patterns.md) for pattern usage
- Configure tool contexts if applicable — see [docs/Tools.md](../docs/Tools.md) for tool context conventions
- Configure tool-specific settings

**Documentation**:
- Update root README with project info
- Populate `project/overview.md` with project name, mission, goals, and scope gathered during setup
- Populate `project/standards.md` with quality standards based on user's development preferences

### Version Control
**If Git detected**:
- Initialize repository (if needed)
- Create .gitignore for detected technologies
- Set up initial commit
- Configure user Git settings

### Validation & Handoff
**System check**:
- Verify context file linking
- Test context loading paths
- Confirm capability detection
- Validate user preferences active

**Documentation sync**:
- Update project status in README files
- Generate quick start instructions
- Create usage examples

**Completion**:
- Report initialization summary
- **Remove System Development Context**: Delete .ai-toolbox/context.development.md (not needed in project mode)
- **Reset Changelog**: Replace the deliverables table in CHANGELOG.md with a single initialization entry — item: "Initialized from AI Project Workspace Jump-Starter", contributor: name collected during setup, date: current date — this establishes a clean baseline for project history
- **Update Root README**: Replace the pre-initialization `### Getting Started` block in the README.md user-editable section (the "New to this system?" link and "Quick Start: Tell your AI agent" prompt) with a neutral placeholder — e.g., `*Add your project's getting started instructions here*` — so the developer fills it in for their actual end-users
- **AI Agent Setup**: Configure the agent to automatically load context at the start of every future session for this project — use the most persistent option available:
  1. **Agent memory** (preferred): Save to the agent's own persistent memory: *"For all sessions in this project at [workspace path], always start by loading context from './.ai-toolbox/context.global.md' and following the established maintenance rules."*
  2. **Project-level persistent config** (if agent memory is unavailable): Create or update the agent's project configuration file with the instruction `"Always start by loading context from './.ai-toolbox/context.global.md' and follow the established maintenance rules automatically."` — common locations:
     - **GitHub Copilot (VS Code)**: `.github/copilot-instructions.md`
     - **Claude**: `CLAUDE.md` at the project root
     - **Other agents**: Consult the agent's documentation for custom instructions or system prompt configuration
- Provide next steps

## Error Handling

**Skipped steps**: If the user skips a collection step (e.g., doesn't know the project name yet), leave a clear `[TODO: update this]` placeholder in the affected file and note which files need manual update
**Graceful degradation**: Continue if non-critical steps fail; flag for manual completion

---

*This command creates a fully operational, environment-aware project workspace ready for immediate development.*