# Final Review

Use this skill before declaring an implementation or cleanup complete.

## Scope

Inspect:

    git status
    git diff

Confirm that every changed file is related to the requested task.

## File Review

Check for:

- accidental new files
- accidental deletions
- temporary files
- generated artifacts
- modified lock files
- unrelated formatting changes
- orphaned files

## Code Review

Check for:

- unused imports
- dead code
- duplicate logic
- unnecessary abstractions
- new boilerplate
- unnecessary dependencies
- changed public behavior
- missing tests
- incorrect assumptions

## Python Review

When applicable:

- inspect `pyproject.toml`
- run configured formatter/linter
- run relevant tests
- run configured type checker
- verify imports

## Verification

Only report commands that were actually executed.

Report failures honestly.

## Final Question

Before completion, answer:

> Did this change leave the repository simpler or more coherent than before?

If not, explain why.
