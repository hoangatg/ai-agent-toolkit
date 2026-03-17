---
description: Spec-driven development workflow. Define requirements before code, use structured specs as source of truth.
---

# /spec - Spec-Driven Development

$ARGUMENTS

---

## Task

Define structured specifications before implementation.

### Steps:

1. **Discover** - Understand the feature requirements
2. **Specify** - Write feature spec with goals, non-goals, acceptance criteria
3. **Plan** - Break into technical tasks with clear inputs/outputs
4. **Review** - User validates spec before implementation starts
5. **Implement** - Use agents to build against spec

### Output Files:
- `specs/{feature-name}.md` — Feature specification
- `project-plan.md` — Updated project plan

---

## Usage Examples

```
/spec user-auth           # Spec for user authentication
/spec payment-flow        # Spec for payment integration
```
