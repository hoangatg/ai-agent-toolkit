---
description: Accessibility audit workflow. WCAG compliance check and fix suggestions.
---

# /accessibility - Accessibility Audit

$ARGUMENTS

---

## Task

Audit and improve application accessibility.

### Steps:

1. **Scan** - Run automated accessibility checks
2. **Audit** - Use `accessibility-expert` agent for manual review
3. **Report** - List violations by WCAG level (A, AA, AAA)
4. **Fix** - Apply fixes for critical violations
5. **Verify** - Re-test with screen reader and keyboard

---

## Usage Examples

```
/accessibility             # Full a11y audit
/accessibility --wcag-aa   # WCAG AA compliance check
/accessibility src/components/ # Audit specific components
```
