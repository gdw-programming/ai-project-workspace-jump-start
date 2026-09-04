# Simplest Output

Decision ladder for avoiding unnecessary context, artifacts, actions, and response content.

## Ladder
1. Does this need to exist at all?
2. Is it already covered by an existing rule or file?
3. Does an existing convention or tool already solve it?
4. Add only minimum new rule, file, command, action, or response needed.

Apply ladder before adding/changing `.ai-toolbox` content and before performing work.

## Boundaries
- Preserve information required for system purpose, capabilities, correctness, and user-requested detail.
- Prefer existing rules, patterns, commands, tools, or conventions when they fully solve need.
- Do not add abstraction, documentation, workflow, or response detail without clear benefit.
- Clarify ambiguity before acting.
- Use `patterns/context-compaction.md` when reducing existing content; this pattern decides whether new content is needed.

## Source
Adapted from [Ponytail](https://github.com/DietrichGebert/ponytail) simplest-output ladder.
