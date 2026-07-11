# Changelog

All notable changes to this project will be documented in this file.

This project follows the principles of [Keep a Changelog](https://keepachangelog.com/) and uses semantic versioning.

# [1.1.1] - 2026-07-11

## Fixed

- Restored "Architectural Exceptions" section in `ANTI_PATTERNS.md` and its cross-references in `SKILL.md` / `CHECKLIST.md`, accidentally deleted during the 1.1.0 redundancy-reduction pass. This section is unique content (not present in `FAILURE_PATTERNS.md`) and is now wrapped in `<!-- DO-NOT-PRUNE -->` markers to prevent recurrence.
- Renamed this changelog entry's predecessor to avoid a duplicate `[1.1.0]` version number (redundancy-reduction changes and architectural-exceptions changes were both tagged 1.1.0).

# [1.1.0] - 2026-07-11

## Changed

### Redundancy Reduction

- Trimmed redundant exposition and duplicate rules across multiple Markdown files while keeping files and unique content intact:
  - `SKILL.md`: Trimmed `Self-review` checklist questions to point to `CHECKLIST.md`.
  - `ANTI_PATTERNS.md`: Trimmed all 11 restated anti-patterns to pointers to `FAILURE_PATTERNS.md`, keeping unique `Pattern-Driven Development` and `Architectural Drift` sections.
  - `EXAMPLES.md`: Trimmed `General Rule` section to point to core mindset in `SKILL.md`.
  - `COMPLEXITY_SCORE.md`: Trimmed duplicate `Complexity Review Questions` list to point to `CHECKLIST.md`.
  - `README.md`: Trimmed `Philosophy`, `Example`, and `Core Question` sections to point to respective files, and updated the `ANTI_PATTERNS.md` description under Included Resources.

---

# [1.0.0] - 2026-07-09

## Added

### Core Skill

- Added `SKILL.md` defining the Simplicity First engineering philosophy.
- Added activation rules for AI coding agents.
- Added principles for minimizing unnecessary complexity.

### Decision Framework

- Added `DECISION_MATRIX.md`.
- Added a structured approach for comparing implementation options.
- Added criteria based on:
  - Simplicity
  - Reuse
  - Maintainability
  - Scope
  - Architecture
  - Performance
  - Dependencies

### Complexity Control

- Added `COMPLEXITY_SCORE.md`.
- Added a scoring system to evaluate complexity introduced by:
  - New files
  - New classes
  - New abstractions
  - Dependencies
  - Architectural changes

### Quality Controls

- Added `CHECKLIST.md`.
- Added final validation questions before completing implementation.

### Failure Detection

- Added `FAILURE_PATTERNS.md`.
- Added detection rules for:
  - Premature abstraction
  - Service explosion
  - Repository without value
  - Interface overuse
  - Dependency creep
  - Complexity cascade

### Examples and Anti-Patterns

- Added `EXAMPLES.md`.
- Added `ANTI_PATTERNS.md`.
- Added practical examples showing simple versus over-engineered solutions.

### Agent Communication

- Added `OUTPUT_FORMATS.md`.
- Added response structures for:
  - Implementation proposals
  - Code reviews
  - Architecture decisions

### Documentation

- Added initial `README.md`.
- Added project documentation structure.

---

## Philosophy

The first release establishes the core principle:

> The simplest correct solution should be the default solution. Complexity must be justified.

---

## Future Plans

Planned improvements:

- Add more real-world engineering scenarios.
- Add automated skill evaluation tests.
- Add framework-specific integrations.
- Add project-specific extensions for Laravel, FastAPI, PostgreSQL and other stacks.