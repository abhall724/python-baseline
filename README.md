\
# Agent Baseline

A minimal baseline for Python repositories using coding agents.

## Structure

```text
AGENTS.md
skills/
├── README.md
├── investigate/
├── file-creation/
├── python/
├── testing/
├── cleanup/
└── final-review/
templates/
└── CLEANUP_PROMPT.md
```

## Installation

Copy `AGENTS.md` into the repository root.

Copy the `skills/` directory into the agent's supported skills location, or
adapt the files to the agent you use.

The skills are deliberately procedural. They should not replace repository
documentation or project configuration.

## Recommended workflow

For normal work:

1. `investigate` when behavior or architecture is unclear.
2. `file-creation` when creating or substantially modifying artifacts.
3. `python` for Python-specific work.
4. `testing` for implementation and validation.
5. `final-review` before completion.

For an over-engineered repository:

1. `cleanup`
2. `testing`
3. `final-review`

## Customize First

Before using this baseline in production, update:

- package manager
- test commands
- formatter/linter
- type checker
- repository-specific architecture
- generated-file conventions
- deployment commands
- security requirements
