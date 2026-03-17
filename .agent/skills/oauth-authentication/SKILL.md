---
name: oauth-authentication
description: Authentication and authorization patterns. OAuth 2.0, JWT, SSO, RBAC, and session management. Use when implementing user authentication or access control.
---

# OAuth & Authentication

> Know who they are. Control what they can do. Do it securely.

---

## 1. Authentication Methods

| Method | Best For | Complexity |
|--------|----------|-----------|
| **Session + Cookie** | Server-rendered apps (Next.js, Rails) | Low |
| **JWT (stateless)** | SPAs, mobile apps, microservices | Medium |
| **OAuth 2.0** | Third-party login (Google, GitHub) | Medium |
| **Passkeys/WebAuthn** | Passwordless, highest security | High |
| **Magic Link** | Email-based, no password | Low |

---

## 2. OAuth 2.0 Flows

| Flow | Use Case | Security |
|------|----------|----------|
| **Authorization Code + PKCE** | Web apps, mobile apps | ✅ Most secure |
| **Client Credentials** | Machine-to-machine | ✅ Server only |
| **Device Code** | TVs, CLI tools | ✅ |
| ~~Implicit~~ | ❌ **Deprecated** | ❌ Don't use |
| ~~Password Grant~~ | ❌ **Deprecated** | ❌ Don't use |

> **Rule:** Always use Authorization Code + PKCE for user-facing apps.

---

## 3. JWT Best Practices

### Token Design

| Aspect | Recommendation |
|--------|---------------|
| **Access token** | Short-lived (15 min) |
| **Refresh token** | Long-lived (7-30 days), rotated |
| **Algorithm** | RS256 (asymmetric) for distributed |
| **Claims** | Minimal: sub, iat, exp, roles |
| **Storage** | HttpOnly cookie (web), secure storage (mobile) |

### Token Security

| ❌ Don't | ✅ Do |
|----------|-------|
| Store in localStorage | HttpOnly, Secure, SameSite cookies |
| Long-lived access tokens | Short access + refresh rotation |
| Send in URL params | Send in Authorization header |
| Encode sensitive data | Minimal claims, lookup DB for details |

---

## 4. Authorization Patterns

| Pattern | Best For |
|---------|----------|
| **RBAC** (Role-Based) | Simple: admin, editor, viewer |
| **ABAC** (Attribute-Based) | Complex: department + level + resource |
| **ReBAC** (Relationship-Based) | Social: "friends of friends" (Zanzibar) |
| **ACL** | File/resource-level permissions |

---

## 5. Auth Providers

| Provider | Type | Best For |
|----------|------|----------|
| **NextAuth.js (Auth.js)** | Library | Next.js apps |
| **Clerk** | Service | React, fastest setup |
| **Supabase Auth** | BaaS | Full-stack with Supabase |
| **Firebase Auth** | BaaS | Mobile + web |
| **Auth0** | Enterprise | B2B, SAML, SSO |
| **Keycloak** | Self-hosted | Enterprise, custom |

---

## 6. Session Management

| Principle | Application |
|-----------|-------------|
| **Secure cookies** | HttpOnly, Secure, SameSite=Lax |
| **Session rotation** | New session ID on login |
| **Idle timeout** | Expire after inactivity |
| **Absolute timeout** | Max session lifetime |
| **Revocation** | Server-side session store for logout |

---

## 7. Multi-Factor Authentication (MFA)

| Factor | Method |
|--------|--------|
| **Something you know** | Password |
| **Something you have** | TOTP (Authenticator app), SMS |
| **Something you are** | Biometrics (Face ID, fingerprint) |

---

## 8. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Roll your own crypto | Use established libraries |
| Store passwords in plain text | bcrypt/argon2 + salt |
| Trust client-side auth | Always verify server-side |
| Same secret for all environments | Rotate secrets per environment |
| Skip HTTPS | TLS everywhere |

---

> **Remember:** Authentication is not authorization. Knowing WHO someone is doesn't mean they can do EVERYTHING. Always check both.
