---
type: ai-toolbox-backlog
title: "Source Attribution and Credits"
status: pending
phase: 1
depends-on: ~
date-added: 2026-09-03
---

# Source Attribution and Credits

## Problem
The system incorporates ideas from external repositories and source materials, but user-facing credit is not yet maintained as a clear, extensible catalog. Individual backlog entries may contain source details without giving users one place to understand the system's influences.

## Change
- Maintain a user-facing Sources and Credits section in `.ai-toolbox/README.md`.
- Credit each external repository, system, idea, or source material used to inform the system with a link and a concise description of what was adapted.
- Keep detailed source and adaptation records in the relevant context or backlog files, using a `## Source` section where appropriate.
- Add authoring guidance that directs future contributors to update both the detailed record and the user-facing catalog.

## Initial Sources
- [Caveman](https://github.com/JuliusBrussee/caveman) — token-conservation rule.
- [Ponytail](https://github.com/DietrichGebert/ponytail) — simplest-output decision ladder.

## Files to touch
- `.ai-toolbox/README.md`
- `.ai-toolbox/docs/Commands.md`

## Notes
Credit only sources that are actually documented as informing the system. Keep the catalog user-facing and concise; do not duplicate full implementation rationale there.