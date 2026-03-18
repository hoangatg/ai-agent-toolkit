---
name: redesign-skill
description: Design audit and upgrade skill for existing projects. Scans codebase for generic patterns, diagnoses weak points, and applies targeted premium fixes without rewriting from scratch. Covers typography, color, layout, interactivity, content, and component improvements.
---

# Redesign Skill

## How This Works
When applied to an existing project, follow this sequence:

1. **Scan** — Read the codebase. Identify the framework, styling method (Tailwind, vanilla CSS, styled-components, etc.), and current design patterns.
2. **Diagnose** — Run through the audit below. List every generic pattern, weak point, and missing state you find.
3. **Fix** — Apply targeted upgrades working with the existing stack. Do not rewrite from scratch. Improve what's there.

## Design Audit

### Typography
Check for these problems and fix them:

- **Browser default fonts or Inter everywhere.** Replace with a font that has character. Good options: `Geist`, `Outfit`, `Cabinet Grotesk`, `Satoshi`. For editorial/creative projects, pair a serif header with a sans-serif body.
- **Headlines lack presence.** Increase size for display text, tighten letter-spacing, reduce line-height. Headlines should feel heavy and intentional.
- **Body text too wide.** Limit paragraph width to roughly 65 characters. Increase line-height for readability.
- **Only Regular (400) and Bold (700) weights used.** Introduce Medium (500) and SemiBold (600) for more subtle hierarchy.
- **Numbers in proportional font.** Use a monospace font or enable tabular figures (`font-variant-numeric: tabular-nums`) for data-heavy interfaces.
- **Missing letter-spacing adjustments.** Use negative tracking for large headers, positive tracking for small caps or labels.
- **All-caps subheaders everywhere.** Try lowercase italics, sentence case, or small-caps instead.
- **Orphaned words.** Single words sitting alone on the last line. Fix with `text-wrap: balance` or `text-wrap: pretty`.

### Color and Surfaces
- **Pure `#000000` background.** Replace with off-black, dark charcoal, or tinted dark (`#0a0a0a`, `#121212`, or a dark navy).
- **Oversaturated accent colors.** Keep saturation below 80%. Desaturate accents so they blend with neutrals instead of screaming.
- **More than one accent color.** Pick one. Remove the rest. Consistency beats variety.
- **Mixing warm and cool grays.** Stick to one gray family. Tint all grays with a consistent hue (warm or cool, not both).
- **Purple/blue "AI gradient" aesthetic.** This is the most common AI design fingerprint. Replace with neutral bases and a single, considered accent.
- **Generic `box-shadow`.** Tint shadows to match the background hue. Use colored shadows instead of pure black at low opacity.
- **Flat design with zero texture.** Add subtle noise, grain, or micro-patterns to backgrounds. Pure flat vectors feel sterile.
- **Perfectly even gradients.** Break the uniformity with radial gradients, noise overlays, or mesh gradients instead of standard linear 45-degree fades.
- **Inconsistent lighting direction.** Audit all shadows to ensure they suggest a single, consistent light source.
- **Random dark sections in a light mode page (or vice versa).** A single dark-background section breaking an otherwise light page looks like a copy-paste accident. Either commit to a full dark mode or keep a consistent background tone throughout.
- **Empty, flat sections with no visual depth.** Add high-quality background imagery (blurred, overlaid, or masked), subtle patterns, or ambient gradients.

### Layout
- **Everything centered and symmetrical.** Break symmetry with offset margins, mixed aspect ratios, or left-aligned headers over centered content.
- **Three equal card columns as feature row.** This is the most generic AI layout. Replace with a 2-column zig-zag, asymmetric grid, horizontal scroll, or masonry layout.
- **Using `height: 100vh` for full-screen sections.** Replace with `min-height: 100dvh` to prevent layout jumping on mobile browsers.
- **Complex flexbox percentage math.** Replace with CSS Grid for reliable multi-column structures.
- **No max-width container.** Add a container constraint (around 1200-1440px) with auto margins.
- **Cards of equal height forced by flexbox.** Allow variable heights or use masonry when content varies in length.
- **Uniform border-radius on everything.** Vary the radius: tighter on inner elements, softer on containers.
- **No overlap or depth.** Use negative margins to create layering and visual depth.
- **Symmetrical vertical padding.** Bottom padding often needs to be slightly larger.
- **Dashboard always has a left sidebar.** Try top navigation, a floating command menu, or a collapsible panel instead.
- **Missing whitespace.** Double the spacing. Let the design breathe.
- **Buttons not bottom-aligned in card groups.** Pin buttons to the bottom of each card.
- **Feature lists starting at different vertical positions.** Use consistent spacing above the list.
- **Inconsistent vertical rhythm in side-by-side elements.** Align shared elements across all items.
- **Mathematical alignment that looks optically wrong.** Apply 1-2px optical adjustments.

### Interactivity and States
- **No hover states on buttons.** Add background shift, slight scale, or translate on hover.
- **No active/pressed feedback.** Add a subtle `scale(0.98)` or `translateY(1px)` on press.
- **Instant transitions with zero duration.** Add smooth transitions (200-300ms) to all interactive elements.
- **Missing focus ring.** Ensure visible focus indicators for keyboard navigation.
- **No loading states.** Replace generic circular spinners with skeleton loaders.
- **No empty states.** Design a composed "getting started" view.
- **No error states.** Add clear, inline error messages for forms. Do not use `window.alert()`.
- **Dead links.** Buttons that link to `#`. Either link to real destinations or visually disable them.
- **No indication of current page in navigation.** Style the active nav link differently.
- **Scroll jumping.** Add `scroll-behavior: smooth`.
- **Animations using `top`, `left`, `width`, `height`.** Switch to `transform` and `opacity`.

### Content
- **Generic names like "John Doe".** Use diverse, realistic-sounding names.
- **Fake round numbers.** Use organic, messy data: `47.2%`, `$99.00`.
- **Placeholder company names.** Invent contextual, believable brand names.
- **AI copywriting cliches.** Never use "Elevate", "Seamless", "Unleash", "Next-Gen", "Delve".
- **Exclamation marks in success messages.** Remove them. Be confident, not loud.
- **"Oops!" error messages.** Be direct: "Connection failed. Please try again."
- **Lorem Ipsum.** Write real draft copy.
- **Title Case On Every Header.** Use sentence case instead.

### Component Patterns
- **Generic card look (border + shadow + white background).** Remove the border, or use only background color, or use only spacing.
- **Always one filled button + one ghost button.** Add text links or tertiary styles.
- **3-card carousel testimonials with dots.** Replace with a masonry wall, embedded social posts, or a single rotating quote.
- **Pricing table with 3 towers.** Highlight the recommended tier with color and emphasis.
- **Modals for everything.** Use inline editing, slide-over panels, or expandable sections instead.
- **Avatar circles exclusively.** Try squircles or rounded squares.
- **Footer link farm with 4 columns.** Simplify.

### Iconography
- **Lucide or Feather icons exclusively.** Use Phosphor, Heroicons, or a custom set.
- **Rocketship for "Launch", shield for "Security".** Replace cliche metaphors.
- **Inconsistent stroke widths across icons.** Standardize to one stroke weight.
- **Missing favicon.** Always include a branded favicon.

### Code Quality
- **Div soup.** Use semantic HTML: `<nav>`, `<main>`, `<article>`, `<aside>`, `<section>`.
- **Hardcoded pixel widths.** Use relative units.
- **Missing alt text on images.** Describe image content.
- **Arbitrary z-index values like `9999`.** Establish a clean z-index scale.
- **Commented-out dead code.** Remove all debug artifacts.
- **Import hallucinations.** Check that every import exists in `package.json`.
- **Missing meta tags.** Add proper `<title>`, `description`, `og:image`.

### Strategic Omissions (What AI Typically Forgets)
- **No legal links.** Add privacy policy and terms of service.
- **No "back" navigation.** Every page needs a way back.
- **No custom 404 page.** Design a helpful, branded experience.
- **No form validation.** Add client-side validation.
- **No "skip to content" link.** Essential for keyboard users.
- **No cookie consent.** If required by jurisdiction, add a compliant consent banner.

## Upgrade Techniques
When upgrading a project, pull from these high-impact techniques:

### Typography Upgrades
- **Variable font animation.** Interpolate weight or width on scroll or hover.
- **Outlined-to-fill transitions.** Text starts as a stroke outline and fills with color on interaction.
- **Text mask reveals.** Large typography acting as a window to video or animated imagery.

### Layout Upgrades
- **Broken grid / asymmetry.** Elements that deliberately ignore column structure.
- **Whitespace maximization.** Aggressive use of negative space.
- **Parallax card stacks.** Sections that stick and stack over each other during scroll.
- **Split-screen scroll.** Two halves sliding in opposite directions.

### Motion Upgrades
- **Smooth scroll with inertia.** Decouple scrolling from browser defaults.
- **Staggered entry.** Elements cascade in with slight delays.
- **Spring physics.** Replace linear easing with spring-based motion.
- **Scroll-driven reveals.** Content entering through expanding masks, wipes, or draw-on SVG paths.

### Surface Upgrades
- **True glassmorphism.** Add a 1px inner border and inner shadow for edge refraction.
- **Spotlight borders.** Card borders that illuminate dynamically under the cursor.
- **Grain and noise overlays.** A fixed, pointer-events-none overlay with subtle noise.
- **Colored, tinted shadows.** Shadows that carry the hue of the background.

## Fix Priority
Apply changes in this order for maximum visual impact with minimum risk:

1. **Font swap** — biggest instant improvement, lowest risk
2. **Color palette cleanup** — remove clashing or oversaturated colors
3. **Hover and active states** — makes the interface feel alive
4. **Layout and spacing** — proper grid, max-width, consistent padding
5. **Replace generic components** — swap cliche patterns for modern alternatives
6. **Add loading, empty, and error states** — makes it feel finished
7. **Polish typography scale and spacing** — the premium final touch

## Rules
- Work with the existing tech stack. Do not migrate frameworks or styling libraries.
- Do not break existing functionality. Test after every change.
- Before importing any new library, check the project's dependency file first.
- If the project uses Tailwind, check the version (v3 vs v4) before modifying config.
- If the project has no framework, use vanilla CSS.
- Keep changes reviewable and focused. Small, targeted improvements over big rewrites.
