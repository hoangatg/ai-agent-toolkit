---
name: redis-caching
description: Redis patterns, caching strategies, pub/sub, and session management. Use when implementing caching, rate limiting, or real-time features with Redis.
---

# Redis Caching

> The in-memory data structure store that makes everything faster.

---

## 1. Caching Strategies

| Strategy | How It Works | Use Case |
|----------|-------------|----------|
| **Cache-Aside** | App checks cache → miss → fetch DB → store cache | General purpose |
| **Write-Through** | Write to cache + DB simultaneously | Consistency critical |
| **Write-Behind** | Write to cache → async write to DB | High write throughput |
| **Read-Through** | Cache auto-fetches on miss | Transparent caching |

---

## 2. Data Structures

| Structure | Use Case |
|-----------|----------|
| **String** | Simple key-value, counters |
| **Hash** | Object storage, user profiles |
| **List** | Queues, timelines, logs |
| **Set** | Unique collections, tags |
| **Sorted Set** | Leaderboards, rate limiting |
| **Stream** | Event sourcing, message queue |
| **HyperLogLog** | Cardinality estimation |

---

## 3. Key Design

| Principle | Example |
|-----------|---------|
| **Namespaced** | `user:1234:profile` |
| **Hierarchical** | `app:module:entity:id` |
| **Versioned** | `v2:user:1234:cache` |
| **TTL always** | Every key should expire |
| **Predictable** | Same input → same key |

---

## 4. Common Patterns

### Rate Limiting

| Algorithm | Method |
|-----------|--------|
| **Fixed window** | INCR + EXPIRE |
| **Sliding window** | Sorted Set + timestamp |
| **Token bucket** | Script-based atomic |

### Session Management

| Principle | Application |
|-----------|-------------|
| **Store session data** | Hash per session ID |
| **TTL** | Auto-expire inactive sessions |
| **Secure ID** | Cryptographically random |
| **Minimal data** | Only what's needed server-side |

### Pub/Sub & Streams

| Feature | Pub/Sub | Streams |
|---------|---------|---------|
| **Persistence** | ❌ Fire-and-forget | ✅ Persisted |
| **Consumer groups** | ❌ | ✅ |
| **Replay** | ❌ | ✅ |
| **Best for** | Notifications | Event processing |

---

## 5. Performance

| Technique | Impact |
|-----------|--------|
| **Pipelining** | Batch multiple commands |
| **Connection pooling** | Reuse connections |
| **Lua scripts** | Atomic multi-step operations |
| **Cluster** | Horizontal scaling |
| **Memory policy** | `allkeys-lru` for cache nodes |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Cache without TTL | Always set expiry |
| Store large values (>1MB) | Keep values small |
| Use KEYS in production | Use SCAN for iteration |
| Single Redis for everything | Separate cache vs persistent |
| Ignore eviction policy | Configure maxmemory + policy |

---

> **Remember:** Redis is fast because it's simple. Use the right data structure for the right problem, always set TTL, and never treat it as a primary database.
