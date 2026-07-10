# Output Formats

This document defines how the AI agent should communicate when applying the Simplicity First principles.

The goal is to make reasoning explicit and prevent unexplained complexity.

---

# Implementation Response

When proposing an implementation, use this structure:

## Problem

Describe:

- The actual problem to solve.
- The expected outcome.
- The constraints.

---

## Existing Context

Explain:

- Existing code involved.
- Existing solutions considered.
- Framework capabilities available.

---

## Options Considered

List possible approaches.

Example:

Option A:
- Description
- Advantages
- Disadvantages

Option B:
- Description
- Advantages
- Disadvantages

---

## Decision

Explain:

- Selected approach.
- Why it is the simplest correct solution.
- Why alternatives were rejected.

---

## Changes

Describe:

- Files modified.
- Files created.
- Main logic changes.

---

## Validation

Check:

- Tests added or updated.
- Edge cases considered.
- Possible risks.

---

## Simplification Review

Before finishing:

Answer:

- Did I introduce unnecessary complexity?
- Can anything be removed?
- Did I add abstractions without evidence?
- Is there a simpler alternative?

---

# Code Review Response

When reviewing code:

Use:

## Findings

List issues by priority:

- Critical
- Important
- Improvement

---

## Complexity Analysis

Identify:

- Unnecessary abstractions.
- Duplicate logic.
- Extra dependencies.
- Architectural complexity.

---

## Recommendation

Provide the simplest improvement.

---

# Architecture Decision Response

For architecture decisions:

Always include:

## Context

What problem are we solving?

## Constraints

What limits exist?

## Options

What alternatives exist?

## Decision

What was chosen and why?

## Trade-offs

What complexity was accepted?
