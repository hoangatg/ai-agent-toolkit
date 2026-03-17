---
name: event-sourcing-architect
description: Event sourcing and CQRS architecture principles. Event stores, projections, snapshots, and eventual consistency. Use when building audit-heavy or temporal systems.
---

# Event Sourcing Architect

> Store what happened, not where you are. Reconstruct any state at any point in time.

---

## 1. Core Concepts

| Concept | Description |
|---------|-------------|
| **Event** | Immutable fact that happened (past tense) |
| **Event Store** | Append-only log of all events |
| **Projection** | Materialized view from events |
| **Snapshot** | Periodic state checkpoint |
| **CQRS** | Separate command (write) and query (read) models |

### When to Use

| ✅ Good Fit | ❌ Bad Fit |
|------------|-----------|
| Audit requirements | Simple CRUD apps |
| Temporal queries | Low complexity domains |
| Complex business logic | Real-time requirements only |
| Event-driven architecture | Team unfamiliar with patterns |

---

## 2. Event Design

### Event Principles

| Principle | Application |
|-----------|-------------|
| **Past tense naming** | `OrderPlaced`, not `PlaceOrder` |
| **Self-contained** | All relevant data included |
| **Immutable** | Never modify, only append |
| **Versioned** | Schema evolution support |

### Event Schema

```
Event {
  id: UUID
  type: "OrderPlaced"
  aggregateId: "order-123"
  version: 3
  timestamp: ISO-8601
  data: { ... }
  metadata: { userId, correlationId }
}
```

---

## 3. CQRS Pattern

### Separation

| Side | Responsibility | Model |
|------|---------------|-------|
| **Command** | Validate + write events | Domain model (aggregates) |
| **Query** | Read optimized views | Projections (denormalized) |

### Benefits

- Read and write scale independently
- Optimized models for each use case
- Multiple read models from same events
- Clear separation of concerns

---

## 4. Projections

| Type | Use Case |
|------|----------|
| **Synchronous** | Strong consistency needed |
| **Asynchronous** | Performance, eventual consistency |
| **Catch-up** | Rebuild from event history |

### Design Principles

- One projection per read use case
- Idempotent event handlers
- Track last processed event position
- Rebuild capability is mandatory

---

## 5. Snapshots

### When to Snapshot

```
No snapshot → replay all events (slow for long-lived aggregates)
With snapshot → load snapshot + replay events after snapshot
```

| Strategy | Trigger |
|----------|---------|
| **Every N events** | After 100-1000 events |
| **Time-based** | Every hour/day |
| **On demand** | When performance degrades |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Mutable events | Append-only, immutable |
| Events as commands | Events record what happened |
| Delete events | Use compensating events |
| One big projection | Focused projection per query |
| Skip versioning | Plan for schema evolution |

---

> **Remember:** Event sourcing trades write simplicity for read flexibility. You can always answer "what happened?" — build read models for "what is?".
