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

See core rules and mindset in [SKILL.md](SKILL.md#rules).

---

# Installation

Copy `SKILL.md` into your AI agent skills directory.

Example:

```
.skills/
└── simplicity-first/
    └── SKILL.md
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

# What's inside SKILL.md

A single self-contained file covering:

- **Core rules and mindset** — When to activate, 5 questions to ask before writing code
- **Failure patterns** — Premature abstraction, service explosion, repository without value, interface without purpose, dependency creep, large refactoring
- **Anti-patterns and architectural exceptions** — Pattern-driven development, architectural drift, and when established conventions are exempt
- **Examples** — Simple vs over-engineered approaches for common scenarios
- **Decision matrix** — Framework for comparing solutions by complexity, maintenance, reuse, performance, dependencies, and architecture impact
- **Complexity score** — Scoring system to evaluate and limit complexity introduced by changes
- **Checklist** — Final review before completing any implementation
- **Output formats** — Standardized templates for implementation proposals, code reviews, and architecture decisions
- **References** — KISS, YAGNI, Occam's Razor, and other foundational principles

---

# Example

See the [Examples](SKILL.md#examples) and [Complexity Score](SKILL.md#scoring-example) sections in SKILL.md.

---

# Core Question

See [core mindset](SKILL.md#core-mindset) in SKILL.md.

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