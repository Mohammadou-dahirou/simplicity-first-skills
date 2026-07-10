# Failure Patterns

These patterns indicate unnecessary complexity, increased maintenance cost, or poor engineering decisions.

When one or more of these patterns appear, stop and reconsider the implementation.

---

## Premature Abstraction

### Signs

- Creating abstractions before they solve a real problem.
- Designing for hypothetical future requirements.
- Introducing generic components used only once.

### Prefer

Duplicate small amounts of code until a clear abstraction naturally emerges.

---

## Unnecessary Files

### Signs

- Creating a new file when an existing one could be extended.
- Splitting logic for organizational reasons only.
- One-class-one-file without architectural benefit.

### Prefer

Keep related logic together until separation provides clear value.

---

## Service Explosion

### Signs

- Creating a service for simple CRUD logic.
- Thin services that only forward method calls.
- Chains of services calling other services.

### Prefer

Keep straightforward business logic close to where it belongs.

---

## Repository Without Value

### Signs

- Repository methods simply mirror ORM methods.
- Repository adds no business logic.
- Repository exists only because "it's a pattern."

### Prefer

Use the ORM directly unless the repository provides real abstraction or domain value.

---

## Interface Without Multiple Implementations

### Signs

- Interface with only one implementation.
- No foreseeable need for polymorphism.
- Interface created "just in case."

### Prefer

Introduce interfaces only when they solve an actual design problem.

---

## Wrapper Classes

### Signs

- Class exists only to wrap another class.
- Methods simply forward calls.
- No additional behavior.

### Prefer

Use the original component directly.

---

## Configuration Overload

### Signs

- Multiple configuration files for simple behavior.
- Configuration created for features that never change.

### Prefer

Keep configuration minimal.

---

## Clever Code

### Signs

- Difficult to understand.
- Uses advanced language features without benefit.
- Optimized for elegance rather than clarity.

### Prefer

Readable code over clever code.

---

## Large Refactoring

### Signs

- Touching unrelated modules.
- Renaming or restructuring during feature development.
- Mixing cleanup with implementation.

### Prefer

Solve one problem at a time.

---

## Framework Reimplementation

### Signs

- Rewriting features already provided by the framework.
- Ignoring built-in conventions.
- Custom solutions replacing stable framework features.

### Prefer

Trust the framework before building custom infrastructure.

---

## Dependency Creep

### Signs

- Adding a package for a small utility.
- Pulling large libraries for simple tasks.
- Multiple packages solving the same problem.

### Prefer

Keep dependencies to the minimum necessary.

---

## Complexity Cascade

### Signs

One unnecessary abstraction leads to another:

Controller
→ Service
→ Interface
→ Repository
→ DTO
→ Mapper
→ Factory

without clear justification.

### Prefer

Introduce only the layers that solve today's problem.

---

## Warning

Whenever multiple failure patterns appear together, stop implementation and search for a simpler design before continuing.