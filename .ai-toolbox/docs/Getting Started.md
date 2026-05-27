# Getting Started

Simple 3-step process to set up any project with this AI-enabled workspace system.

## Step 1: Get the System

**From GitHub**: Click "Use this template" → Clone to your workspace  
**Download**: Download ZIP → Extract to your project folder

## Step 2: Initialize Your Project

Tell your AI agent:
```
Load context from './.ai-toolbox/context.global.md' then use the initialize command for this project: "[PROJECT_NAME]"; description: "[PROJECT_DESCRIPTION]"
```

**Example**:
```
Load context from './.ai-toolbox/context.global.md' then use the initialize command for this project: "Task Manager"; description: "Personal productivity app with React frontend"
```

## Step 3: Start Building

Your project is ready! The AI context system is now active and will:
- Automatically load your local environment and preferences
- Apply context management rules passively  
- Provide context-aware assistance

**AI Agent Setup**: Configure your agent to load context automatically at the start of every session — choose the most persistent option available:

1. **Agent memory** (preferred): Ask your agent to save to its own memory: *"For all sessions in this project, always start by loading context from './.ai-toolbox/context.global.md' and following the established maintenance rules."*
2. **Project configuration** (if agent memory is unavailable): Add the instruction below to your agent's project configuration file:
   ```
   Always start by loading context from './.ai-toolbox/context.global.md' and follow the established maintenance rules automatically.
   ```
   Common locations:
   - **GitHub Copilot (VS Code)**: `.github/copilot-instructions.md`
   - **Claude**: `CLAUDE.md` at the project root
   - **Other agents**: Consult the agent's documentation for custom instructions or system prompt configuration

Once configured, just ask for what you need — the context system works in the background.

**Further customization** (optional, after initialization):
- Define your project: [Project Context.md](Project%20Context.md)
- Add domain contexts: [Domains.md](Domains.md)
- Apply reusable patterns: [Patterns.md](Patterns.md)
- Configure tool contexts: [Tools.md](Tools.md)
- Extend command patterns: [Commands.md](Commands.md)
- Manage your backlog: [Backlog.md](Backlog.md)
- Customize your local preferences: [Local Context.md](Local%20Context.md)

---

**That's it!** The AI context system handles environment detection, preference collection, and setup automatically.