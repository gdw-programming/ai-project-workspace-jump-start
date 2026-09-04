# Upstream Notes

Store template-agnostic findings that could improve the workspace system for all downstream projects. Finding files are personal, gitignored, and sent manually to the upstream maintainer.

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

Use `date-updated` when revising a previously sent finding and set its status to `needs-resend`. Use `~` for dates that do not apply yet.