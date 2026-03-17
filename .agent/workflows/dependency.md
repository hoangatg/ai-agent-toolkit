---
description: Dependency audit and update workflow. Check outdated packages, security vulnerabilities, and upgrade safely.
---

# /dependency - Dependency Audit

$ARGUMENTS

---

## Task

Audit and update project dependencies safely.

### Steps:

1. **Audit** - Check for outdated packages and vulnerabilities
2. **Prioritize** - Security fixes first, then major updates
3. **Update** - Apply updates with test verification
4. **Verify** - Run full test suite after updates

---

## Usage Examples

```
/dependency                # Full dependency audit
/dependency --security     # Security vulnerabilities only
/dependency --major        # Check major version updates
```
