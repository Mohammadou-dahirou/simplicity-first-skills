# Decision Matrix

Before implementing a solution, evaluate the available options.

Never assume the first solution is the best one.

---

# Decision Process

Follow these steps before writing code:

1. Identify the problem.
2. List at least two possible solutions.
3. Compare them using the criteria below.
4. Select the simplest solution that satisfies the requirements.
5. Justify why more complex alternatives were rejected.

---

# Evaluation Criteria

Evaluate each solution using the following questions.

## Simplicity

- How many new files are required?
- How many new concepts are introduced?
- Does the solution increase cognitive load?

Prefer the solution with the lowest complexity.

---

## Reuse

- Can existing code be reused?
- Can an existing component be extended?
- Does the framework already solve this problem?

Prefer reuse over creation.

---

## Maintainability

- Will another developer understand this quickly?
- Is debugging straightforward?
- Is future modification simple?

Prefer maintainability over flexibility.

---

## Scope

- Does the solution touch unrelated modules?
- Does it require widespread changes?

Prefer localized changes.

---

## Architecture

- Does the solution preserve the current architecture?
- Does it introduce unnecessary layers?

Avoid architectural drift.

---

## Performance

- Is the solution efficient enough?
- Is optimization actually required?
- Is complexity introduced solely for performance?

Only optimize when justified by evidence.

---

## Dependencies

- Does this require a new dependency?
- Can the same result be achieved without one?

Every dependency has a maintenance cost.

---

# Tie Breaker

When multiple solutions satisfy the requirements:

Choose the one that:

- introduces the fewest abstractions;
- creates the fewest files;
- requires the least code;
- is easiest to understand;
- has the lowest maintenance cost.

---

# Complexity Escalation

Only increase complexity when there is clear evidence.

Examples include:

- duplicated logic appearing multiple times;
- measurable performance issues;
- architectural constraints;
- security requirements;
- explicit project requirements.

Future possibilities are not sufficient justification.

---

# Final Validation

Before implementation, ask:

- Why is this the simplest correct solution?
- What alternatives were considered?
- Why were they rejected?
- What complexity was intentionally avoided?

If these questions cannot be answered clearly, reconsider the design.