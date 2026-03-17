---
name: analytics-tracking
description: Analytics and conversion tracking. GA4, PostHog, event design, funnels, and data-driven decisions. Use when setting up analytics or optimizing conversion funnels.
---

# Analytics Tracking

> You can't improve what you don't measure — but measure what matters, not everything.

---

## 1. Analytics Strategy

### What to Track

| Level | Metrics |
|-------|---------|
| **Business** | Revenue, MRR, churn rate |
| **Product** | DAU/WAU/MAU, activation rate |
| **Feature** | Adoption, usage frequency |
| **Technical** | Page load, errors, Core Web Vitals |

### Framework: AARRR

| Stage | Key Events |
|-------|-----------|
| **Acquisition** | `page_view`, `utm_source`, `referral` |
| **Activation** | `sign_up`, `onboarding_complete`, `first_value` |
| **Retention** | `login`, `feature_used`, `session_count` |
| **Revenue** | `plan_upgraded`, `payment_complete` |
| **Referral** | `invite_sent`, `share_clicked` |

---

## 2. Event Design

### Naming Convention

| Convention | Example |
|-----------|---------|
| **Object + Action** | `button_clicked`, `form_submitted` |
| **Consistent case** | `snake_case` for events |
| **Descriptive** | `checkout_started` not `click1` |
| **Grouped** | Prefix by feature: `auth_login`, `auth_signup` |

### Event Properties

| Property | Always Include |
|----------|---------------|
| **userId** | If authenticated |
| **timestamp** | When it happened |
| **context** | Page, source, device |
| **value** | Revenue, quantity if applicable |

---

## 3. Tool Selection

| Tool | Best For | Price |
|------|----------|-------|
| **GA4** | Web traffic, SEO | Free |
| **PostHog** | Product analytics, self-host | Free tier |
| **Mixpanel** | Event-based analysis | Free tier |
| **Amplitude** | Product intelligence | Free tier |
| **Plausible** | Privacy-focused, simple | Paid |

---

## 4. GA4 Setup

### Key Configurations

| Setting | What |
|---------|------|
| **Enhanced measurement** | Auto-track scrolls, outbound clicks |
| **Custom events** | Business-specific actions |
| **Conversions** | Mark key events as conversions |
| **Audiences** | Segment users for analysis |
| **Data retention** | Set to 14 months (max free) |

---

## 5. Funnel Analysis

### Building Effective Funnels

| Principle | Application |
|-----------|-------------|
| **Define steps** | Clear linear path to conversion |
| **Measure drop-off** | Where users leave |
| **Segment** | By source, device, cohort |
| **Time-bound** | Reasonable conversion window |
| **Act on data** | Optimize highest drop-off first |

---

## 6. Privacy & Compliance

| Regulation | Requirements |
|-----------|-------------|
| **GDPR** | Consent before tracking (EU) |
| **CCPA** | Opt-out option (California) |
| **Cookie law** | Cookie consent banner |

### Best Practices

- Use consent management platform
- Anonymize IP addresses
- Implement data deletion requests
- Document data flows

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Track everything | Track what drives decisions |
| Unnamed events (`event1`) | Descriptive naming convention |
| Skip consent | Implement proper consent flow |
| Vanity metrics only | Track actionable metrics |
| Set and forget | Regular analytics review (weekly) |

---

> **Remember:** Analytics should answer "why" not just "what." Set up tracking to support decisions, not just dashboards.
