# Project Initialization Command

**Aliases**: `initialization`
**Trigger**: `context.local.md` missing during context loading
**Purpose**: Complete workspace setup to operational project state

## Detection Pattern
If `context.local.md` missing when loading `context.global.md` → initiate workflow.

## Initialization Sequence

### Project State Detection
Check workspace state before proceeding:
- Does `context.development.md` exist?
- Does `project/overview.md` contain stub/placeholder text?
- Does `README.md` contain pre-initialization placeholder?
- Does workspace contain established non-template project files (source dirs, populated README, changelog history, existing Git repo)?

**First-time setup** — `context.development.md` exists and project files contain placeholder content:
Run full sequence below.

**Existing-project setup** — `context.development.md` exists, but workspace contains established project files or history:
- Priority higher than First-time setup when both appear true. Template docs/ and metadata stubs do not indicate existing project alone.
- Before customization, ask project owner to inventory source structure, README/docs, CHANGELOG, Git repo/remotes, project metadata, team tool conventions.
- Ask whether to use **retrofit setup** or proceed with **full initialization**. Do not choose full initialization silently.
- Retrofit setup preserves existing source files, project directories, README, documentation, CHANGELOG, Git history, remotes. Changes to existing project files require explicit approval.
- Use existing docs to suggest metadata; confirm before populating `project/overview.md` or `project/standards.md`. Leave placeholders for unconfirmed info.
- If owner cannot confirm project state, stop before destructive steps and ask clarification.

**Returning contributor** — `context.development.md` deleted and project files populated:
- Run: Environment Detection, personal items in User Preference Collection, Local Context Creation, Validation & Handoff, AI Agent Setup.
- Skip: project-wide User Preference Collection, Project Customization, Version Control (except personal Git settings), shared Completion steps (Remove System Dev Context, Reset Changelog, Update Root README).
- Before personal preferences, read `project/overview.md`, `project/standards.md`, relevant `tools/` contexts.

### Environment Detection
**Auto-discover**:
- OS (Windows, macOS, Linux)
- Primary shell (Bash, PowerShell, Zsh)
- Workspace root path
- Current date/timezone

**Capability scan**:
- Git availability and config
- Code editors (VS Code)
- Runtime environments (Node.js, Python, Java)
- Package managers (npm, pip, gem)
- Dev tools (Docker, databases)

### User Preference Collection
*Route decisions by scope: individual/machine preferences → `context.local.md`; project-wide decisions → source-controlled files (`project/`, `tools/`, `domains/`, `context.global.md`).*

**Personal workflow preferences**:
- Contributor name (used to attribute completed work)
- Change management style (iterative vs. batch)
- Communication style with AI agents (concise vs. verbose)

**Project tracking preferences**:
- Ask user preference:
  - **Built-in files** (default): Use STATUS.md, BACKLOG.md, CHANGELOG.md — AI agents maintain automatically
  - **External tools**: GitHub Issues, Jira, Notion, Linear — built-in files removed or kept as lightweight mirrors
  - **Minimal**: README.md updates only — no separate tracking files
- Document approach in `project/standards.md`.
- If using built-in files:
  - Completed item age-out criteria (default: 30 days OR 3 newest per contributor, whichever comes first): Option A (N days), Option B (N newest per contributor), Option C (N days OR N newest per contributor).
  - Update **Active criteria** line in BACKLOG.md. Inform user criteria can be changed anytime (see [docs/Backlog.md](../docs/Backlog.md)).

**Branching strategy preference**:
- Ask if project wants enforced feature-branch-only workflow (never commit to main/master):
  - **Enforced**: Populate **Branching strategy** line in `tools/git.md` with Branch Protection rule below.
  - **Not enforced**: Leave placeholder in `tools/git.md`.
- If enforced, use text verbatim:
  > **Branch Protection**: All code changes must land on a feature branch — never directly on main/master. Determine the correct branch during planning: if the work continues an existing feature branch, identify it and confirm; if on main/master at implementation start, the first action before any file edit is to create a new branch per tools/git.md conventions. Post-plan, verify the active branch before proceeding. This is especially important for private repositories where branch protection rules may not be configured — this rule is the only safeguard against committing directly to main.

**Development environment preferences**:
- Personal/machine (`context.local.md`): editor/IDE, terminal, shell preferences.
- Project-wide (`tools/` contexts): package manager, build tools, test frameworks, debugging toolchain.

**File system conventions** (`project/standards.md`):
- Cross-platform path handling, text encoding, line endings, file naming conventions.

**Personal tool configuration** (`context.local.md`):
- Git user config, IDE settings, shell aliases, environment variables.

### Local Context Creation

**Generate context.local.md**:
1. **Environment Basics** (auto-detected: OS, shell, workspace root, date)
2. **Available Tools** (auto-detected dev capabilities)
3. **User Preferences Section** (minimal personal settings with USER EDITABLE SECTION markers)

**User Customization Setup**:
- Explain manual editing options and prompt-based updates. Ensure user understands file is gitignored.

**Integration**:
- Auto-merge with global routing; validate loading paths.

### Project Customization
**New project structure setup**:
- Create directories based on project type.
- Initialize domain contexts (`docs/Domains.md`), apply patterns (`docs/Patterns.md`), configure tool contexts (`docs/Tools.md`).
- Create `.ai-toolbox/upstream-notes/` with committed `README.md` stub.

**Existing-project retrofit**:
- Preserve established project structure. Review existing docs; populate metadata only after owner confirmation.
- Configure `.ai-toolbox` contexts and approved changes only.

**Documentation**:
- **New project**: Update root README with project info. Populate `project/overview.md` (mission, goals, scope) and `project/standards.md`.
- **Existing-project retrofit**: Preserve root README and populate `project/overview.md` / `project/standards.md` only after owner confirmation.

### Version Control
**If Git detected**:
- **New project**: Initialize repository if needed, create .gitignore for detected tech, set up initial commit, configure Git settings.
- **Existing-project retrofit**: Preserve existing repository, history, remotes, .gitignore. Do not rewrite history or create initial commit automatically.

### Validation & Handoff
**System check**:
- Verify context file linking, test loading paths, confirm capability detection, validate user preferences.

**Documentation sync**:
- **New project**: Update project status in README files, generate quick start instructions and usage examples.
- **Existing-project retrofit**: Preserve existing docs; offer suggested status/quick start changes for owner approval.

**Completion**:
- Report initialization summary.
- **Remove System Dev Context**: Delete `.ai-toolbox/context.development.md`.
- **Reset Changelog (new project)**: Replace deliverables table in CHANGELOG.md with single initialization entry ("Initialized from AI Project Workspace Jump-Starter", contributor name, date).
- **Preserve Changelog (existing retrofit)**: Keep existing CHANGELOG history.
- **Update Root README (new project)**: Replace pre-initialization `### Getting Started` block in README.md with neutral placeholder (`*Add your project's getting started instructions here*`).
- **Preserve Root README (existing retrofit)**: Do not replace content.
- **AI Agent Setup**: Configure agent to auto-load context at start of future sessions:
  1. **Agent memory** (preferred): *"For all sessions in this project at [workspace path], always start by loading context from './.ai-toolbox/context.global.md' and following the established maintenance rules."*
  2. **Project-level persistent config**: Add instruction `"Always start by loading context from './.ai-toolbox/context.global.md' and follow the established maintenance rules automatically."` (`.github/copilot-instructions.md`, `CLAUDE.md`, etc.).
- Provide next steps.

## Error Handling
**Skipped steps**: Leave clear `[TODO: update this]` placeholder and note affected files.
**Graceful degradation**: Continue if non-critical steps fail; flag for manual completion.

---
*Creates operational, environment-aware project workspace ready for immediate development.*