---
name: shadcn-radix-ui
description: shadcn/ui and Radix UI component patterns. Accessible primitives, copy-paste components, and design system integration. Use when building React UIs with accessible, customizable components.
---

# shadcn/ui & Radix UI

> Beautifully designed components built on Radix UI primitives. Copy-paste, customize, own your code.

## Architecture

```
Radix UI Primitives (unstyled, accessible)
    └── shadcn/ui (styled with Tailwind CSS)
        └── Your Components (customized)
```

## Key Principles

- **Copy-paste, not dependency**: Components live in YOUR codebase
- **Accessible by default**: Built on Radix primitives (WAI-ARIA)
- **Customizable**: Full control over styles and behavior
- **Composable**: Combine primitives for complex UIs

---

## Component Categories

| Category | Components |
|----------|------------|
| **Layout** | Card, Separator, Sheet, Sidebar |
| **Forms** | Input, Select, Checkbox, Radio, Switch, Slider |
| **Feedback** | Alert, Toast, Progress, Skeleton |
| **Overlay** | Dialog, Drawer, Popover, Tooltip, DropdownMenu |
| **Data** | Table, DataTable, Calendar, Charts |
| **Navigation** | Tabs, Breadcrumb, Pagination, NavigationMenu |

---

## Best Practices

| Practice | Why |
|----------|-----|
| Use `cn()` utility | Merge Tailwind classes safely |
| Customize in your codebase | Don't modify node_modules |
| Use CSS variables for theming | Easy dark mode and brand colors |
| Compose with Radix primitives | Build custom components from accessible base |
