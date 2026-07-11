# Complexity Score

The Complexity Score helps evaluate whether a proposed solution introduces unnecessary complexity.

The objective is not to avoid all complexity.

The objective is to ensure that every complexity has a reason.

---

# Scoring Rules

## Adding Complexity

| Change | Score |
|---|---:|
| Modify existing file | +1 |
| Create new file | +2 |
| Create new class | +3 |
| Create new interface | +4 |
| Create new abstraction layer | +5 |
| Add new dependency | +10 |
| Add new package/library | +10 |
| Add database table | +8 |
| Add external service | +15 |
| Large refactoring | +10 |

---

# Reducing Complexity

| Improvement | Score |
|---|---:|
| Remove duplicated code | -2 |
| Delete unused code | -5 |
| Reuse existing component | -3 |
| Use framework feature | -3 |
| Simplify architecture | -5 |

---

# Interpretation

## 0-5 : Simple

The solution introduces minimal complexity.

Proceed.

---

## 6-15 : Acceptable

Review the added complexity.

Ensure every addition is justified.

---

## 16-30 : High Complexity

Stop and reconsider.

Look for simpler alternatives.

---

## 30+ : Excessive Complexity

The solution is probably over-engineered.

Redesign before implementation.

---

# Complexity Review Questions

Before accepting a solution, verify it against the questions in [CHECKLIST.md](CHECKLIST.md).

---

# Example

## Feature

Add user filtering.

### Option A

Modify existing query.

Score:

```
Modify existing file: +1
Total: 1
```

### Option B

Create:

- FilterService
- FilterRepository
- FilterInterface
- FilterFactory

Score:

```
New files: +8
New classes: +12
New interface: +4
New abstraction: +5

Total: 29
```

Decision:

Choose Option A unless Option B solves a proven existing problem.