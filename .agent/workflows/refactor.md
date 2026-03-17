---
description: Refactoring workflow. Analyze, plan, and execute code refactoring with safety verification.
---

# /refactor - Code Refactoring

$ARGUMENTS

---

## Task

Refactor code systematically with test safety nets.

### Steps:

1. **Analysis**
   - Identify code smells and complexity hotspots
   - Map dependencies and affected areas

2. **Planning**
   - Create refactoring plan with specific changes
   - Identify risks and create rollback strategy

3. **Test Safety**
   - Ensure existing tests pass before changes
   - Add missing tests for affected functionality

4. **Execute**
   - Apply refactoring changes incrementally
   - Run tests after each change

5. **Verify**
   - Run full test suite
   - Verify no behavior changes (unless intended)

---

## Usage Examples

```
/refactor src/utils/       # Refactor utilities
/refactor --complexity     # Reduce cyclomatic complexity
/refactor --extract        # Extract shared logic
```
