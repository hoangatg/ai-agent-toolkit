---
name: scroll-experience
description: Scroll-driven animations and interactions. GSAP, Framer Motion, CSS scroll-driven animations, and parallax effects. Use when creating immersive scrolling experiences.
---

# Scroll Experience

> Make scrolling an adventure, not a chore.

---

## 1. Technology Selection

| Technology | Best For |
|-----------|----------|
| **CSS Scroll-Driven Animations** | Native, performant, simple effects |
| **GSAP ScrollTrigger** | Complex timelines, production-grade |
| **Framer Motion** | React ecosystem, declarative |
| **Lenis** | Custom smooth scrolling |
| **Intersection Observer** | Trigger-based, lightweight |

---

## 2. Scroll Animation Patterns

| Pattern | Description | Complexity |
|---------|-------------|-----------|
| **Reveal on scroll** | Elements appear as you scroll | Low |
| **Parallax** | Layers move at different speeds | Low-Medium |
| **Pin + scrub** | Element sticks while animating | Medium |
| **Horizontal scroll** | Horizontal movement via vertical scroll | Medium |
| **Scroll-linked video** | Video progress tied to scroll | High |
| **3D scene scroll** | Camera/scene changes with scroll | High |

---

## 3. GSAP ScrollTrigger

### Core Concepts

| Concept | Purpose |
|---------|---------|
| **trigger** | Element that starts the animation |
| **start/end** | When animation begins/ends |
| **scrub** | Link animation progress to scroll |
| **pin** | Fix element during scroll range |
| **snap** | Snap to discrete positions |

### Performance Settings

| Setting | Use |
|---------|-----|
| `scrub: true` | Smooth, exact scroll tracking |
| `scrub: 0.5` | Slight lag for smoothness |
| `anticipatePin: 1` | Prevent jank when pinning |
| `invalidateOnRefresh` | Recalculate on resize |

---

## 4. CSS Scroll-Driven Animations

### Key Properties

| Property | Purpose |
|----------|---------|
| `animation-timeline: scroll()` | Bind to scroll progress |
| `animation-timeline: view()` | Bind to element visibility |
| `animation-range` | Define start/end points |
| `view-timeline` | Named element timelines |

---

## 5. Performance Principles

| Principle | Application |
|-----------|-------------|
| **Animate transforms only** | `transform` and `opacity` are GPU-accelerated |
| **Will-change** | Hint browser about animated properties |
| **Reduce repaints** | No layout-triggering properties (width, height) |
| **Debounce scroll** | Don't fire on every pixel |
| **Lazy load** | Load content as needed |
| **Prefers-reduced-motion** | Respect accessibility settings |

### What to Animate

| ✅ GPU-Accelerated | ❌ Layout-Triggering |
|-------------------|---------------------|
| `transform` | `width`, `height` |
| `opacity` | `top`, `left` |
| `filter` | `margin`, `padding` |
| `clip-path` | `font-size` |

---

## 6. Accessibility

| Requirement | Implementation |
|-------------|---------------|
| **prefers-reduced-motion** | Disable/reduce animations |
| **Keyboard navigation** | Scroll alternatives for keyboards |
| **Content accessible** | Content readable without animations |
| **Performance** | Don't block interaction |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Animate layout properties | Use transform + opacity |
| Hijack native scroll | Enhance, don't replace |
| Animation without purpose | Every animation should serve UX |
| Skip mobile testing | Touch scrolling is different |
| Ignore reduced-motion | Always provide alternative |

---

> **Remember:** The best scroll animations feel natural and inevitable. If the user notices the technology, you've overdone it.
