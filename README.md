# Simplicity First Skill

A software engineering skill for AI coding agents that prevents unnecessary complexity and promotes simple, maintainable solutions.

Designed for:
- Antigravity
- Cursor
- Claude Code
- Other AI coding assistants supporting skills/instructions

---

## Why this skill?

AI coding assistants are very good at generating solutions.

However, they often introduce unnecessary complexity:

- Too many abstractions
- Unnecessary services
- Premature design patterns
- Extra dependencies
- Large refactoring
- Over-engineered architectures

The goal of Simplicity First is to teach AI agents a senior engineering habit:

> Build the simplest correct solution first. Complexity must be justified.

---

# Philosophy

Simplicity First follows these principles:

- Prefer existing code over new code.
- Prefer deletion over addition.
- Prefer framework features over custom implementations.
- Prefer explicit solutions over unnecessary abstractions.
- Optimize for maintainability, not cleverness.
- Solve today's problem, not imaginary future problems.

---

# Installation

Copy the `simplicity-first` folder into your AI agent skills directory.

Example:

```
.skills/
└── simplicity-first/
    ├── SKILL.md
    ├── CHECKLIST.md
    ├── FAILURE_PATTERNS.md
    ├── DECISION_MATRIX.md
    ├── EXAMPLES.md
    ├── ANTI_PATTERNS.md
    ├── COMPLEXITY_SCORE.md
    ├── OUTPUT_FORMATS.md
    ├── REFERENCE.md
    ├── CHANGELOG.md
    └── LICENSE.txt
```

---

# How it works

Before implementing a solution, the agent should:

1. Understand the problem.
2. Check existing code.
3. Evaluate simpler alternatives.
4. Avoid unnecessary abstractions.
5. Implement the smallest valid solution.
6. Review the result for unnecessary complexity.

---

# Included Resources

## SKILL.md

Defines the core behavior and activation rules.

## CHECKLIST.md

A final review checklist to detect unnecessary complexity.

## FAILURE_PATTERNS.md

Common complexity mistakes:

- Premature abstraction
- Service explosion
- Repository without value
- Interface without purpose
- Dependency creep
- Large refactoring

## DECISION_MATRIX.md

A framework for comparing solutions based on:

- Complexity
- Maintenance
- Reuse
- Performance
- Dependencies
- Architecture impact

## EXAMPLES.md

Real examples showing simple versus over-engineered approaches.

## ANTI_PATTERNS.md

Patterns that frequently create unnecessary complexity.

## COMPLEXITY_SCORE.md

A scoring system to evaluate and limit complexity introduced by new changes.

## OUTPUT_FORMATS.md

Standardized communication formats for implementation, code review, and architecture decisions.

## REFERENCE.md

Lists sources, principles (KISS, YAGNI, Occam's Razor), and engineering practices that inspired this skill.

## CHANGELOG.md

Chronological log of changes to the project.

## LICENSE.txt

MIT License details.

---

# Example

## Problem

Add filtering to a list of users.

## Over-engineered solution

Create:

- FilterService
- FilterRepository
- FilterInterface
- FilterFactory

## Simplicity First solution

Add the filter where the existing query logic already exists.

Introduce abstraction only when real complexity appears.

---

# Core Question

Before adding code:

> Is this the simplest solution that solves the real problem?

If not, simplify.

---

# Contributing

Contributions should follow the same philosophy:

- Small changes.
- Clear purpose.
- No unnecessary abstractions.
- Evidence-based improvements.

---

# License

MIT License