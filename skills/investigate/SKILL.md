# Investigate

Use this skill for unfamiliar code, debugging, architectural changes, or
behavior whose cause is not immediately obvious.

## Goal

Establish evidence before changing implementation.

## Process

1. Identify the user-visible or system-level behavior.
2. Locate the relevant entry point.
3. Trace the execution path.
4. Search for tests around the behavior.
5. Identify the first point where observed behavior diverges from expected
   behavior.
6. Form a concrete hypothesis.
7. Verify the hypothesis against code, tests, logs, or runtime evidence.
8. Only then propose or implement the change.

## Evidence Priority

Prefer:

1. Tests
2. Runtime behavior and logs
3. Existing implementations
4. Configuration
5. Documentation
6. Framework conventions
7. Model memory

Do not infer current library APIs when the installed dependency or authoritative
documentation can be inspected.

## Avoid

- speculative fixes
- unrelated refactors
- rewriting code before identifying the cause
- creating abstractions to make an investigation easier
- treating a plausible explanation as a verified root cause

## Completion

Before implementation, be able to state:

- what is happening
- where it happens
- why it happens
- what evidence supports that explanation
- how the proposed change will prove or disprove the hypothesis
