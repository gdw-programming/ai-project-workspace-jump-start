# Tool-Specific Contexts

Tool contexts define shared conventions, configurations, and workflow standards for development tools. Load only relevant tool contexts.

## Available Tools
- [**git.md**](git.md) — Version control context and conventions
- [**package-managers/**](package-managers/README.md) — Package-manager security audit and remediation patterns

## Usage
Tool contexts provide:
- Team conventions and preferences for specific tools
- Project-relevant configuration patterns
- Integration points with `domains/` and `patterns/`

```
context.global.md → tools/{tool}.md
```

Combine with domain or pattern context when tool guidance is needed:
```
patterns/setup.md + tools/git.md → version-controlled project setup
```

---
*See [docs/Tools.md](../docs/Tools.md) for usage guidance.*