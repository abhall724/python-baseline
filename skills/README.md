# Agent Skills

These skills are intentionally modular. The root `AGENTS.md` contains only
high-value, always-relevant constraints.

Use a skill when the task matches its workflow.

## Included Skills

- `investigate` — understand unfamiliar behavior before changing code
- `file-creation` — create, modify, validate, and organize repository files
- `python` — Python-specific implementation and dependency practices
- `testing` — establish and verify test oracles
- `cleanup` — remove LLM-generated boilerplate safely
- `final-review` — final diff/status/scope verification

## Design Principle

Do not move generic repository facts into skills merely to make the root file
smaller. Skills are for procedures and specialized workflows.

Repository-specific facts belong in the repository's documentation.
Mechanical rules belong in project configuration such as `pyproject.toml`.
