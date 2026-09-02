---
type: ai-toolbox-backlog
title: "Upstream Notes System"
status: pending
phase: 3
depends-on: 1, 2, 4, 5
date-added: 2026-09-02
---

# Upstream Notes System

## Problem
Downstream projects built from this template discover template-agnostic improvements but have no structured, repeatable way to send them back upstream. A prior downstream project used this pattern manually (dropping notes into a local scratch folder for later hand-off) — this item formalizes it as a first-class toolbox feature.

## Change
1. Add `.ai-toolbox/upstream-notes/` to `.gitignore` (with an exception so `upstream-notes/README.md` stays committed).
2. Document in `context.global.md` Version Control Integration: `upstream-notes/` holds personal notes for findings to send back to the upstream template project; `README.md` is committed, finding files are not versioned.
3. Add an Operational Behavior rule in `context.global.md`: **Upstream Notes** — when a finding is agnostic to the current project and would improve the template for all downstream projects, add it as a new file in `.ai-toolbox/upstream-notes/` using the naming convention in its `README.md`; finding files are gitignored and sent manually to the upstream maintainer. Upstream notes are a required deliverable for every change set — during planning, scan existing upstream notes for relevant findings and list any that need creating/updating as explicit plan items.
4. Add a line to the `commands/review-change-set.md` checklist (after Knowledge capture): verify template-agnostic findings from this work are captured in `.ai-toolbox/upstream-notes/`; set `date-updated` and `status: needs-resend` on any previously-sent finding that was revised.
5. Create `.ai-toolbox/upstream-notes/README.md` with the naming convention `<domain>--[slug].md` (e.g. `ai-toolbox--[slug].md` for toolbox-wide findings; project-specific prefixes for anything domain-specific) and the YAML frontmatter format:
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
6. Wire folder creation (with the README stub) into `commands/initialization.md` so the pattern is discoverable from first use.

## Files to touch
- `.gitignore`
- `.ai-toolbox/context.global.md` (Version Control Integration, Operational Behavior)
- `.ai-toolbox/commands/review-change-set.md` (checklist)
- `.ai-toolbox/upstream-notes/README.md` (new)
- `.ai-toolbox/commands/initialization.md` (folder creation step)

## Notes
`date-updated` tracks revisions to previously-sent findings; `needs-resend` status flags when upstream has stale content relative to what was sent.
