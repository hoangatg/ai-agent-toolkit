---
name: microservices-patterns
description: Microservices architecture patterns. Service decomposition, communication, resilience, and data management. Use when designing or refactoring distributed systems.
---

# Microservices Patterns

> Break systems apart. Keep them working together.

---

## 1. Decomposition Strategies

### When to Use Microservices

| Signal | Monolith | Microservices |
|--------|----------|---------------|
| Team size | < 10 | 10+ (multiple teams) |
| Deploy frequency | Weekly | Multiple times/day |
| Scaling needs | Uniform | Different per component |
| Tech diversity | One stack | Multiple stacks needed |

### Decomposition Approaches

| Approach | Method |
|----------|--------|
| **By business domain** | Bounded contexts (DDD) |
| **By subdomain** | Core, supporting, generic |
| **Strangler fig** | Gradually extract from monolith |
| **By data ownership** | Each service owns its data |

---

## 2. Communication Patterns

### Sync vs Async

| Pattern | Use When | Protocol |
|---------|----------|----------|
| **Request/Response** | Need immediate answer | HTTP, gRPC |
| **Event-driven** | Fire-and-forget, decoupling | Kafka, RabbitMQ, SQS |
| **Command** | Trigger action, need ack | Queue + response |
| **Query** | Read data, no side effects | HTTP GET, GraphQL |

### API Gateway

| Responsibility | Implementation |
|---------------|----------------|
| Routing | Path-based routing to services |
| Auth | JWT validation, API keys |
| Rate limiting | Per-client quotas |
| Aggregation | Combine multiple service responses |

---

## 3. Data Management

### Database per Service

| Principle | Application |
|-----------|-------------|
| **Own your data** | Each service has its own DB |
| **No shared databases** | Coupling killer |
| **Saga pattern** | Distributed transactions |
| **Event sourcing** | Audit trail, temporal queries |
| **CQRS** | Separate read/write models |

### Saga Patterns

| Type | How It Works |
|------|-------------|
| **Choreography** | Services react to events |
| **Orchestration** | Central coordinator manages steps |

---

## 4. Resilience Patterns

| Pattern | Purpose |
|---------|---------|
| **Circuit breaker** | Stop cascading failures |
| **Retry + backoff** | Handle transient errors |
| **Timeout** | Don't wait forever |
| **Bulkhead** | Isolate failure domains |
| **Fallback** | Graceful degradation |

---

## 5. Observability

| Pillar | Must Have |
|--------|----------|
| **Distributed tracing** | Follow requests across services |
| **Centralized logging** | Correlated logs, structured format |
| **Health checks** | Liveness + readiness per service |
| **Metrics** | RED method (Rate, Errors, Duration) |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Distributed monolith | True independence per service |
| Shared database | Database per service |
| Sync everywhere | Async by default, sync when needed |
| No service contracts | API versioning and schemas |
| Skip observability | Tracing from day 1 |

---

> **Remember:** Microservices solve organizational scaling, not technical complexity. Start with a well-structured monolith, extract when justified.
