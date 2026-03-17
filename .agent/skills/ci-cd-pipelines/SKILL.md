---
name: ci-cd-pipelines
description: CI/CD pipeline design. GitHub Actions, GitLab CI, automated testing, and deployment automation. Use when setting up or optimizing build and deploy pipelines.
---

# CI/CD Pipelines

> Every push should build, test, and potentially ship — automatically.

---

## 1. Platform Selection

| Platform | Best For |
|----------|----------|
| **GitHub Actions** | GitHub repos, marketplace ecosystem |
| **GitLab CI** | Self-hosted GitLab, built-in registry |
| **CircleCI** | Fast builds, Docker-native |
| **Jenkins** | Self-hosted, unlimited customization |
| **Bitbucket Pipelines** | Atlassian ecosystem |

---

## 2. Pipeline Design

### Standard Stages

```
Push → Lint → Test → Build → Deploy (Preview) → Deploy (Production)
```

### Stage Design

| Stage | Trigger | Fail = Block? |
|-------|---------|--------------|
| **Lint** | Every push | ✅ Yes |
| **Unit Tests** | Every push | ✅ Yes |
| **Integration Tests** | Every push | ✅ Yes |
| **Build** | Every push | ✅ Yes |
| **E2E Tests** | PR only | ⚠️ Warning |
| **Preview Deploy** | PR only | ❌ No |
| **Production Deploy** | Merge to main | ✅ Yes |

---

## 3. GitHub Actions Patterns

### Key Concepts

| Concept | Purpose |
|---------|---------|
| **Workflow** | `.yml` file defining the pipeline |
| **Job** | Set of steps on one runner |
| **Step** | Individual command or action |
| **Action** | Reusable workflow unit |
| **Matrix** | Run same job with different configs |
| **Cache** | Speed up dependencies install |

### Performance Optimization

| Technique | Impact |
|-----------|--------|
| **Dependency caching** | 50-80% faster installs |
| **Parallel jobs** | Reduce total time |
| **Conditional runs** | Skip unnecessary steps |
| **Reusable workflows** | DRY pipeline code |
| **Self-hosted runners** | More power, less cost |

---

## 4. Testing in CI

| Test Type | When | Timeout |
|-----------|------|---------|
| **Lint** | Always | 2 min |
| **Unit** | Always | 5 min |
| **Integration** | Always | 10 min |
| **E2E** | PR + main | 15 min |
| **Visual regression** | PR | 10 min |

---

## 5. Deployment Strategies

| Strategy | Risk | Use Case |
|----------|------|----------|
| **Direct** | High | Dev/staging |
| **Blue/Green** | Low | Zero-downtime |
| **Canary** | Very low | Gradual rollout |
| **Feature flags** | Lowest | Decouple deploy from release |

---

## 6. Secrets & Security

| Practice | Implementation |
|----------|---------------|
| **Encrypted secrets** | Platform secret stores |
| **Least privilege** | Minimal permissions per workflow |
| **OIDC** | Federated auth (no static keys) |
| **Dependency scanning** | Dependabot, Snyk |
| **Signed commits** | Verify authorship |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Skip CI on main | Always run full pipeline |
| Manual deploy steps | Fully automated |
| Secrets in repo | Encrypted secret stores |
| No caching | Cache deps and build artifacts |
| Flaky tests pass | Fix or quarantine flaky tests |

---

> **Remember:** The best CI/CD pipeline is invisible — developers push code, and it safely arrives in production. Invest in reliability, speed, and fast feedback.
