---
name: graphql-expert
description: GraphQL schema design, resolvers, federation, and client patterns. Apollo, urql, and Relay. Use when building or consuming GraphQL APIs.
---

# GraphQL Expert

> Ask for exactly what you need. Nothing more, nothing less.

---

## 1. Schema Design

### Design Principles

| Principle | Application |
|-----------|-------------|
| **Domain-first** | Model business entities, not database tables |
| **Naming** | PascalCase types, camelCase fields |
| **Nullability** | Non-null by default, nullable when uncertain |
| **Pagination** | Cursor-based (Relay spec) for lists |
| **Versioning** | Evolve schema, don't version |

### Type Patterns

| Type | Use Case |
|------|----------|
| **Object** | Domain entities |
| **Input** | Mutation arguments |
| **Interface** | Shared fields across types |
| **Union** | "One of" return types |
| **Enum** | Fixed set of values |
| **Scalar** | Custom types (DateTime, URL, JSON) |

---

## 2. Resolver Patterns

| Pattern | Purpose |
|---------|---------|
| **DataLoader** | Batch + cache N+1 queries |
| **Field resolver** | Lazy load nested data |
| **Context** | Share auth, DB, services |
| **Middleware** | Auth, logging, validation |

### N+1 Problem

```
❌ Without DataLoader: 1 query + N queries
✅ With DataLoader: 1 query + 1 batched query
```

---

## 3. Client Patterns

| Client | Best For |
|--------|----------|
| **Apollo Client** | Full-featured, React ecosystem |
| **urql** | Lightweight, framework-agnostic |
| **Relay** | Facebook-scale, compiler-driven |
| **graphql-request** | Minimal, no framework |

### Client Cache

| Strategy | When |
|----------|------|
| **Normalized cache** | Complex relationships |
| **Document cache** | Simple queries |
| **No cache** | Real-time/frequently changing |

---

## 4. Federation (Microservices)

| Concept | Purpose |
|---------|---------|
| **Subgraph** | Domain-specific GraphQL service |
| **Supergraph** | Unified schema from subgraphs |
| **Gateway** | Routes queries to subgraphs |
| **@key** | Entity identity across services |
| **@external** | Reference fields from other services |

---

## 5. Security

| Threat | Defense |
|--------|---------|
| **Query depth** | Max depth limit (e.g., 10) |
| **Query complexity** | Cost analysis per field |
| **Introspection** | Disable in production |
| **Batching attacks** | Limit batch size |
| **Authorization** | Field-level auth in resolvers |

---

## 6. Subscriptions

| Transport | Use Case |
|-----------|----------|
| **WebSocket** | Real-time updates |
| **SSE** | Simpler, HTTP-based |
| **Polling** | Fallback, wider support |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Expose DB schema as API | Design domain-first schema |
| Ignore N+1 queries | Use DataLoader everywhere |
| Allow unlimited depth | Set query complexity limits |
| Over-fetch in resolvers | Resolve only requested fields |
| REST-style naming | Graph thinking (nodes + edges) |

---

> **Remember:** GraphQL is not REST with a different syntax. Think in graphs — entities connected by relationships.
