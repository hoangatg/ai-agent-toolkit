---
name: stripe-integration
description: Stripe payment integration. Checkout, subscriptions, webhooks, and billing management. Use when implementing payments or monetization in applications.
---

# Stripe Integration

> Get paid reliably. Stripe handles the hard parts of payments.

---

## 1. Integration Patterns

| Pattern | Best For | Complexity |
|---------|----------|-----------|
| **Checkout Session** | Quick setup, hosted page | Low |
| **Payment Intent** | Custom UI, full control | Medium |
| **Subscription** | Recurring billing | Medium |
| **Billing Portal** | Self-service management | Low |
| **Connect** | Marketplace, split payments | High |

---

## 2. Checkout Flow

### Server-Side Flow

```
Client Request → Create Checkout Session → Redirect to Stripe
  → Customer Pays → Webhook: checkout.session.completed
  → Fulfill Order → Show Success Page
```

### Key Decisions

| Decision | Options |
|----------|---------|
| **Hosted vs Embedded** | Hosted (simpler) vs Elements (custom UI) |
| **Payment methods** | Cards, Apple Pay, Google Pay, SEPA |
| **Tax handling** | Stripe Tax, manual, or external |
| **Trial periods** | Free trial before charging |

---

## 3. Subscription Management

### Subscription Lifecycle

```
Created → Active → [Past Due → Unpaid → Canceled]
                  → [Paused]
                  → [Canceled at period end]
```

### Key Webhooks

| Event | Action |
|-------|--------|
| `checkout.session.completed` | Provision access |
| `invoice.payment_succeeded` | Confirm renewal |
| `invoice.payment_failed` | Notify user, retry |
| `customer.subscription.deleted` | Revoke access |
| `customer.subscription.updated` | Update plan details |

---

## 4. Webhook Security

### Verification Principles

| Principle | Implementation |
|-----------|---------------|
| **Verify signature** | Use Stripe SDK, never skip |
| **Idempotent handling** | Deduplicate by event ID |
| **Acknowledge fast** | Return 200 immediately, process async |
| **Retry handling** | Stripe retries for 3 days |
| **Event ordering** | Don't assume order, check timestamps |

---

## 5. Security

| Practice | Implementation |
|----------|---------------|
| **Server-side only** | Secret key never on client |
| **Webhook verification** | Validate every webhook signature |
| **PCI compliance** | Use Stripe.js/Elements (SAQ A) |
| **Idempotency keys** | Prevent duplicate charges |
| **Metadata** | Track internal IDs, don't store card data |

---

## 6. Testing

| Tool | Purpose |
|------|---------|
| **Test mode** | Test API keys with `sk_test_` |
| **Test cards** | `4242424242424242` for success |
| **Stripe CLI** | `stripe listen --forward-to` for webhooks |
| **Test clocks** | Simulate subscription time progression |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Store card numbers | Use Stripe.js + tokenization |
| Skip webhook verification | Always verify signatures |
| Fulfill before payment confirmed | Wait for webhook confirmation |
| Client-side secret key | Server-side only, use publishable key on client |
| Trust client-side price | Server creates sessions with actual prices |

---

> **Remember:** Never trust the client for prices or payment status. The server creates the session, Stripe processes the payment, and webhooks confirm the result.
