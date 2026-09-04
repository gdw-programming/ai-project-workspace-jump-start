# List Commands

**Aliases**: `list-commands`
**Purpose**: Display available commands in logical order, with sub-steps shown hierarchically.
**Pattern**: Read files in `commands/`; read H1 name; identify sub-steps; produce plain text output.
**Context**: `commands/` directory
**Output format** (plain text):
```
[Command name] (filename.md)
    -- [Sub-step or sequenced command name]
```
**Hierarchy rules**:
- Named workflow sub-steps appear as sub-items under command.
- Explicitly called or sequenced commands appear as sub-items under initiating command.
- Independent commands appear at top level.
