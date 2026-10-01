# LLM Boilerplate Cleanup

Use this skill when a repository has accumulated excessive abstractions,
boilerplate, duplicated concepts, or unnecessary files from AI-generated work.

## Goal

Restore a coherent, simple architecture without changing intended behavior.

Do not optimize for fewer files.

Optimize for fewer unnecessary concepts, layers, representations, and
indirection.

## Phase 1 — Freeze Behavior

Before modifying code:

- inspect `git status`
- inspect current diff
- establish the existing test/validation baseline
- identify entry points
- identify generated files
- identify external integrations

Do not begin by deleting code.

## Phase 2 — Build an Inventory

Look for:

- one-implementation interfaces/protocols
- one-function classes
- pass-through services
- pass-through repositories
- one-product factories
- unnecessary managers/handlers
- duplicate DTOs/models
- field-for-field mappers
- wrapper layers
- generic utility modules
- duplicate configuration
- unused files
- unused dependencies
- generated artifacts treated as source
- unnecessary package files

For every candidate document:

- what it does
- who consumes it
- what complexity it hides
- whether it creates a meaningful boundary
- whether multiple implementations exist
- what would replace it
- confidence level

Do not modify code during inventory.

## Phase 3 — Classify

Use exactly one:

### KEEP
Concrete value exists.

### COLLAPSE
Can be replaced by a simpler implementation without losing a meaningful
boundary.

### MERGE
Multiple concepts represent the same responsibility.

### DELETE
No meaningful consumer or behavior remains.

### DEFER
Purpose or consequences are uncertain.

When uncertain, DEFER.

## Abstraction Test

Ask:

> What concrete problem does this abstraction solve?

Strong reasons to keep an abstraction include:

- multiple real implementations
- meaningful domain boundary
- infrastructure boundary
- shared behavior
- lifecycle management
- security isolation
- transaction boundary
- external system isolation
- framework requirement
- meaningful polymorphism
- independently evolving component

Do not keep an abstraction merely because it:

- could be useful someday
- makes mocking theoretically easier
- is common in tutorials
- is called "clean architecture"
- looks enterprise-grade
- hides a trivial forwarding call

## Phase 4 — Simplify in Batches

Do not perform a massive uncontrolled refactor.

Recommended order:

1. Remove unused artifacts.
2. Remove dead abstractions.
3. Collapse pass-through layers.
4. Merge duplicate concepts.
5. Simplify remaining structures.
6. Reassess architecture.

Run validation after each logical batch.

## File Creation Rule

Do not create a new file merely to relocate code.

Do not replace:

    service.py -> manager.py

or:

    factory.py -> provider.py

unless the replacement solves a real problem.

## Generated Files

Never manually simplify generated output.

Find the source of truth and generator first.

If unknown, DEFER.

## Final Cleanup Review

Check:

- deleted/renamed symbol references
- unused imports
- orphaned files
- duplicate implementations
- duplicate configuration
- accidental dependency changes
- generated artifacts
- unrelated edits

Then inspect the complete diff.

## Cleanup Success

A successful cleanup should reduce at least one meaningful dimension of
complexity:

- call depth
- number of concepts
- number of representations
- indirection
- sources of truth
- dependency surface
- navigation cost
- unnecessary files

Renaming or rearranging code without reducing complexity is not a cleanup.
