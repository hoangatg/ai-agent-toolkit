---
name: supabase-firebase
description: Backend-as-a-Service patterns. Supabase and Firebase for auth, database, storage, and real-time. Use when building apps with BaaS platforms.
---

# Supabase & Firebase

> Skip the backend boilerplate. Ship faster with managed services.

---

## 1. Platform Selection

| Factor | Supabase | Firebase |
|--------|----------|---------|
| **Database** | PostgreSQL (SQL) | Firestore (NoSQL) |
| **Auth** | Built-in, OAuth, magic links | Built-in, OAuth, phone |
| **Real-time** | Postgres changes, broadcast | Firestore listeners |
| **Storage** | S3-compatible | GCS-based |
| **Functions** | Edge Functions (Deno) | Cloud Functions (Node.js) |
| **Self-host** | ✅ Docker | ❌ Google only |
| **Pricing** | Generous free tier | Pay-as-you-go (can spike) |
| **Best for** | SQL lovers, open-source | Mobile apps, Google ecosystem |

---

## 2. Supabase Patterns

### Database (PostgreSQL)

| Feature | Use Case |
|---------|----------|
| **Row Level Security** | Per-user data access |
| **Realtime** | Subscribe to DB changes |
| **Edge Functions** | Server logic (Deno runtime) |
| **PostgREST** | Auto-generated REST API |
| **Database Functions** | Business logic in SQL |

### RLS Design

| Principle | Application |
|-----------|-------------|
| **Enable on all tables** | Default deny |
| **Policy per operation** | SELECT, INSERT, UPDATE, DELETE |
| **Use auth.uid()** | Match current user |
| **Test policies** | Verify with different users |

---

## 3. Firebase Patterns

### Firestore Data Modeling

| Pattern | Use Case |
|---------|----------|
| **Subcollections** | One-to-many (user → orders) |
| **Denormalization** | Read-heavy, embed data |
| **Collection groups** | Query across subcollections |

### Security Rules

| Principle | Application |
|-----------|-------------|
| **Default deny** | No access without explicit rule |
| **Validate writes** | Check data types and ranges |
| **Limit reads** | Don't expose all data |
| **Test rules** | Firebase Emulator Suite |

---

## 4. Auth Integration

### Supabase Auth

| Method | Implementation |
|--------|---------------|
| Email/Password | `supabase.auth.signUp()` |
| OAuth | `supabase.auth.signInWithOAuth()` |
| Magic Link | `supabase.auth.signInWithOtp()` |
| Row Level Security | Auto-injected `auth.uid()` |

### Firebase Auth

| Method | Implementation |
|--------|---------------|
| Email/Password | `createUserWithEmailAndPassword()` |
| OAuth | `signInWithPopup(provider)` |
| Phone | `signInWithPhoneNumber()` |
| Security Rules | `request.auth.uid` |

---

## 5. Cost Optimization

| Strategy | Platform |
|----------|----------|
| Use indexes wisely | Both |
| Minimize reads | Firebase (reads are charged) |
| Connection pooling | Supabase (pgBouncer) |
| Edge functions over cloud | Supabase |
| Firestore bundles | Firebase (offline cache) |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Skip security rules | RLS (Supabase) / Rules (Firebase) |
| Store secrets client-side | Edge/Cloud Functions only |
| Unbounded queries | Pagination, limits |
| Deep nesting (Firestore) | Flat structure, subcollections |
| Trust client data | Validate server-side |

---

> **Remember:** BaaS accelerates development but doesn't eliminate architecture thinking. Design your data model and security rules carefully — they're harder to change later.
