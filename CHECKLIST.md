# Simplicity Checklist

Complete this checklist before finalizing any implementation.

---

# Eliminate Before Adding

- [ ] Can the problem be solved without writing new code?
- [ ] Can existing code be modified instead?
- [ ] Can existing functionality be reused?
- [ ] Can code be removed instead of added?

If any answer is **Yes**, prefer that option.

---

# Framework First

- [ ] Does the framework already provide this feature?
- [ ] Am I reimplementing existing functionality?
- [ ] Am I introducing a dependency unnecessarily?

Prefer built-in solutions whenever reasonable.

---

# Abstraction Check

For every new abstraction (service, repository, interface, helper, etc.) ask:

<!-- DO-NOT-PRUNE -->
- [ ] Is this already an established convention in this codebase (3+ existing occurrences) or a documented architectural decision? If yes, this is an Architectural Exception (see ANTI_PATTERNS.md) — follow the convention, skip the rest of this check.
<!-- /DO-NOT-PRUNE -->
- [ ] What concrete problem does it solve?
- [ ] Is this problem present today?
- [ ] Is there evidence this abstraction is needed?
- [ ] Would duplication be simpler?

If these questions cannot be answered clearly, do not introduce the abstraction.

---

# New Files

For every new file:

- [ ] Why can't this logic live in an existing file?
- [ ] Does this file have a single responsibility?
- [ ] Will this file likely remain useful in six months?

Avoid creating files for convenience alone.

---

# Scope Control

- [ ] Are changes limited to the smallest possible area?
- [ ] Did I avoid unrelated refactoring?
- [ ] Did I preserve the existing architecture?

---

# Readability

- [ ] Can another developer understand this quickly?
- [ ] Are names clear?
- [ ] Is the code straightforward?

Readable code is preferred over clever code.

---

# Maintenance Cost

Every new element increases maintenance.

Before adding:

- [ ] New class
- [ ] New interface
- [ ] New dependency
- [ ] New configuration
- [ ] New database table
- [ ] New package

Ask:

> Is the long-term maintenance cost justified?

---

# Final Question

Before completing the task, answer honestly:

> If I were reviewing this Pull Request from another engineer, would I ask them to simplify it?

If the answer is **Yes**, simplify first.