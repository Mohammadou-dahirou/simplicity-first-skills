# Examples

This document illustrates how the Simplicity First principles should be applied in common engineering situations.

---

# Example 1 — Fix a Bug

## ❌ Overengineered

Bug found in a controller.

Solution:

- Create a new service.
- Create a repository.
- Create an interface.
- Move the logic.
- Add a helper.

Result:

Five new files for a one-line fix.

---

## ✅ Simplicity First

Modify the existing controller.

Extract a private method only if readability improves.

No additional abstractions.

Reason:

The problem is local.
No reusable component has emerged.

---

# Example 2 — Duplicate Logic

The same validation appears twice.

## ❌ Overengineered

Immediately create:

- Generic Validator
- Validation Service
- Abstract Base Class

---

## ✅ Simplicity First

Keep the duplication.

Wait until a third occurrence appears or a clear reusable concept emerges.

Reason:

Small duplication is cheaper than unnecessary abstraction.

---

# Example 3 — New Feature

A new business rule must be added.

## ❌ Overengineered

Create:

- Service
- Repository
- DTO
- Mapper
- Factory
- Interface

---

## ✅ Simplicity First

Extend the existing domain component.

Only introduce a new abstraction if the responsibility clearly changes.

---

# Example 4 — Framework Feature

Need pagination.

## ❌ Overengineered

Implement custom pagination.

---

## ✅ Simplicity First

Use the framework's built-in pagination.

Reason:

Framework code is tested, documented and maintained.

---

# Example 5 — Performance

A developer suspects the code is slow.

## ❌ Overengineered

Rewrite the architecture.

Introduce caching everywhere.

---

## ✅ Simplicity First

Measure first.

Identify the bottleneck.

Optimize only what is proven to be slow.

---

# Example 6 — New Class

A helper method is needed.

## ❌ Overengineered

Create:

StringHelperFactoryManager

---

## ✅ Simplicity First

Use a private method or an existing utility.

Only create a class when it has a clear responsibility.

---

# General Rule

When two solutions solve the same problem:

Choose the one that introduces the least complexity.