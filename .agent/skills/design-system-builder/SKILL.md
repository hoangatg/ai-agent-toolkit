---
name: design-system-builder
description: Building and maintaining design systems. Component libraries, design tokens, documentation, and team adoption. Use when creating reusable UI component libraries.
---

# Design System Builder

> Design once, use everywhere. Consistency at scale.

---

## 1. Core Components

### Design System Layers

| Layer | Contains |
|-------|---------|
| **Tokens** | Colors, spacing, typography, shadows |
| **Foundations** | Grid, layout, breakpoints |
| **Components** | Buttons, inputs, cards, modals |
| **Patterns** | Forms, navigation, data display |
| **Templates** | Full page layouts |

---

## 2. Design Tokens

### Token Architecture

| Level | Example | Purpose |
|-------|---------|---------|
| **Global** | `color-blue-500` | Platform values |
| **Alias** | `color-primary` | Semantic mapping |
| **Component** | `button-bg-primary` | Component-specific |

### Token Formats

| Tool | Format |
|------|--------|
| **Style Dictionary** | JSON → CSS/JS/iOS/Android |
| **Figma Tokens** | Figma plugin → JSON |
| **CSS Custom Properties** | Native browser support |

---

## 3. Component Design

### Component API Principles

| Principle | Application |
|-----------|-------------|
| **Composition** | Compound components over mega-props |
| **Polymorphic** | `as` prop for element type |
| **Accessible** | ARIA attributes built-in |
| **Themed** | Tokens, not hardcoded values |
| **Documented** | Props table + examples + guidelines |

### Component Maturity Levels

| Level | Requirements |
|-------|-------------|
| **Alpha** | Functional, basic tests |
| **Beta** | Accessible, documented, stable API |
| **Stable** | Full tests, Storybook, design approved |
| **Deprecated** | Migration guide, timeline |

---

## 4. Documentation

### Docs Site Requirements

| Section | Content |
|---------|---------|
| **Getting Started** | Install, setup, quickstart |
| **Foundations** | Colors, typography, spacing |
| **Components** | Live examples, props, guidelines |
| **Patterns** | Common usage patterns |
| **Changelog** | Version history |

### Tools

| Tool | Purpose |
|------|---------|
| **Storybook** | Component playground + docs |
| **Chromatic** | Visual regression testing |
| **Docusaurus** | Documentation site |

---

## 5. Versioning & Publishing

| Strategy | Approach |
|----------|----------|
| **Semantic versioning** | Major (breaking), Minor (feature), Patch (fix) |
| **Changesets** | Manage versioning in monorepo |
| **Release process** | Automated CI/CD publish |
| **Migration guides** | For every breaking change |

---

## 6. Adoption Strategy

| Phase | Action |
|-------|--------|
| **1. Foundation** | Build core tokens + 5-10 key components |
| **2. Champion** | One team adopts, provides feedback |
| **3. Expand** | More teams adopt, iterate |
| **4. Mandate** | All new projects use design system |
| **5. Maintain** | Dedicated team, contribution model |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Build 50 components day 1 | Start with 5-10 most used |
| Hardcoded values | Everything through tokens |
| Skip accessibility | WCAG 2.1 AA minimum |
| No documentation | Storybook + guidelines |
| One person owns it | Shared ownership, contribution model |

---

> **Remember:** A design system is a product, not a project. It needs users, feedback, versioning, and ongoing maintenance to succeed.
