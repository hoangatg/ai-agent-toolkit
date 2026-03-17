---
name: message-queues
description: Message queue and event streaming patterns. Kafka, RabbitMQ, SQS, and pub/sub architectures. Use when building async processing, event-driven systems, or decoupled services.
---

# Message Queues

> Decouple everything. Process asynchronously. Scale independently.

---

## 1. Technology Selection

| Technology | Best For | Model |
|-----------|----------|-------|
| **Kafka** | High throughput, event streaming | Log-based |
| **RabbitMQ** | Complex routing, traditional MQ | Broker-based |
| **AWS SQS** | Managed, serverless | Queue |
| **Redis Streams** | Lightweight, already using Redis | Log-based |
| **NATS** | Lightweight, cloud-native | Pub/Sub |
| **Google Pub/Sub** | Managed, GCP ecosystem | Topic-based |

---

## 2. Pattern Selection

| Pattern | Use When |
|---------|----------|
| **Point-to-Point** | One producer, one consumer |
| **Pub/Sub** | One event, many consumers |
| **Fan-Out** | Broadcast to all consumers |
| **Work Queue** | Distribute work across workers |
| **Request-Reply** | Async request with response |
| **Dead Letter Queue** | Handle failed messages |

---

## 3. Kafka Patterns

| Concept | Purpose |
|---------|---------|
| **Topics** | Category of messages |
| **Partitions** | Parallelism unit |
| **Consumer Groups** | Scale consumers independently |
| **Offset** | Track consumption position |
| **Compaction** | Keep latest per key |

### Partition Strategy

| Strategy | Use Case |
|----------|----------|
| **Key-based** | Order guarantee per entity |
| **Round-robin** | Even distribution |
| **Custom** | Business-specific routing |

---

## 4. Message Design

| Principle | Application |
|-----------|-------------|
| **Schema** | Use Avro/Protobuf, not raw JSON |
| **Idempotent** | Safe to process twice |
| **Self-contained** | Include all needed data |
| **Versioned** | Schema evolution support |
| **Small** | Reference large data, don't embed |

### Message Structure

```
{
  "id": "uuid",
  "type": "OrderCreated",
  "timestamp": "ISO-8601",
  "source": "order-service",
  "data": { ... },
  "metadata": { "correlationId", "version" }
}
```

---

## 5. Reliability Patterns

| Pattern | Purpose |
|---------|---------|
| **At-least-once** | May duplicate, never lose |
| **At-most-once** | May lose, never duplicate |
| **Exactly-once** | Kafka transactions (complex) |
| **Outbox pattern** | DB + queue atomicity |
| **Retry + DLQ** | Handle poison messages |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Synchronous over queues | Use queues for async only |
| Huge messages (>1MB) | Reference pattern for large data |
| Ignore ordering | Design for out-of-order |
| No dead letter queue | Always handle failures |
| Tight coupling to broker | Abstract behind interface |

---

> **Remember:** Message queues solve coupling, not speed. If you need sync response, use HTTP. Queues are for "do this eventually, reliably."
