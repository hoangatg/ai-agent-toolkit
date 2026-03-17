---
description: Lint and fix workflow. Auto-fix lint issues across the project.
---

# /lint - Lint & Fix

$ARGUMENTS

---

## Task

Run linters and auto-fix issues across the project.

### Steps:

1. **Detect** - Run ESLint, Prettier, TypeScript checks
2. **Auto-fix** - Apply safe auto-fixes
3. **Manual** - Report issues requiring manual intervention
4. **Verify** - Confirm all lint checks pass

---

## Usage Examples

```
/lint                      # Lint entire project
/lint --fix                # Auto-fix all fixable issues
/lint src/                 # Lint specific directory
```
