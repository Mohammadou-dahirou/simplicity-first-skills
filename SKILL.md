---
name: simplicity-first
description: Always prefer the simplest correct solution. Minimize code, abstractions, dependencies, and architectural complexity unless there is a clear, demonstrated benefit.
---

# Simplicity First

Simplicity is the default. Complexity must be justified by evidence, not elegance.

## Activate when
New features, bug fixes, refactoring, architecture decisions, code review, performance work.

## Core mindset
Before writing code, ask:
1. Can I solve this without new code?
2. Can I modify existing code instead of creating new files?
3. Can I remove code instead of adding it?
4. Does the framework already do this?
5. Is this abstraction solving a real problem, or an imagined future one?
6. Is this decision easy to reverse if requirements change?
7. Am I solving today's problem or tomorrow's imagined problem?
8. Do I have enough context to make this decision?

## Evidence First

Never justify complexity using assumptions.

Complexity must be supported by evidence, not intuition.

Acceptable evidence includes:

- Existing project convention
- A documented architectural decision (ADR)
- A measurable performance bottleneck
- A production issue
- A security requirement
- A regulatory or compliance requirement
- An explicit business requirement

Future possibilities are not evidence.

If there isn't enough information to justify a decision, ask for more context before proposing an architecture.

## Rules

- **Prefer existing code.** Modify before creating. A new file needs a clear design reason.
- **Avoid premature abstraction.** Don't create services, repositories, interfaces, factories, strategies, or helpers without a demonstrated need. Future possibilities don't count.
  <!-- DO-NOT-PRUNE -->
  Exception: this doesn't apply to patterns already established as project convention. See [Architectural Exceptions](#architectural-exceptions) before flagging an existing pattern.
  <!-- /DO-NOT-PRUNE -->
- **Trust the framework.** Use built-in features before building custom ones.
- **Minimize change.** Keep changes small and localized. Don't touch unrelated code.
- **Optimize for maintainability.** Readable beats clever.

Every new abstraction is gated by the [Justification Check](#justification-check) below — the single check; don't re-derive it elsewhere.

## Failure Patterns

| Pattern | Signs | Prefer instead |
|---|---|---|
| Premature abstraction | Built for a hypothetical future need; generic component used once | Duplicate until a real abstraction emerges |
| Unnecessary files | New file when an existing one could be extended; split for organization only | Keep related logic together |
| Service explosion | Service wraps simple CRUD; thin pass-through services | Keep business logic close to where it belongs |
| Repository without value | Methods just mirror the ORM | Use the ORM directly |
| Interface, one implementation | No foreseeable polymorphism | Add the interface when a second implementation appears |
| Wrapper classes | Class only forwards calls | Use the original component |
| Configuration overload | Config for behavior that never changes | Keep config minimal |
| Clever code | Optimized for elegance, not clarity | Readable over clever |
| Large refactoring | Touches unrelated modules mid-feature | Solve one problem at a time |
| Framework reimplementation | Rebuilding what the framework already does | Trust the framework |
| Dependency creep | New package for a small utility | Write a small utility when the functionality is simple and self-contained. For security, auth, crypto, standards compliance, parsing, serialization, or protocol implementations, prefer mature libraries. |
| Complexity cascade | Controller → Service → Interface → Repository → DTO → Mapper → Factory, unjustified | Add only the layers today's problem needs |

**Threshold:** 2 or more of these patterns present together in one change → stop and redesign before continuing.

## Anti-Patterns
- **Pattern-driven development** — using a design pattern because it's popular, not because the problem needs it.
- **Architectural drift** — gradually introducing new patterns until the project loses consistency. Consistency beats novelty.

## Architectural Exceptions
<!-- DO-NOT-PRUNE: unique content — do not replace with a cross-reference or delete during redundancy cleanup -->
The rules above target *new, local, undocumented* decisions — not existing project convention. A pattern is exempt when at least one holds:
- Documented as an architectural decision (ADR, README, design doc) for this project.
- Already used consistently (3rd+ occurrence, not the 1st).
- Serves a cross-cutting requirement: transactional integrity (outbox pattern), audit/compliance logging, multi-service boundary, auth isolation.
- Removing it would mean diverging from the codebase's convention, not simplifying it.

When exempt: **follow the convention — don't flag it, don't score it** (see Decision Process below). A one-off "simpler" exception to an established convention is itself a form of inconsistency.

When unsure whether something is a local decision or convention: count existing occurrences before objecting.

Before claiming an Architectural Exception, provide evidence.

Examples:

- existing file names
- similar implementations already in the project
- ADR or design document
- repeated occurrences (3+)

Do not assume a convention exists without verifying it.
<!-- /DO-NOT-PRUNE -->

## Examples

| Scenario | Overengineered | Simplicity First |
|---|---|---|
| Bug in a controller | New service + repository + interface + helper for a one-line fix | Fix the controller; extract a private method only if it aids readability |
| Duplicate validation (2×) | Generic Validator + Validation Service + abstract base class | Keep the duplication until a 3rd occurrence or a clear concept emerges |
| New business rule | Service, Repository, DTO, Mapper, Factory, Interface | Extend the existing domain component |
| Need pagination | Custom pagination | Framework's built-in pagination |
| Suspected slowness | Rewrite the architecture, cache everywhere | Measure before optimizing. Never optimize based on intuition. Caching, parallelism, async, indexing, or architectural changes require measurable evidence of a real bottleneck. |
| Need a helper | `StringHelperFactoryManager` | A private method or existing utility |

## Reversible Decisions

Prefer decisions that are easy to change later.

A small amount of localized duplication is often preferable to an abstraction that becomes difficult to modify.

When two solutions are equally correct, prefer the one that is easier to remove, replace, or extend.

## Naming Smells

Generic names often hide unclear responsibilities.

Classes ending with names such as

- Manager
- Helper
- Utility
- Processor
- Coordinator
- Executor
- Resolver
- Factory
- Wrapper

require explicit justification.

Prefer names that describe a domain concept rather than an implementation role.

## Decision Process

0. Verify that enough context exists. If requirements, architecture, or conventions are unclear, ask questions before proposing a solution.
1. Identify the problem and list ≥2 candidate solutions.
2. For each: check **Architectural Exceptions** first. Exempt → follow it, score = 0, skip step 3.
3. Score the remaining non-exempt options with the table below.
4. Pick the lowest score that meets requirements. Ties go to fewest files/abstractions/dependencies.
5. State why the rejected alternatives were rejected.

### Complexity Score

| Adds | Pts | Reduces | Pts |
|---|---:|---|---:|
| Modify existing file | +1 | Remove duplicated code | −2 |
| New file | +2 | Delete unused code | −5 |
| New class | +3 | Reuse existing component | −3 |
| New interface | +4 | Use framework feature | −3 |
| New abstraction layer | +5 | Simplify architecture | −5 |
| New dependency/package | +10 | | |
| New database table | +8 | | |
| New external service | +15 | | |
| Large refactoring | +10 | | |

**0–5** simple, proceed · **6–15** acceptable, review each addition · **16–30** stop, find a simpler design · **30+** redesign before implementing.

*Example:* adding a query clause to filter (+1) beats a FilterService+Repository+Interface+Factory (~29) unless the latter solves a proven, existing problem.

**Valid reasons to accept complexity:** duplicated logic (3rd+ occurrence), measurable performance issue, architectural constraint, security requirement, explicit project requirement, or an Architectural Exception. Future possibilities are never sufficient.

## Justification Check

Before adding any file, class, interface, service, or dependency:
<!-- DO-NOT-PRUNE -->
- [ ] Is this already an Architectural Exception (3+ occurrences or documented decision)? If yes, follow convention — skip the rest.
<!-- /DO-NOT-PRUNE -->
- [ ] What concrete, present-day problem does it solve?
- [ ] Would duplication or modifying existing code be simpler?
- [ ] Does the framework already provide this?
- [ ] Is the change scoped to only what's needed, with no unrelated refactoring?
- [ ] Would I ask another engineer to simplify this in review?
- [ ] Is the decision easy to reverse?
- [ ] Is every added abstraction supported by concrete evidence?
- [ ] Am I introducing this because of today's requirements rather than hypothetical future needs?

If any question can't be answered clearly, don't add it.

## Output Formats

- **Implementation:** Problem → Existing context (code/framework already available) → Options (≥2, trade-offs) → Decision (+ why alternatives were rejected) → Changes (files touched/created) → Validation (tests, edge cases, risks) → Justification Check result.
- **Code review:** Findings (critical / important / improvement) → Complexity issues found (abstractions, duplication, dependencies) → Simplest fix recommended.
- **Architecture decision:** Context → Constraints → Options → Decision → Trade-offs accepted.

## Code Review Principles

When reviewing code:

- Assume the existing implementation is correct until evidence suggests otherwise.
- Do not recommend refactoring unrelated code.
- Preserve established project conventions.
- Prefer localized improvements over architectural rewrites.
- Explain why a simpler alternative is better before recommending it.

## AI-Specific Guardrails

Do not invent architectural problems.

Do not recommend abstractions solely because they are considered best practices.

Do not rewrite working code to match personal style.

Do not introduce new layers without evidence.

If multiple solutions are valid, recommend the simplest one and explain why.

## References

KISS, YAGNI, Occam's Razor — prefer the simplest solution that fits the facts; avoid speculative work. *Refactoring* (Fowler): small, purposeful changes. *Clean Code* (Martin): meaningful names, small functions — not a license for unnecessary abstraction. *Domain-Driven Design* (Evans): use domain concepts only where they add real value. Convention over configuration (Laravel/Rails/Django/FastAPI): trust framework conventions before custom infrastructure. *Simple Made Easy* (Hickey): complexity comes from unnecessary interdependence. *The Pragmatic Programmer* (Thomas/Hunt): avoid duplication, keep decisions reversible.

Review this skill when framework recommendations change, new practices emerge, or new failure patterns are discovered — based on evidence, not trends.