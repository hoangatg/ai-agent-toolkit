---
name: htmx-alpine
description: HTMX and Alpine.js patterns for building interactive web applications without heavy JavaScript frameworks. Hypermedia-driven architecture, progressive enhancement. Use when building server-rendered apps with modern interactivity.
---

# HTMX & Alpine.js

> Build modern interactive web apps without heavy JS frameworks. Hypermedia as the engine of application state.

## HTMX Core

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `hx-get` | GET request | `hx-get="/api/users"` |
| `hx-post` | POST request | `hx-post="/api/users"` |
| `hx-target` | Where to put response | `hx-target="#results"` |
| `hx-swap` | How to insert | `hx-swap="innerHTML"` |
| `hx-trigger` | When to fire | `hx-trigger="click"` |
| `hx-indicator` | Loading spinner | `hx-indicator=".spinner"` |

## Alpine.js Core

| Directive | Purpose |
|-----------|---------|
| `x-data` | Component state |
| `x-bind` | Dynamic attributes |
| `x-on` | Event listeners |
| `x-show` | Toggle visibility |
| `x-for` | List rendering |
| `x-transition` | CSS transitions |

---

## When to Use

| Use Case | HTMX | Alpine.js | Both |
|----------|------|-----------|------|
| Server-rendered CRUD | ✅ | | |
| Client-side toggles | | ✅ | |
| Interactive forms | | | ✅ |
| Real-time updates | ✅ (SSE) | | |
