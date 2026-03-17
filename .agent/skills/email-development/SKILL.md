---
name: email-development
description: Email template development. HTML email, transactional emails, responsive design, and deliverability. Use when building email templates or marketing email systems.
---

# Email Development

> The most universal communication channel — and the hardest to style.

---

## 1. Email Types

| Type | Purpose | Tool |
|------|---------|------|
| **Transactional** | Receipts, password reset, notifications | SendGrid, Resend, AWS SES |
| **Marketing** | Newsletters, promotions, drip campaigns | Mailchimp, ConvertKit |
| **Automated** | Welcome series, abandoned cart | Customer.io, Braze |

---

## 2. HTML Email Development

### Key Constraints

| Constraint | Why |
|-----------|-----|
| **Table-based layout** | Outlook doesn't support flexbox/grid |
| **Inline styles** | Many clients strip `<style>` tags |
| **No JavaScript** | Completely stripped |
| **Limited CSS** | No media queries in many clients |
| **Image blocking** | Many clients block images by default |

### Modern Tools

| Tool | Purpose |
|------|---------|
| **React Email** | React components → HTML email |
| **MJML** | Responsive email framework |
| **Maizzle** | Tailwind CSS for email |
| **Litmus/Email on Acid** | Cross-client testing |
| **Resend** | Modern email API |

---

## 3. Responsive Design

### Strategy

| Approach | Support |
|----------|---------|
| **Fluid layout** | `width: 100%; max-width: 600px` |
| **Hybrid/spongy** | Works without media queries |
| **Media queries** | iOS Mail, Apple Mail, Gmail app |

### Email Width Standards

| Element | Width |
|---------|-------|
| **Max width** | 600px |
| **Content padding** | 20px sides |
| **CTA button** | Min 44px height (touch target) |
| **Font size** | Min 14px body, 22px+ heading |

---

## 4. Deliverability

### Authentication

| Protocol | Purpose |
|----------|---------|
| **SPF** | Authorize sending servers |
| **DKIM** | Sign emails cryptographically |
| **DMARC** | Policy for failed auth |
| **BIMI** | Brand logo in inbox |

### Best Practices

| Practice | Impact |
|----------|--------|
| **Clean list** | Remove bounces, unsubscribes |
| **Warm up IP** | Gradual volume increase |
| **Avoid spam triggers** | No ALL CAPS, excessive links |
| **Text version** | Always include plain text |
| **Unsubscribe** | One-click, visible link |

---

## 5. Transactional Email Patterns

### Common Templates

| Template | Key Elements |
|----------|-------------|
| **Welcome** | Greeting, next steps, CTA |
| **Password reset** | Secure link, expiry notice |
| **Order confirmation** | Order details, tracking |
| **Invoice** | Line items, totals, payment link |
| **Notification** | Brief message, action link |

---

## 6. Testing

| What to Test | Tool |
|-------------|------|
| **Rendering** | Litmus, Email on Acid |
| **Spam score** | Mail-tester.com |
| **Link validation** | Check all links work |
| **Dark mode** | Test in dark mode clients |
| **Accessibility** | Alt text, contrast, structure |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| CSS-only layout | Table-based (Outlook) |
| Image-only emails | Text + images, alt text |
| No plain text version | Always include |
| Skip authentication (SPF/DKIM) | Set up all three protocols |
| Send without testing | Test across top 5 clients |

---

> **Remember:** Email is 20 years behind the web in terms of CSS support. Design for the worst client (Outlook), and progressively enhance for the best (Apple Mail).
