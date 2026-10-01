# Agent Instructions

## Mission

Make the smallest correct change that solves the requested problem while
preserving existing behavior, architecture, and repository conventions.

Prefer understanding existing code over introducing new abstractions.

## Before Changing Code

- Inspect relevant implementation and tests before editing.
- Read `pyproject.toml` before making Python/tooling/dependency decisions.
- Check for more-specific `AGENTS.md` instructions in the target directory.
- Search for existing implementations before creating new files or abstractions.
- Identify generated files and their sources of truth before modifying them.

## Complexity Discipline

Prefer the simplest implementation consistent with the repository's existing
architecture.

Do not introduce abstractions, files, layers, wrappers, factories, interfaces,
or helper modules without a concrete reason.

Do not add architecture for hypothetical future requirements.

Follow the repository's existing level of abstraction. Do not impose a preferred
architecture merely because it is common elsewhere.

## File Creation

Before creating a file:

1. Search for an existing appropriate location.
2. Search for similar files and implementations.
3. Determine whether the requested change belongs in an existing file.
4. Determine whether the target is source, generated output, configuration,
   documentation, test fixture, or an artifact.
5. Create a new file only when it represents a meaningful responsibility or
   repository conventions require it.

Do not create generic `utils.py`, `helpers.py`, `common.py`, `base.py`,
`manager.py`, or `factory.py` files without a concrete repository-specific
reason.

Do not generate boilerplate unless the repository already uses the pattern,
the framework requires it, or the task explicitly requires it.

## Abstractions

Before introducing a class, interface/protocol, factory, service, repository,
DTO, mapper, wrapper, or other abstraction, identify the concrete problem it
solves.

Do not create abstractions solely because:

- they may be useful someday
- they make mocking theoretically easier
- a tutorial or framework commonly uses them
- "clean architecture" suggests them
- there is only one function or implementation

Prefer concrete code until there is evidence that an abstraction is needed.

## Generated Files

Never manually edit generated files.

Identify the source of truth and generator, modify the source, regenerate the
artifact, and inspect the resulting diff.

If the source of truth cannot be identified, stop and investigate.

## Verification

After implementation:

1. Run the smallest relevant validation.
2. Run broader tests when the change crosses boundaries.
3. Inspect `git status`.
4. Inspect the complete diff.
5. Check for unrelated changes, orphaned files, and generated artifacts.

Never claim code was tested, built, linted, benchmarked, or verified unless the
corresponding operation was actually performed.

## Scope

Do not refactor unrelated code merely because it could be improved.

When ambiguity affects architecture, security, data integrity, public behavior,
or generated artifacts, ask before proceeding.

For ordinary implementation details, make a reasonable decision and continue.
