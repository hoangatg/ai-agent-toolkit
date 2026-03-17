---
description: Release management workflow. Version bump, changelog generation, tagging, and deployment.
---

# /release - Release Management

$ARGUMENTS

---

## Task

Coordinate a software release with quality gates.

### Steps:

1. **Pre-check** - Ensure all tests pass, no blocking issues
2. **Version** - Bump version (semver: major/minor/patch)
3. **Changelog** - Generate changelog from commits
4. **Tag** - Create git tag and release branch
5. **Deploy** - Trigger deployment pipeline

---

## Usage Examples

```
/release patch             # Patch release (bug fixes)
/release minor             # Minor release (new features)
/release major             # Major release (breaking changes)
```
