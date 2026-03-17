---
name: monorepo-management
description: Monorepo strategies with Turborepo, Nx, and pnpm workspaces. Shared packages, build optimization, and team workflows. Use when managing multi-package or multi-app repositories.
---

# Monorepo Management

> One repo, many packages. Shared code, independent deploys.

---

## 1. Tool Selection

| Tool | Best For |
|------|----------|
| **Turborepo** | JavaScript/TypeScript, simple setup |
| **Nx** | Full-featured, plugins, any language |
| **pnpm Workspaces** | Package management (often paired with Turbo/Nx) |
| **Lerna** | Legacy, publishing-focused |
| **Bazel** | Very large scale, polyglot |

---

## 2. Structure

### Recommended Layout

```
monorepo/
├── apps/            # Deployable applications
│   ├── web/         # Next.js frontend
│   ├── mobile/      # React Native app
│   └── api/         # Backend server
├── packages/        # Shared libraries
│   ├── ui/          # Shared UI components
│   ├── config/      # Shared configs (ESLint, TS)
│   ├── utils/       # Shared utilities
│   └── types/       # Shared TypeScript types
├── turbo.json       # Turborepo config
├── pnpm-workspace.yaml
└── package.json     # Root package
```

---

## 3. Dependency Management

| Principle | Application |
|-----------|-------------|
| **Internal packages** | Reference via workspace protocol `workspace:*` |
| **Shared deps** | Hoist common dependencies to root |
| **Version sync** | Same version of React across all apps |
| **Dev deps** | Config packages (ESLint, TypeScript) shared |

---

## 4. Build Optimization

### Turborepo Features

| Feature | Impact |
|---------|--------|
| **Remote caching** | Skip builds already done by teammates |
| **Task pipelines** | Define build order dependencies |
| **Parallel execution** | Build independent packages simultaneously |
| **Pruning** | Deploy only needed packages |

### Pipeline Config

```
Only rebuild what changed:
├── Package A changed → Rebuild A + dependents
├── Package B unchanged → Cache hit ✅
└── App X depends on A → Rebuild X
```

---

## 5. CI/CD for Monorepos

| Strategy | Approach |
|----------|----------|
| **Affected only** | Build/test only changed packages |
| **Remote cache** | Share build cache across CI runs |
| **Parallel** | Run tests per package in parallel |
| **Deploy independently** | Each app has its own deploy pipeline |

---

## 6. Shared Package Design

| Principle | Application |
|-----------|-------------|
| **Clear API** | Export explicit public API |
| **Typed** | Full TypeScript support |
| **Tested** | Own test suite |
| **Documented** | README per package |
| **Versioned** | Changesets for versioning |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| npm/yarn without workspaces | pnpm workspaces |
| Build everything always | Incremental + cached builds |
| Circular dependencies | Clear dependency graph |
| One config for everything | Per-package configs extending shared |
| Couple all packages | Independent versioning and deploys |

---

> **Remember:** A monorepo is not a monolith. Packages should be independent units that happen to live together for convenience. If coupling increases, your monorepo is a mono-mess.
