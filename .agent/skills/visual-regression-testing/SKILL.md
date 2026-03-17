---
name: visual-regression-testing
description: Visual regression testing patterns. Playwright screenshots, Chromatic, Percy, and pixel-by-pixel comparison. Use when ensuring UI changes don't break existing visual layouts.
---

# Visual Regression Testing

> Catch unintended UI changes before users do. Screenshot comparison for every PR.

## Tool Comparison

| Tool | Type | CI Integration | Cost |
|------|------|---------------|------|
| **Playwright Screenshots** | Open source | Any CI | Free |
| **Chromatic** | Cloud service | GitHub/GitLab | Freemium |
| **Percy** | Cloud service | Any CI | Paid |
| **BackstopJS** | Open source | Any CI | Free |
| **Loki** | Storybook-based | Any CI | Free |

---

## Playwright Visual Testing

```typescript
import { test, expect } from '@playwright/test'

test('homepage visual', async ({ page }) => {
  await page.goto('/')
  await expect(page).toHaveScreenshot('homepage.png', {
    maxDiffPixels: 100,
    threshold: 0.2,
  })
})
```

## Best Practices

| Practice | Why |
|----------|-----|
| Stable test environment | Prevent flaky snapshots |
| Mask dynamic content | Dates, avatars, ads change |
| Test multiple viewports | Mobile, tablet, desktop |
| Use threshold | Allow anti-aliasing differences |
| Review in CI | Approve/reject visual changes in PRs |
