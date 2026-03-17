---
name: api-rate-limiting
description: API rate limiting, throttling, and quota management patterns. Token bucket, sliding window, and distributed rate limiting. Use when protecting APIs from abuse and ensuring fair usage.
---

# API Rate Limiting

> Protect your APIs from abuse while ensuring fair usage for all consumers.

## Algorithm Comparison

| Algorithm | Description | Best For |
|-----------|-------------|----------|
| **Token Bucket** | Tokens refill at fixed rate | Burst-tolerant APIs |
| **Sliding Window** | Count requests in rolling window | Precise rate limiting |
| **Fixed Window** | Count per time interval | Simple implementation |
| **Leaky Bucket** | Process at constant rate | Smooth output rate |

---

## Implementation Patterns

### Headers (Standard)
```
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 42
X-RateLimit-Reset: 1626847200
Retry-After: 60
```

### Storage Options

| Storage | Latency | Distributed |
|---------|---------|-------------|
| In-memory | μs | ❌ Single server |
| Redis | ~1ms | ✅ |
| Cloudflare KV | ~10ms | ✅ Global |
| DynamoDB | ~5ms | ✅ |

### Rate Limit Strategies

| Strategy | Description |
|----------|-------------|
| **Per-User** | Limits per authenticated user |
| **Per-IP** | Limits per client IP |
| **Per-API-Key** | Limits per API key / tier |
| **Global** | Total requests across all clients |
| **Endpoint-specific** | Different limits per route |
