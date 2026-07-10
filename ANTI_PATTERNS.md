# Anti-Patterns

The following practices should be avoided unless there is a clear and justified reason.

---

## Pattern-Driven Development

Applying design patterns because they are popular.

Not because the problem requires them.

---

## Future-Proof Programming

Building for hypothetical future requirements.

Prefer solving today's problem.

---

## Service Everywhere

Creating a service for every piece of logic.

Services should represent meaningful business capabilities.

---

## Repository Everywhere

Wrapping the ORM without adding value.

If the repository only forwards ORM calls, remove it.

---

## Interface Everywhere

Creating interfaces with a single implementation and no foreseeable variation.

---

## One Class Per Tiny Action

Avoid classes whose only purpose is forwarding one method call.

---

## Generic Helpers

Creating Utility or Helper classes that become dumping grounds for unrelated logic.

---

## Clever Code

Code that impresses more than it explains.

Prefer clarity over cleverness.

---

## Large Refactoring During Feature Work

Do not redesign the application while implementing an unrelated feature.

One Pull Request should solve one problem.

---

## Framework Reinvention

Replacing stable framework features with custom implementations.

Trust the framework.

---

## Dependency Addiction

Adding packages for trivial functionality.

Every dependency increases maintenance cost.

---

## Architectural Drift

Gradually introducing new patterns until the project loses consistency.

Consistency is more valuable than novelty.

---

## Complexity Cascade

One unnecessary abstraction often leads to several more.

Question every additional layer.

---

# Final Reminder

Every new abstraction, dependency, file or architectural layer must justify its existence.

If it cannot, it should not exist.