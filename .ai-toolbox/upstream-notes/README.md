# Upstream Notes

Store template-agnostic findings that improve the workspace system for downstream projects. Finding files are personal, gitignored, and sent manually to upstream maintainer.

## Naming
Name findings `<domain>--[slug].md`:
- `ai-toolbox--[slug].md` for workspace-system findings
- `<project-domain>--[slug].md` for domain-specific findings

## Frontmatter
Each finding starts with:
```yaml
---
type: <domain>-improvement
title: "Human-readable title"
status: pending | sent-upstream | needs-resend
date-added: YYYY-MM-DD
date-updated: ~
date-sent: ~
---
```

Use `date-updated` when revising previously sent finding and set status to `needs-resend`. Use `~` for dates not applying yet.