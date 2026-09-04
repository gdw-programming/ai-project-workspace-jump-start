# List Commands

**Aliases**: `list-commands`
**Purpose**: Display all available commands in logical use order, with sub-steps shown hierarchically
**Pattern**: Read all files in commands/; for each file read the H1 command name; identify sub-steps by checking whether the command contains named sub-steps or explicitly sequences into another named command; produce plain text output in the format below
**Context**: commands/ directory
**Output format** (plain text):
```
[Command name] (filename.md)
    -- [Sub-step or sequenced command name]
```
**Hierarchy rules**:
- Named workflow sub-steps within a command appear as sub-items under the command
- Commands that are explicitly called or must run before/after another command as part of a defined sequence appear as sub-items under the initiating command
- Independent commands appear at the top level
