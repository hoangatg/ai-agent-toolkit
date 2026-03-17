---
name: create-pr
description: Clean pull request creation with structured descriptions, changelogs, and review checklists. Use when packaging work into a reviewable, mergeable pull request.
---

# Create PR

> Package your work so reviewers say "yes" quickly.

---

## 1. Before Creating PR

### Pre-PR Checklist

| Check | Action |
|-------|--------|
| **Tests pass** | Run full test suite locally |
| **Lint clean** | No warnings or errors |
| **Self-review** | Read your own diff first |
| **Small scope** | One feature/fix per PR |
| **Branch updated** | Rebase on latest main |
| **No debug code** | Remove console.logs, TODO hacks |

---

## 2. PR Title

### Format

```
<type>(<scope>): <short description>
```

### Examples

| Good ✅ | Bad ❌ |
|--------|-------|
| `feat(auth): add JWT refresh token flow` | `update auth` |
| `fix(api): handle null response in user endpoint` | `fix bug` |
| `refactor(db): migrate to connection pooling` | `changes` |

---

## 3. PR Description Template

```markdown
## Summary
One paragraph explaining what this PR does and why.

## Changes
- Added X to handle Y
- Refactored Z for better performance
- Fixed bug where A caused B

## Testing
- [ ] Unit tests added for new logic
- [ ] Manual testing: describe what you tested
- [ ] Edge cases considered: list them

## Screenshots / Recordings
(For UI changes — before/after)

## Related
- Closes #123
- Depends on #456
```

---

## 4. Changelog Entry

### Format (Keep a Changelog)

```markdown
## [Unreleased]

### Added
- JWT refresh token flow for seamless re-authentication

### Fixed
- Null response handling in user API endpoint

### Changed
- Database connection pooling for improved throughput
```

---

## 5. Review-Friendly Practices

| Practice | Why |
|----------|-----|
| **Annotate your PR** | Add comments explaining tricky code |
| **Stack PRs** | Break large features into reviewable parts |
| **Highlight risks** | Flag areas that need careful review |
| **Respond promptly** | Don't let review feedback go stale |
| **Don't take it personally** | Reviews improve code, not judge you |

---

## 6. Merge Strategy

| Strategy | When |
|----------|------|
| **Squash merge** | Feature branches → clean history |
| **Merge commit** | Preserve full branch history |
| **Rebase** | Linear history, small PRs |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| 2000+ line PR | Keep under 400 lines |
| "WIP" merged PR | Complete before requesting review |
| No description | Always explain what and why |
| Force-merge without approval | Get at least one approval |
| Mix unrelated changes | One concern per PR |

---

> **Remember:** A good PR tells a story. The reviewer should understand what changed, why, and how you verified it — without asking questions.
