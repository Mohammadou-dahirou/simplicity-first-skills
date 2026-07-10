---
name: simplicity-first
description: Always prefer the simplest correct solution. Minimize code, abstractions, dependencies, and architectural complexity unless there is a clear, demonstrated benefit.
---

# Simplicity First

## Purpose

This skill prevents unnecessary complexity during software engineering tasks.

Its goal is to encourage solutions that are simple, maintainable, readable, and consistent with the existing codebase.

Simplicity is the default choice. Complexity must always be justified.

---

## Activate when

Use this skill for every engineering task involving:

- New features
- Bug fixes
- Refactoring
- Architecture decisions
- Code review
- Performance improvements

---

## Core mindset

Before writing code, ask:

1. Can I solve this without writing new code?
2. Can I modify existing code instead of creating new files?
3. Can I remove code instead of adding code?
4. Does the framework already provide this capability?
5. Is this abstraction solving a real problem or an imagined future one?

If the answer is unclear, prefer the simpler solution. Refer to [EXAMPLES.md](EXAMPLES.md) for concrete examples.

---

## Rules

### Prefer existing code

Modify existing components before creating new ones.

Avoid introducing new files unless they clearly improve the design. For patterns to avoid, see [ANTI_PATTERNS.md](ANTI_PATTERNS.md).

---

### Avoid premature abstraction

Do not create:

- Services
- Repositories
- Interfaces
- Factories
- Strategies
- Helpers

unless there is a demonstrated need.

Future possibilities are not sufficient justification. See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md) for signs of over-engineering.

---

### Trust the framework

Use the framework's built-in features before building custom solutions.

Avoid reinventing existing capabilities.

---

### Minimize change

Keep changes as small and localized as possible.

Avoid touching unrelated code.

---

### Optimize for maintainability

Prefer code that another developer can understand quickly.

Readable code is more valuable than clever code.

---

### Complexity requires justification

Every new abstraction should answer:

- What problem does it solve?
- Why is the existing code insufficient?
- What maintenance cost does it introduce?
- Is there a simpler alternative?

If these questions cannot be answered clearly, do not introduce the abstraction. Compare options using [DECISION_MATRIX.md](DECISION_MATRIX.md), evaluate them with [COMPLEXITY_SCORE.md](COMPLEXITY_SCORE.md), and follow the templates in [OUTPUT_FORMATS.md](OUTPUT_FORMATS.md).

---

## Self-review

Before finishing, verify:

- Is this the simplest solution?
- Did I add unnecessary files?
- Did I introduce unnecessary abstractions?
- Can any code be removed?
- Can I rely more on the framework?
- Would I make the same decision if I had to maintain this code for five years?

If not, simplify before completing the task. Use [CHECKLIST.md](CHECKLIST.md) for a comprehensive review.

---

## Supporting Resources

- [CHECKLIST.md](CHECKLIST.md) — Review checklist for finalizing implementation
- [EXAMPLES.md](EXAMPLES.md) — Comparison of simple vs over-engineered solutions
- [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md) — Common mistakes to avoid
- [ANTI_PATTERNS.md](ANTI_PATTERNS.md) — Coding anti-patterns
- [DECISION_MATRIX.md](DECISION_MATRIX.md) — Framework for comparing options
- [COMPLEXITY_SCORE.md](COMPLEXITY_SCORE.md) — Scoring system to evaluate code changes
- [OUTPUT_FORMATS.md](OUTPUT_FORMATS.md) — Standardized templates for agent responses
- [REFERENCE.md](REFERENCE.md) — External sources and foundational principles
- [CHANGELOG.md](CHANGELOG.md) — Project history and updates
- [LICENSE.txt](LICENSE.txt) — MIT License details