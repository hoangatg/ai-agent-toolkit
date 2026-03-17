---
name: edge-computing
description: Edge computing patterns for Cloudflare Workers, Vercel Edge, Deno Deploy, and AWS Lambda@Edge. Use when building globally distributed, low-latency applications.
---

# Edge Computing

> Run code at the edge — closest to users. Sub-10ms cold starts, global distribution.

## Platform Comparison

| Platform | Runtime | Cold Start | Limits |
|----------|---------|------------|--------|
| **Cloudflare Workers** | V8 isolates | < 5ms | 128MB RAM |
| **Vercel Edge Functions** | V8 isolates | < 5ms | 128MB RAM |
| **Deno Deploy** | Deno | < 5ms | 512MB RAM |
| **AWS Lambda@Edge** | Node.js | 50-200ms | 128MB RAM |
| **Fastly Compute** | Wasm | < 1ms | 128MB RAM |

---

## Edge-Compatible Patterns

| Pattern | Description |
|---------|-------------|
| **KV Storage** | Key-value at the edge (Workers KV, Vercel KV) |
| **Edge Databases** | D1, Turso, PlanetScale, Neon serverless |
| **Streaming** | Response streaming with ReadableStream |
| **Geolocation** | Route by user location |
| **A/B Testing** | Feature flags at edge, zero client JS |

## Edge Constraints

- No Node.js APIs (fs, crypto, net)
- Limited execution time (30s-60s)
- No native modules
- Must use Web APIs (fetch, Request, Response)
- Use edge-compatible ORMs (Drizzle, Prisma Edge)
