# Simplest Output

Decision ladder for avoiding unnecessary context, artifacts, actions, and response content.

## Ladder

1. Does this need to exist at all?
2. Is it already covered by an existing rule or file?
3. Does an existing convention or tool already solve it?
4. Add only the minimum new rule, file, command, action, or response needed.

Apply the ladder before adding or changing `.ai-toolbox` content and before proposing or performing work for a user request.

## Boundaries

- Preserve information required for the system's purpose, capabilities, correctness, and user-requested detail.
- Prefer an existing rule, pattern, command, tool, or convention when it fully solves the need.
- Do not add abstraction, documentation, workflow, or response detail without a clear benefit.
- If ambiguity affects the decision, clarify it before acting.
- Use `patterns/context-compaction.md` when reducing content that already exists; this pattern decides whether new content is needed.

## Source

Adapted from [Ponytail](https://github.com/DietrichGebert/ponytail)'s simplest-output decision ladder.
