# References

This document lists the sources, principles and engineering practices that inspired the Simplicity First skill.

The goal is not to copy external rules blindly, but to extract proven engineering principles and adapt them for AI-assisted development.

---

# Core Principles

## KISS — Keep It Simple, Stupid

Principle:

> Prefer simple solutions over complex solutions.

Applied in this skill:

- Avoid unnecessary abstraction.
- Prefer readable code.
- Reduce cognitive load.

Reference:

- https://en.wikipedia.org/wiki/KISS_principle

---

## YAGNI — You Aren't Gonna Need It

Principle:

> Do not implement functionality until it is actually needed.

Applied in this skill:

- Avoid future-proofing without evidence.
- Avoid speculative architecture.
- Solve current requirements first.

Reference:

- Extreme Programming practices
- https://www.extremeprogramming.org/rules/consider.html

---

## Occam's Razor

Principle:

> Prefer the simplest explanation that fits the facts.

Applied in this skill:

- Choose the simplest valid implementation.
- Avoid unnecessary assumptions.

---

# Software Design References

## Refactoring

Inspired by:

Martin Fowler — Refactoring

Key ideas:

- Improve design through small changes.
- Keep behavior stable.
- Refactor with a clear purpose.

Reference:

- https://martinfowler.com/books/refactoring.html

---

## Clean Code Principles

Inspired by:

Robert C. Martin

Applied selectively:

- Meaningful names.
- Small focused functions.
- Readability.

Note:

Clean Code principles should not become a reason to create unnecessary abstractions.

---

## Domain-Driven Design

Inspired by:

Eric Evans — Domain-Driven Design

Applied selectively:

- Use domain concepts when they provide real value.
- Avoid applying DDD patterns mechanically.

Reference:

- https://www.domainlanguage.com/ddd/

---

# Framework Philosophy

## Convention Over Configuration

Inspired by modern frameworks:

- Laravel
- Rails
- Django
- FastAPI ecosystem

Principle:

Use existing framework conventions before creating custom infrastructure.

---

# Engineering Practices

## Simple Made Easy

Inspired by:

Rich Hickey

Principle:

Complexity comes from unnecessary interdependence.

Applied in this skill:

- Reduce coupling.
- Prefer independent simple components.

---

## The Pragmatic Programmer

Inspired by:

David Thomas and Andrew Hunt

Applied principles:

- Avoid duplication.
- Keep knowledge local.
- Make reversible decisions when possible.

---

# AI-Assisted Development Context

This skill also addresses common AI coding assistant behaviors:

- Over-generation of code.
- Excessive abstraction.
- Unnecessary architecture.
- Adding dependencies without justification.

The goal is to make AI agents behave closer to experienced software engineers.

---

# Maintenance Principle

References should be reviewed when:

- Framework recommendations change.
- New engineering practices emerge.
- New failure patterns are discovered.

The skill should evolve based on evidence, not trends.