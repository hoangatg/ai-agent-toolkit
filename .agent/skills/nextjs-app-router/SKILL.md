---
name: nextjs-app-router
description: Next.js 14+ App Router patterns. Server Components, Server Actions, streaming, caching, and modern data fetching. Use when building Next.js applications with the App Router.
---

# Next.js App Router

> Server-first React. Less JavaScript, faster pages.

---

## 1. Core Concepts

### Server vs Client Components

| Feature | Server Component (default) | Client Component (`"use client"`) |
|---------|---------------------------|-----------------------------------|
| **Rendering** | Server only | Server + Client hydration |
| **JS bundle** | Zero | Included in bundle |
| **Data fetching** | Direct DB/API access | useEffect or React Query |
| **State/Effects** | ❌ No hooks | ✅ useState, useEffect |
| **Event handlers** | ❌ No onClick | ✅ Full interactivity |
| **Best for** | Static content, data display | Interactive UI, forms |

> **Rule:** Everything is a Server Component unless it needs interactivity. Push `"use client"` as far down the tree as possible.

---

## 2. Routing

### File Conventions

| File | Purpose |
|------|---------|
| `page.tsx` | Route UI |
| `layout.tsx` | Shared layout (persists across navigations) |
| `loading.tsx` | Streaming fallback |
| `error.tsx` | Error boundary |
| `not-found.tsx` | 404 page |
| `route.ts` | API endpoint |

### Route Groups & Parallel Routes

| Pattern | Syntax | Use Case |
|---------|--------|----------|
| **Route Group** | `(group)` | Organize without URL impact |
| **Parallel** | `@slot` | Multiple views on same page |
| **Intercepting** | `(.)`, `(..)` | Modal patterns |
| **Dynamic** | `[slug]` | Parameterized routes |
| **Catch-all** | `[...slug]` | Flexible matching |

---

## 3. Data Fetching

### Patterns

| Pattern | Where | Caching |
|---------|-------|---------|
| `fetch()` in Server Component | Server | Cached by default |
| Server Action | Server | No cache |
| React Query | Client | Client cache |
| `unstable_cache` | Server | Manual cache |

### Caching Strategy

| Cache Layer | Default | Override |
|-------------|---------|----------|
| **Request memoization** | ON | Per request |
| **Data cache** | ON | `revalidate` option |
| **Full route cache** | ON (static) | `dynamic = 'force-dynamic'` |
| **Router cache** | ON | `revalidatePath()`, `revalidateTag()` |

---

## 4. Server Actions

### Principles

| Principle | Application |
|-----------|-------------|
| **`"use server"`** | Mark function as server action |
| **Progressive enhancement** | Forms work without JS |
| **Validation** | Always validate on server (use Zod) |
| **Revalidation** | Call `revalidatePath()` after mutations |
| **Optimistic UI** | `useOptimistic` for instant feedback |

---

## 5. Streaming & Suspense

### Implementation

```
Layout (instant)
├── Header (instant)  
├── <Suspense fallback={<Skeleton />}>
│   └── SlowDataComponent (streams in)
└── Footer (instant)
```

### When to Use

| Scenario | Approach |
|----------|----------|
| Slow data fetch | Wrap in Suspense |
| Multiple data sources | Parallel Suspense boundaries |
| Critical content | No Suspense (block render) |
| SEO content | Server Component, no streaming |

---

## 6. Middleware

| Use Case | Implementation |
|----------|---------------|
| **Auth redirect** | Check session, redirect to login |
| **Geolocation** | Route based on country |
| **A/B testing** | Rewrite to variant pages |
| **Rate limiting** | Block excessive requests |

---

## 7. Performance

| Technique | Impact |
|-----------|--------|
| **Server Components** | Zero JS for static content |
| **Image component** | Auto optimization, lazy loading |
| **Font optimization** | `next/font` for zero layout shift |
| **Static generation** | Pre-render at build time |
| **Partial prerendering** | Static shell + dynamic holes |

---

## 8. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| `"use client"` on everything | Server Components by default |
| Fetch in client components | Fetch in server, pass as props |
| Ignore caching | Understand all 4 cache layers |
| Client-side auth checks only | Middleware + server validation |
| Skip loading/error states | Always add loading.tsx + error.tsx |

---

> **Remember:** App Router is "server-first." Think about what runs on the server (most things) and only add `"use client"` when you need browser APIs or interactivity.
