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

## Sending Manually
1. Identify the notes to send: those with `status: pending` or `needs-resend`. List them for the user.
2. Send them by the user's chosen method. Do not change any metadata yet.
3. Ask the user to confirm which notes were actually sent.
4. For each confirmed note only, set `status: sent-upstream` and `date-sent` to the send date. Leave `date-updated` unchanged. Leave unconfirmed notes as they are.
5. Verify the notes marked `sent-upstream` match the confirmed send exactly, and that no unsent note was marked.