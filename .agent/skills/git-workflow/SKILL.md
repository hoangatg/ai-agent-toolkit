---
name: git-workflow
description: Git branching strategies, conventional commits, PR best practices, and CI/CD integration. Use when setting up or improving development workflows.
---

# Git Workflow

> Good git habits make teams fast. Bad ones make teams suffer.

---

## 1. Branching Strategies

| Strategy | Best For | Complexity |
|----------|----------|-----------|
| **GitHub Flow** | Small teams, continuous deploy | Low |
| **GitFlow** | Release cycles, versioned software | Medium |
| **Trunk-Based** | CI/CD, feature flags | Low-Medium |

### GitHub Flow (Recommended for most)

```
main (always deployable)
  └── feature/xyz → PR → Review → Merge → Deploy
```

### Branch Naming

| Type | Pattern | Example |
|------|---------|---------|
| **Feature** | `feature/short-desc` | `feature/user-auth` |
| **Bugfix** | `fix/short-desc` | `fix/login-crash` |
| **Hotfix** | `hotfix/short-desc` | `hotfix/payment-error` |
| **Chore** | `chore/short-desc` | `chore/update-deps` |

---

## 2. Conventional Commits

### Format

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

### Types

| Type | When |
|------|------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, no logic change |
| `refactor` | Code restructuring |
| `perf` | Performance improvement |
| `test` | Adding/fixing tests |
| `chore` | Build, CI, tooling |
| `revert` | Reverting a commit |

### Breaking Changes

```
feat(api)!: change response format

BREAKING CHANGE: response.data is now an array
```

---

## 3. Pull Request Best Practices

| Principle | Application |
|-----------|-------------|
| **Small PRs** | < 400 lines changed |
| **Clear title** | Conventional commit format |
| **Description** | What, why, how, testing done |
| **Screenshots** | For UI changes |
| **Self-review first** | Review your own diff before submitting |

### PR Template

```markdown
## What
Brief description of changes

## Why
Context and motivation

## Testing
How this was tested

## Checklist
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] No breaking changes
```

---

## 4. Code Review

| Speed | Principle |
|-------|----------|
| **< 24h** | Review within one business day |
| **Approve or comment** | Don't leave PRs hanging |
| **Constructive** | Suggest alternatives, not just criticize |
| **Distinguish** | Blockers vs. nitpicks vs. questions |

---

## 5. Git Hygiene

| Practice | Why |
|----------|-----|
| **Rebase before merge** | Clean linear history |
| **Squash for features** | One commit per feature |
| **Never force-push main** | Protect shared branches |
| **Tag releases** | Semantic versioning |
| **Clean up branches** | Delete after merge |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| `git push -f main` | Protect main branch |
| 2000-line PRs | Small, focused PRs |
| "fix stuff" commits | Descriptive conventional commits |
| Commit secrets | Use .gitignore + env files |
| Long-lived branches | Merge frequently, feature flags |

---

> **Remember:** Git history is your project's memory. Keep it clean, meaningful, and useful for your future self and teammates.
