# File Creation

Use this skill whenever creating, moving, replacing, or substantially modifying
repository files.

## Core Principle

A file is an artifact with an owner, source of truth, consumers, and validation
requirements.

Do not create a file merely because it is convenient.

## 1. Discover

Before creating a file, search for:

- similar filenames
- similar implementations
- neighboring modules
- consumers
- tests
- templates
- schemas
- generators
- configuration
- documentation

## 2. Determine Ownership

Classify the file:

- source
- generated output
- configuration
- test
- fixture
- documentation
- script
- experiment
- user-facing artifact
- temporary output

If generated, identify the source of truth before editing.

## 3. Determine Location

Follow the repository's existing organization.

Do not create a new top-level directory without a concrete reason.

Mirror nearby patterns when they represent an intentional convention.

## 4. Determine Format

Inspect neighboring files and project configuration.

Use existing:

- formatters
- schemas
- serializers
- generators
- naming conventions
- package conventions

Do not invent a new format when an established one exists.

## 5. Create the Smallest Complete Artifact

Avoid:

- speculative sections
- placeholder abstractions
- generic helper modules
- unused imports
- future-facing configuration
- boilerplate copied from unrelated projects

Do not add documentation or comments that merely restate obvious code.

## 6. Validate

Validate both:

- syntax/format
- integration with actual consumers

A file compiling or parsing successfully is not sufficient if it is supposed
to participate in an application, test suite, build, or generation pipeline.

## 7. Inspect

After creation:

- inspect `git diff`
- inspect `git status`
- search for references
- check whether expected consumers import/use it
- check for accidental generated artifacts
- check for unrelated formatter changes

## 8. Report

State:

- files created
- files modified
- validation actually performed
- anything that remains unverified
