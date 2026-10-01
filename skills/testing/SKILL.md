# Testing and Verification

Use this skill whenever behavior changes or a cleanup may affect behavior.

## Test Oracle

Before claiming a task is complete, identify what observable evidence proves
the change is correct.

Possible oracles include:

- unit tests
- integration tests
- API/contract tests
- CLI execution
- import checks
- schema validation
- generated output comparison
- end-to-end behavior
- type checking
- linting/formatting

## Test Selection

Start with the smallest relevant test.

Then broaden validation when the change crosses:

- module boundaries
- package boundaries
- external integrations
- configuration
- public APIs
- generated artifacts

## Tests Must Test Something

Do not create tests merely to increase coverage.

Avoid:

- asserting mocks instead of behavior
- tests that duplicate implementation details
- tests that pass regardless of implementation
- giant fixtures for trivial behavior
- speculative test infrastructure

## Cleanup Work

When simplifying code:

1. Run baseline tests before changes when practical.
2. Make one logical simplification.
3. Run relevant tests.
4. Inspect failures.
5. Continue only when the previous change is understood.

## Verification Honesty

Never claim:

- "tests pass"
- "build succeeds"
- "verified"
- "lint is clean"

unless the corresponding command was actually executed and succeeded.

Distinguish between:

- inspected
- reasoned about
- tested
- validated
- verified at runtime
