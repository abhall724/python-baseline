# Python Development

Use this skill for Python implementation, dependency, packaging, and tooling
changes.

## Source of Truth

Inspect `pyproject.toml` before making assumptions about:

- Python version
- dependencies
- package layout
- formatter
- linter
- test runner
- type checker
- build system

Do not duplicate configuration from `pyproject.toml` into agent instructions.

## Package Management

Use the repository's existing package manager.

If the repository uses `uv`:

- use `uv add` / `uv remove` for dependencies
- use `uv run` to execute project commands
- treat `uv.lock` as generated dependency state
- never manually edit `uv.lock`

Do not introduce a package manager because it is preferred elsewhere.

## Python Structure

Follow the repository's existing package structure.

Do not create:

- `utils.py`
- `helpers.py`
- `common.py`
- `base.py`

without a concrete responsibility that fits the repository.

Do not create a class merely because a function exists.

Prefer functions for stateless behavior unless an existing architectural
pattern or concrete state/lifecycle boundary justifies a class.

## Dependencies

Before adding a dependency:

1. Check existing dependencies.
2. Check whether the standard library is sufficient.
3. Check whether an existing project dependency already provides the capability.
4. Confirm the dependency is appropriate for the project's supported Python
   version.
5. Add it using the repository's package manager.

## Type Hints

Follow the repository's existing type-checking conventions.

Do not add elaborate typing constructs merely to satisfy an abstract notion of
"clean Python."

## Imports

Use the repository's existing import conventions.

After refactoring, remove orphaned imports and verify package imports.

## Validation

Prefer the repository's configured commands. Typical examples include:

    uv run ruff check .
    uv run ruff format --check .
    uv run pytest
    uv run pyright

Do not assume these commands exist; inspect project configuration first.
