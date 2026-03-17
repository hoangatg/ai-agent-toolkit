---
name: zustand-state-management
description: Zustand and modern React state management patterns. Lightweight stores, middleware, persistence, and devtools. Use when implementing client-side state management in React applications.
---

# Zustand State Management

> Lightweight, scalable state management for React. No boilerplate, no providers, just stores.

## Why Zustand?

| Feature | Redux Toolkit | Zustand | Jotai |
|---------|-------------|---------|-------|
| **Boilerplate** | Medium | Minimal | Minimal |
| **Bundle Size** | ~12kb | ~1kb | ~2kb |
| **Provider needed** | Yes | No | Yes |
| **DevTools** | Built-in | Middleware | External |
| **Learning curve** | Steep | Easy | Easy |

---

## Core Patterns

```typescript
// Store creation
const useStore = create<State>((set, get) => ({
  count: 0,
  increment: () => set((s) => ({ count: s.count + 1 })),
  // Async actions
  fetchData: async () => {
    const data = await api.fetch()
    set({ data })
  },
}))

// Usage in components
const count = useStore((s) => s.count)  // Auto-memoized selector
```

## Middleware Stack

| Middleware | Purpose |
|-----------|---------|
| `persist` | localStorage/sessionStorage persistence |
| `devtools` | Redux DevTools integration |
| `immer` | Immutable updates with mutable syntax |
| `subscribeWithSelector` | Fine-grained subscriptions |

---

## Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Select entire store `useStore()` | Use selectors `useStore(s => s.count)` |
| Put server state in store | Use TanStack Query for server state |
| One mega store | Split into focused domain stores |
