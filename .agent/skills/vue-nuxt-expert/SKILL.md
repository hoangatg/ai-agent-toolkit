---
name: vue-nuxt-expert
description: Vue 3 Composition API and Nuxt 3 patterns. Reactivity, composables, server-side rendering, and full-stack Vue development. Use when building Vue.js or Nuxt applications.
---

# Vue & Nuxt Expert

> The progressive framework — simple to start, powerful to scale.

---

## 1. Vue 3 Core

### Composition API Patterns

| Pattern | Use Case |
|---------|----------|
| **ref()** | Primitive reactive values |
| **reactive()** | Object/array reactive state |
| **computed()** | Derived values |
| **watch()** | Side effects on change |
| **watchEffect()** | Auto-tracked side effects |

### Composables Design

| Principle | Application |
|-----------|-------------|
| **Naming** | `useXxx` convention |
| **Return object** | `{ data, loading, error }` |
| **Cleanup** | Use `onUnmounted` for teardown |
| **Reusable** | No component-specific logic |

---

## 2. Nuxt 3 Architecture

### Directory Conventions

| Directory | Purpose | Auto-import |
|-----------|---------|-------------|
| `pages/` | File-based routing | ✅ |
| `components/` | Vue components | ✅ |
| `composables/` | Composition functions | ✅ |
| `server/` | API routes, middleware | ✅ |
| `layouts/` | Page layouts | ✅ |
| `middleware/` | Route middleware | ✅ |
| `plugins/` | App plugins | ✅ |

### Data Fetching

| Composable | Rendering | Caching |
|-----------|-----------|---------|
| `useFetch()` | SSR + client | ✅ De-duped |
| `useAsyncData()` | SSR + client | ✅ Key-based |
| `$fetch()` | Client-only | ❌ Manual |
| `useLazyFetch()` | Non-blocking SSR | ✅ De-duped |

---

## 3. State Management

| Solution | Best For |
|----------|----------|
| **Pinia** | Global state (official) |
| **useState()** | SSR-friendly shared state |
| **Composables** | Feature-scoped state |
| **VueUse** | Common reactive utilities |

---

## 4. Server Engine (Nitro)

| Feature | Purpose |
|---------|---------|
| **API routes** | `server/api/` file-based |
| **Server middleware** | Request processing |
| **Server plugins** | DB connections, init |
| **Hybrid rendering** | Per-route SSR/SSG/SPA |
| **Deploy anywhere** | Node, Edge, Serverless |

---

## 5. Performance

| Technique | Impact |
|-----------|--------|
| **Auto-imports** | Tree-shake unused code |
| **Lazy components** | `<LazyComponent />` prefix |
| **Payload optimization** | Minimize SSR payload |
| **Image optimization** | `<NuxtImg>` component |
| **Route preloading** | `<NuxtLink prefetch>` |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Options API in new code | Composition API + `<script setup>` |
| reactive() for primitives | ref() for primitives |
| Mutate props | emit events, v-model |
| Vuex in new projects | Pinia (official successor) |
| Manual imports | Let Nuxt auto-import |

---

> **Remember:** Vue's power is in its simplicity. `<script setup>` + Composition API + Pinia covers 95% of use cases without boilerplate.
