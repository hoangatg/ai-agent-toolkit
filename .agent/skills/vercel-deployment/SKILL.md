---
name: vercel-deployment
description: Vercel deployment patterns. Preview deployments, edge functions, ISR, analytics, and production optimization. Use when deploying Next.js or frontend apps on Vercel.
---

# Vercel Deployment

> Push to deploy. Preview everything. Ship with confidence.

---

## 1. Deployment Model

### How It Works

```
git push → Build → Preview URL → Review → Merge → Production
```

### Environment Types

| Environment | Trigger | URL |
|-------------|---------|-----|
| **Production** | Push to main | `app.com` |
| **Preview** | Push to any branch / PR | `branch-xxx.vercel.app` |
| **Development** | `vercel dev` | `localhost:3000` |

---

## 2. Configuration

### vercel.json Essentials

| Setting | Purpose |
|---------|---------|
| **redirects** | URL redirects (301/302) |
| **rewrites** | URL rewrites (proxy) |
| **headers** | Custom response headers |
| **functions** | Serverless function config |
| **crons** | Scheduled functions |

---

## 3. Edge & Serverless Functions

| Type | Runtime | Cold Start | Best For |
|------|---------|-----------|----------|
| **Serverless** | Node.js | ~250ms | API routes, heavy logic |
| **Edge** | V8 Isolates | ~0ms | Fast responses, middleware |

### Edge Function Limitations

- No Node.js APIs (fs, child_process)
- Limited execution time (30s)
- Smaller bundle size
- Limited npm packages

---

## 4. Caching & ISR

### Incremental Static Regeneration

| Pattern | Use Case |
|---------|----------|
| **Time-based** | `revalidate: 60` (every 60s) |
| **On-demand** | `revalidateTag()` / `revalidatePath()` |
| **Static** | Build-time only |

### Cache Headers

| Header | Effect |
|--------|--------|
| `s-maxage=60` | CDN cache for 60s |
| `stale-while-revalidate` | Serve stale while fetching new |
| `no-store` | Never cache |

---

## 5. Performance

| Feature | Impact |
|---------|--------|
| **Edge Network** | Global CDN, close to users |
| **Image Optimization** | Auto `next/image` on edge |
| **Font Optimization** | `next/font` zero CLS |
| **Analytics** | Web Vitals tracking |
| **Speed Insights** | Real user monitoring |

---

## 6. Environment Variables

| Type | Scope |
|------|-------|
| **Production** | Only production deploys |
| **Preview** | Only preview deploys |
| **Development** | `vercel dev` only |
| **NEXT_PUBLIC_** | Exposed to browser |

### Security

| ❌ Don't | ✅ Do |
|----------|-------|
| `NEXT_PUBLIC_` for secrets | Server-side env only |
| Commit `.env.local` | Use Vercel dashboard |
| Same secrets all envs | Different per environment |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Deploy without preview | Always preview-test PRs |
| Ignore build logs | Check warnings, bundle size |
| Skip environment separation | Different env vars per stage |
| Long serverless functions | Keep under 10s, use edge when possible |
| Ignore Web Vitals | Monitor with Vercel Analytics |

---

> **Remember:** Vercel's power is in the Git workflow. Every branch is a preview, every merge is a deploy. Trust the system, optimize the code.
