---
name: minimalist-skill
description: Premium utilitarian minimalism UI protocol. Clean, editorial-style interfaces inspired by Notion and Linear. Warm monochrome palettes, serif/sans-serif typographic contrast, massive whitespace, flat bento grids with crisp hairline borders, and muted pastel accents.
---

# Protocol: Premium Utilitarian Minimalism UI Architect

## 1. Protocol Overview
Name: Premium Utilitarian Minimalism & Editorial UI
Description: An advanced frontend engineering directive for generating highly refined, ultra-minimalist, "document-style" web interfaces analogous to top-tier workspace platforms. This protocol strictly enforces a high-contrast warm monochrome palette, bespoke typographic hierarchies, meticulous structural macro-whitespace, bento-grid layouts, and an ultra-flat component architecture with deliberate muted pastel accents. It actively rejects standard generic SaaS design trends.

## 2. Absolute Negative Constraints (Banned Elements)
The AI must strictly avoid the following generic web development defaults:
- DO NOT use the "Inter", "Roboto", or "Open Sans" typefaces.
- DO NOT use generic, thin-line icon libraries like "Lucide", "Feather", or standard "Heroicons".
- DO NOT use Tailwind's default heavy drop shadows (e.g., `shadow-md`, `shadow-lg`, `shadow-xl`). Shadows must be practically non-existent or heavily customized to be ultra-diffuse and low opacity (< 0.05).
- DO NOT use primary colored backgrounds for large elements or sections.
- DO NOT use gradients, neon colors, or 3D glassmorphism (beyond subtle navbar blurs).
- DO NOT use `rounded-full` (pill shapes) for large containers, cards, or primary buttons.
- DO NOT use emojis anywhere in code, markup, text content, headings, or alt text.
- DO NOT use generic placeholder names like "John Doe", "Acme Corp", or "Lorem Ipsum".
- DO NOT use AI copywriting clichés: "Elevate", "Seamless", "Unleash", "Next-Gen", "Game-changer", "Delve".

## 3. Typographic Architecture
The interface must rely on extreme typographic contrast and premium font selection to establish an editorial feel.
- **Primary Sans-Serif (Body, UI, Buttons):** `font-family: 'SF Pro Display', 'Geist Sans', 'Helvetica Neue', 'Switzer', sans-serif`.
- **Editorial Serif (Hero Headings & Quotes):** `font-family: 'Lyon Text', 'Newsreader', 'Playfair Display', 'Instrument Serif', serif`. Apply tight tracking (`letter-spacing: -0.02em` to `-0.04em`) and tight line-height (`1.1`).
- **Monospace (Code, Keystrokes, Meta-data):** `font-family: 'Geist Mono', 'SF Mono', 'JetBrains Mono', monospace`.
- **Text Colors:** Body text must never be absolute black (`#000000`). Use off-black/charcoal (`#111111` or `#2F3437`) with generous `line-height` of `1.6`. Secondary text: muted gray (`#787774`).

## 4. Color Palette (Warm Monochrome + Spot Pastels)
Color is a scarce resource, utilized only for semantic meaning or subtle accents.
- **Canvas / Background:** Pure White `#FFFFFF` or Warm Bone/Off-White `#F7F6F3` / `#FBFBFA`.
- **Primary Surface (Cards):** `#FFFFFF` or `#F9F9F8`.
- **Structural Borders / Dividers:** Ultra-light gray `#EAEAEA` or `rgba(0,0,0,0.06)`.
- **Accent Colors:** Exclusively use highly desaturated, washed-out pastels:
  - Pale Red: `#FDEBEC` (Text: `#9F2F2D`)
  - Pale Blue: `#E1F3FE` (Text: `#1F6C9F`)
  - Pale Green: `#EDF3EC` (Text: `#346538`)
  - Pale Yellow: `#FBF3DB` (Text: `#956400`)

## 5. Component Specifications
- **Bento Box Feature Grids:**
  - Asymmetrical CSS Grid layouts.
  - Cards must have exactly `border: 1px solid #EAEAEA`.
  - Border-radius: crisp `8px` or `12px` maximum.
  - Internal padding: generous (`24px` to `40px`).
- **Primary Call-To-Action (Buttons):**
  - Solid background `#111111`, text `#FFFFFF`. 
  - Slight border-radius (`4px` to `6px`). No box-shadow. 
  - Hover state: subtle color shift to `#333333` or micro-scale `transform: scale(0.98)`.
- **Tags & Status Badges:**
  - Pill-shaped, very small typography (`text-xs`), uppercase with wide tracking.
  - Background must use the defined Muted Pastels.
- **Accordions (FAQ):**
  - Strip all container boxes. Separate items only with `border-bottom: 1px solid #EAEAEA`.
  - Use clean `+` and `-` icons for toggle state.
- **Keystroke Micro-UIs:**
  - Render shortcuts as physical keys using `<kbd>` tags.
- **Faux-OS Window Chrome:**
  - When mocking software, wrap in minimalist container with white top bar containing three small gray circles (macOS window controls).

## 6. Iconography & Imagery Directives
- **System Icons:** Use "Phosphor Icons (Bold or Fill weights)" or "Radix UI Icons" for a technical aesthetic.
- **Illustrations:** Monochromatic, rough continuous-line ink sketches with a single offset geometric shape filled with a muted pastel color.
- **Photography:** High-quality, desaturated images with warm tone. Apply subtle overlays to blend into monochrome palette. Use `https://picsum.photos/seed/{context}/1200/800` when real assets unavailable.
- **Hero & Section Backgrounds:** Add subtle full-width background imagery at very low opacity, soft radial light spots, or minimal geometric line patterns.

## 7. Subtle Motion & Micro-Animations
Motion should feel invisible — present but never distracting. The goal is quiet sophistication, not spectacle.
- **Scroll Entry:** Elements fade in gently. Use `translateY(12px)` + `opacity: 0` resolving over `600ms` with `cubic-bezier(0.16, 1, 0.3, 1)`. Use `IntersectionObserver`, never `window.addEventListener('scroll')`.
- **Hover States:** Cards lift with ultra-subtle shadow shift (`0 2px 8px rgba(0,0,0,0.04)` over `200ms`). Buttons respond with `scale(0.98)` on `:active`.
- **Staggered Reveals:** Lists and grid items enter with cascade delay (`animation-delay: calc(var(--index) * 80ms)`).
- **Background Ambient Motion:** Optional. Very slow-moving radial gradient blob (`animation-duration: 20s+`, `opacity: 0.02-0.04`). Must be `position: fixed; pointer-events: none`.
- **Performance:** Animate exclusively via `transform` and `opacity`. No layout-triggering properties.

## 8. Execution Protocol
When tasked with writing frontend code:
1. Establish macro-whitespace first. Use massive vertical padding (`py-24` or `py-32`).
2. Constrain typography content width to `max-w-4xl` or `max-w-5xl`.
3. Apply custom typographic hierarchy and monochromatic color variables immediately.
4. Ensure every card, divider, and border adheres to `1px solid #EAEAEA`.
5. Add scroll-entry animations to all major content blocks.
6. Ensure sections have visual depth through imagery, ambient gradients, or subtle textures.
7. Provide code that reflects this high-end, uncluttered, editorial aesthetic natively.
