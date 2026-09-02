# AI Project Context Management System

A portable, hierarchical context and command system for AI-assisted projects. It enables consistent team collaboration, model and agent switching, and in-repo project memory without locking workflows to a single tool.

## Getting Started with Your Project

**Quick Setup**: See [docs/Getting Started.md](docs/Getting%20Started.md) for the simple 3-step process.

**What This System Provides**: Environment detection, preference collection, and hierarchical context management that works with any AI agent system.

---

## Context Loading Patterns

```bash
# Core context always loaded first
context.global.md + context.local.md (auto-merged)

# Project initialization
context.global.md → commands/initialization.md

# Project status check
context.global.md → ../STATUS.md
```

*See the docs/ guides for extending domains, patterns, tool contexts, and commands as your project grows.*

## System Features

### Portable AI Collaboration Layer
- **Context and Command Portability**: Context routing and command patterns live in version-controlled files, so behavior travels with the repository
- **Cross-Agent Interoperability**: Works with different AI agents and model providers by using shared file-based context instead of tool-specific memory
- **Team + Local Balance**: Shared project context in `.ai-toolbox` with machine-specific preferences in `context.local.md`

### Built-In Initialization
- **Automatic Setup**: Local environment detection and context file creation
- **User Preference Collection**: Guided configuration of development workflows  
- **Zero Configuration**: Ready-to-use context system from first project use
- **Cross-Platform**: Supports Windows, macOS, and Linux development environments

See [docs/Getting Started.md](docs/Getting%20Started.md) for complete setup process.

### Intelligent Maintenance
- **Real-Time Updates**: Environment and capability changes automatically detected
- **Preference Persistence**: User workflows maintained across updates
- **Documentation Sync**: Project status automatically updated across all files

See [docs/Local Context.md](docs/Local%20Context.md) for local environment management details.

### Project Backlog and History
- **Cross-Session Tracking**: Upcoming work and recently completed items persist in [BACKLOG.md](../BACKLOG.md) across sessions
- **Collaboration Ready**: Dependency and parallel safety signals for team coordination
- **AI-Maintained**: Completed items automatically aged out to [CHANGELOG.md](../CHANGELOG.md) per configurable criteria
- **Prompt-Driven**: Add items, suggest next steps, and mark completions via natural language

See [docs/Backlog.md](docs/Backlog.md) for prompt examples and backlog management guidance.

## Core Principles

- **AI-Optimized Content**: `.ai-toolbox` content (excluding `docs/`) is structured for AI processing — not for human readers
- **Project Memory**: `.ai-toolbox` is the project's persistent memory for cross-agent and cross-tool collaboration
- **Portable Context Contract**: Context files and command definitions are the stable contract across contributors, sessions, and AI tools
- **Human Docs at Root**: Status, backlog, and changelog live at the project root as human-readable files (`STATUS.md`, `BACKLOG.md`, `CHANGELOG.md`)
- **Minimal Loading**: Load only what you need
- **Domain Agnostic**: No assumptions about project type
- **DRY Information**: Single source of truth
- **Minimal Context**: Essential information only

## Context System Structure

**Before Initialization**:
```
project-space/
├── .ai-toolbox/         # AI context management system
├── .sandbox/            # Work area for references (gitignored)
├── BACKLOG.md           # Project backlog
├── CHANGELOG.md         # Project history
├── STATUS.md            # Project status
├── README.md            # Project documentation
└── .gitignore           # Version control patterns
```

**After Initialization**:
```
your-project/
├── .ai-toolbox/         # AI context system
├── .sandbox/            # Work area for references (gitignored)
├── */*                  # Your project structure defined by you
├── BACKLOG.md           # Project backlog
├── CHANGELOG.md         # Project history
├── STATUS.md            # Project status
├── README.md            # Your project documentation
└── .gitignore           # Version control patterns
```

**AI Context System Structure**:
```
.ai-toolbox/
├── docs/                # Human-readable guides for using this system
│   ├── Getting Started.md # Simple 3-step user guide
│   ├── Local Context.md # Local environment guide
│   ├── Backlog.md       # Backlog usage guide
│   ├── Project Context.md # Project overview and standards guide
│   ├── Domains.md       # Domain context guide
│   ├── Patterns.md      # Patterns usage guide
│   ├── Tools.md         # Tool contexts guide
│   └── Commands.md      # Commands usage guide
├── context.local.md     # Machine-specific environment and personal preferences (gitignored)
├── context.global.md    # 🚀 START HERE - Central routing and maintenance rules
├── backlog/             # System development backlog items
├── commands/            # Available operations (AI-optimized)
├── project/             # Project context: overview and standards (AI-optimized)
├── domains/             # Domain-specific contexts (AI-optimized)
├── patterns/            # Reusable patterns (AI-optimized)
└── tools/               # Tool-specific contexts (AI-optimized)
```

**Project-Level Human Documents** (outside `.ai-toolbox`, maintained by AI agents):
```
STATUS.md              # Current project phase and workspace structure
BACKLOG.md             # Upcoming work and recently completed items
CHANGELOG.md           # Permanent project history and completed deliverables
```

## Usage Examples

*Note: context.local.md is automatically merged with context.global.md in all scenarios*

### Common Paths
```
context.global.md → ../STATUS.md (project status)
context.global.md → commands/initialization.md (setup new project)
```

### With Domain, Pattern, and Tool Contexts
- Domain-specific contexts for specialized project types (research.md example provided)
- Reusable patterns for common development approaches (setup.md example provided)
- Tool-specific contexts for your team's development tools (git.md example provided)

See [docs/Domains.md](docs/Domains.md) for domain context patterns and how to add new domains.
See [docs/Patterns.md](docs/Patterns.md) for pattern usage and how to add new patterns.
See [docs/Tools.md](docs/Tools.md) for tool context usage and how to add new tool contexts.
See [docs/Commands.md](docs/Commands.md) for command context usage and how to extend commands.

## Growing the System

Add contexts as needed following DRY principles and updating context.global.md routing.

## AI Agent Integration

### Example Integration
```
Your Agent Config → ai-toolbox/context.global.md → [context hierarchy]
```

### AI Agent Requirements
- **Documentation Sync**: Automatically update documentation when modifying routing
- **DRY Maintenance**: Eliminate redundancies across context files
- **Rule Application**: Follow all maintenance rules automatically

## Philosophy

This system grows organically with your needs while maintaining:
- ✅ Flexibility for any project type
- ✅ Minimal context loading overhead
- ✅ Information consistency (DRY)
- ✅ Clear navigation paths
- ✅ AI agent collaboration support

---
**AI context management system ready for any project type.**