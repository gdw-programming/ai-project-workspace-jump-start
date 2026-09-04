# Project Status

Human-readable project status. Updated by AI agents as the project evolves.

---

## Current Phase
Ready to initialize project

## Project
Context system operational

---

## Capabilities
- Context and command portability across sessions, contributors, and AI tooling
- Team collaboration through shared, version-controlled project context with local contributor overrides
- Model and agent switching using file-based context routing instead of vendor-specific memory
- Extended in-repo documentation and operational history via STATUS.md, BACKLOG.md, and CHANGELOG.md
- Project initialization workflow with user preference collection and local environment adaptation

---

## Workspace Structure
```
ai-project-workspace/            # Project root
├── .ai-toolbox/                 # AI context management system
│   ├── context.development.md  # System development context (deleted at initialization)
│   ├── context.global.md        # Central routing and maintenance rules
│   ├── context.steering.md      # On-demand keyword and topic routing index
│   ├── backlog/                 # System development backlog items
│   │   ├── 09-upstream-notes-system.md
│   │   ├── 10-package-manager-security-tooling.md
│   │   └── 13-brain-first-planning-and-research.md
│   ├── commands/                # Available operations — one file per command
│   │   ├── README.md           # Commands directory guide and index
│   │   ├── initialization.md   # Project initialization (auto-triggered)
│   │   ├── list-commands.md    # List all available commands
│   │   ├── load-context-chain.md # Load contexts following hierarchy
│   │   ├── validate-context-chain.md # Check context references
│   │   ├── compact-context.md      # Reduce natural-language context
│   │   ├── update-work-context.md # Update work tracking and backlog
│   │   ├── add-domain-context.md # Create new domain-specific context
│   │   ├── initialize-project.md # Set up basic project structure
│   │   ├── organize-structure.md # Create logical directory organization
│   │   ├── setup-quality-gates.md # Establish basic quality controls
│   │   ├── document-project.md # Create appropriate documentation
│   │   ├── review-change-set.md # Verify change set consistency
│   │   ├── describe-change-set.md # Generate change set summary
│   │   ├── define-project-scope.md # Establish project boundaries
│   │   ├── track-progress.md   # Monitor project status
│   │   ├── maintain-standards.md # Ensure consistent quality
│   │   └── plan-next-phase.md  # Identify upcoming work
│   ├── docs/                   # AI context system documentation
│   │   ├── Getting Started.md  # User onboarding guide
│   │   ├── Local Context.md    # User customization guide
│   │   ├── Backlog.md          # Backlog usage guide
│   │   ├── Project Context.md  # Project overview and standards guide
│   │   ├── Domains.md          # Domain contexts guide
│   │   ├── Patterns.md         # Patterns usage guide
│   │   ├── Tools.md            # Tool contexts guide
│   │   ├── Commands.md         # Commands usage guide
│   │   └── Steering.md         # Steering context guide
│   ├── project/                # Project context
│   │   ├── README.md           # Project directory guide
│   │   ├── overview.md         # Project mission and goals
│   │   └── standards.md        # Universal quality guidelines
│   ├── domains/                # Domain-specific contexts
│   │   ├── README.md           # Domain directory guide
│   │   └── research.md         # Research and discovery domain
│   ├── patterns/               # Reusable patterns
│   │   ├── README.md           # Patterns directory guide
│   │   ├── setup.md            # Project setup patterns
│   │   ├── context-compaction.md # Context compaction pattern
│   │   └── simplest-output.md   # Simplest-output decision ladder
│   ├── tools/                  # Tool-specific contexts
│   │   ├── README.md           # Tools directory guide
│   │   └── git.md              # Git version control context
│   └── README.md               # AI context system overview
├── BACKLOG.md                  # Project backlog and recently completed work
├── CHANGELOG.md                # Project history and completed deliverables
├── STATUS.md                   # This file — current project status
├── .gitignore                  # Version control patterns
└── README.md                   # Project overview

```

---

*Updated automatically during operations.*
