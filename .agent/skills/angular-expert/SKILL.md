---
name: angular-expert
description: Angular 17+ development with signals, standalone components, and modern patterns. Use when building Angular applications, enterprise SPAs, or migrating Angular projects.
---

# Angular Expert

> Modern Angular 17+ with signals, standalone components, and control flow syntax.

## Key Changes in Modern Angular

| Feature | Old Way | New Way (17+) |
|---------|---------|---------------|
| **Components** | NgModules | Standalone components |
| **Reactivity** | RxJS-heavy | Signals + computed |
| **Control Flow** | *ngIf, *ngFor | @if, @for, @switch |
| **SSR** | Universal | Built-in SSR + hydration |
| **Routing** | Module-based | Functional guards + resolvers |

---

## Patterns

- **Signals**: `signal()`, `computed()`, `effect()` for reactive state
- **Standalone**: Components/directives/pipes without NgModule
- **Functional Guards**: Route guards as functions, not classes
- **Deferrable Views**: `@defer` for lazy loading sections
- **New Control Flow**: `@if`, `@for`, `@switch` template syntax

---

## Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Subscribe manually in components | Use async pipe or toSignal() |
| Create NgModules for everything | Use standalone components |
| Ignore OnPush | Use ChangeDetectionStrategy.OnPush |
