---
description: Component creation workflow. Design, build, and test reusable UI components.
---

# /component - Component Creation

$ARGUMENTS

---

## Task

Create a polished, reusable UI component with tests.

### Steps:

1. **Design**
   - Define component API (props, events, slots)
   - Plan variants, sizes, and states

2. **Build**
   - Use `frontend-specialist` agent to implement
   - Follow design system patterns
   - Ensure accessibility (ARIA, keyboard nav)

3. **Style**
   - Apply design tokens and theming
   - Handle responsive behavior
   - Add animations and transitions

4. **Test**
   - Use `test-engineer` agent for tests
   - Unit tests for logic, interaction tests for UX

5. **Document**
   - Create usage examples
   - Document props and variants

---

## Usage Examples

```
/component Button          # Create Button component
/component DataTable       # Create DataTable component
/component Modal --a11y    # Create accessible Modal
```
