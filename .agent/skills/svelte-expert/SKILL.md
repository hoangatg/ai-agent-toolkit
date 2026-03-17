---
name: svelte-expert
description: Svelte 5 and SvelteKit development patterns. Runes, snippets, server-side rendering, and full-stack Svelte. Use when building Svelte applications or SvelteKit projects.
---

# Svelte Expert

> Svelte 5 with runes, SvelteKit 2 for full-stack development. Less boilerplate, more performance.

## Svelte 5 Runes

| Rune | Purpose | Example |
|------|---------|---------|
| `$state` | Reactive state | `let count = $state(0)` |
| `$derived` | Computed values | `let doubled = $derived(count * 2)` |
| `$effect` | Side effects | `$effect(() => console.log(count))` |
| `$props` | Component props | `let { name } = $props()` |
| `$bindable` | Two-way binding | `let { value = $bindable() } = $props()` |

---

## SvelteKit Patterns

- **File-based routing**: `src/routes/[slug]/+page.svelte`
- **Server load functions**: `+page.server.ts` for data loading
- **Actions**: Form handling with `+page.server.ts` actions
- **Hooks**: `src/hooks.server.ts` for middleware
- **API Routes**: `+server.ts` for REST endpoints

---

## Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Use stores in Svelte 5 | Use $state runes |
| Client-side data fetching | Server load functions |
| Skip form validation | Use SvelteKit actions + superforms |
