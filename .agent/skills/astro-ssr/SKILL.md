---
name: astro-ssr
description: Astro 4+ development with content collections, islands architecture, and hybrid rendering. Use when building content-heavy sites, blogs, documentation, or hybrid SSR/SSG applications.
---

# Astro Expert

> Astro 4+ — the web framework for content-driven websites. Islands architecture for optimal performance.

## Core Concepts

| Concept | Description |
|---------|-------------|
| **Islands Architecture** | Interactive components as isolated "islands" in static HTML |
| **Zero JS by Default** | Ship no JavaScript unless explicitly needed |
| **Content Collections** | Type-safe content management with schemas |
| **View Transitions** | Built-in page transitions (MPA) |
| **Hybrid Rendering** | Mix SSG + SSR + prerendering per route |

---

## Framework Integration

Astro supports multiple UI frameworks in the same project:

```astro
---
import ReactComponent from './React.tsx'
import VueComponent from './Vue.vue'
import SvelteComponent from './Svelte.svelte'
---
<ReactComponent client:load />
<VueComponent client:visible />
<SvelteComponent client:idle />
```

### Client Directives

| Directive | When JS Loads |
|-----------|--------------|
| `client:load` | Immediately |
| `client:idle` | When browser is idle |
| `client:visible` | When component enters viewport |
| `client:media` | When media query matches |
| `client:only` | Skip SSR, client-side only |

---

## Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Make everything interactive | Use islands only where needed |
| Use SSR for static content | Use prerendering for static pages |
| Skip content collections | Use typed collections for content |
