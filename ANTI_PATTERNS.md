# Anti-Patterns

The following practices should be avoided unless there is a clear and justified reason.

---

## Pattern-Driven Development

Applying design patterns because they are popular.

Not because the problem requires them.

---

## Future-Proof Programming

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#premature-abstraction).

---

## Service Everywhere

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#service-explosion).

---

## Repository Everywhere

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#repository-without-value).

---

## Interface Everywhere

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#interface-without-multiple-implementations).

---

## One Class Per Tiny Action

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#unnecessary-files).

---

## Generic Helpers

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#unnecessary-files) and [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#wrapper-classes).

---

## Clever Code

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#clever-code).

---

## Large Refactoring During Feature Work

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#large-refactoring).

---

## Framework Reinvention

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#framework-reimplementation).

---

## Dependency Addiction

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#dependency-creep).

---

## Architectural Drift

Gradually introducing new patterns until the project loses consistency.

Consistency is more valuable than novelty.

---

## Complexity Cascade

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#complexity-cascade).

---

<!-- DO-NOT-PRUNE: this section is unique content, not a restatement of anything in FAILURE_PATTERNS.md. Do not replace with a cross-reference or delete during redundancy cleanup. -->

# Architectural Exceptions

These anti-patterns apply to **new, local, undocumented** decisions made during a single task.

They do **not** apply when a pattern is already an established convention of the project — even if it looks like "Service Everywhere" or "Repository Everywhere" from the outside.

A pattern is exempt when at least one of these holds:

- It is documented as an architectural decision (ADR, README, design doc) for this project.
- It is used consistently across the existing codebase (this would be the 3rd+ occurrence, not the 1st).
- It exists to satisfy a cross-cutting requirement: transactional integrity (e.g. outbox pattern), audit/compliance logging, multi-service boundary, or authentication/authorization isolation.
- Removing it would mean diverging from the codebase's current convention rather than simplifying it.

In these cases, the correct action is to **follow the existing pattern**, not to flag or remove it. Introducing a one-off simpler exception to an established convention is itself a form of unnecessary complexity (inconsistency).

When unsure whether something is a local decision or an established convention: check how many other places in the codebase already do it this way before objecting.

<!-- /DO-NOT-PRUNE -->

---

# Final Reminder

See [FAILURE_PATTERNS.md](FAILURE_PATTERNS.md#warning).

If a pattern already exists as project convention, don't re-litigate it — follow it.