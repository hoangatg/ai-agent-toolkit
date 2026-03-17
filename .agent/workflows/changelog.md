---
description: Changelog generation workflow. Generate changelog from git commit history.
---

# /changelog - Changelog Generation

$ARGUMENTS

---

## Task

Generate an organized changelog from git history.

### Steps:

1. **Scan** - Analyze git commits since last release
2. **Categorize** - Group by type (Features, Fixes, Breaking Changes)
3. **Format** - Generate markdown following Keep a Changelog format
4. **Update** - Append to CHANGELOG.md

---

## Usage Examples

```
/changelog                 # Generate since last tag
/changelog v2.0.0..HEAD    # Generate for specific range
```
