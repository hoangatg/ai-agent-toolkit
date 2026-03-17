---
name: aws-serverless
description: AWS serverless architecture principles. Lambda, API Gateway, DynamoDB, S3, SAM/CDK patterns. Use when building serverless applications on AWS.
---

# AWS Serverless

> Pay for what you use. Scale to zero. Ship faster.

---

## 1. Serverless Architecture

### Core Services

| Service | Purpose | Use When |
|---------|---------|----------|
| **Lambda** | Compute | Event-driven functions |
| **API Gateway** | HTTP endpoints | REST/WebSocket APIs |
| **DynamoDB** | Database | Key-value, high throughput |
| **S3** | Storage | Files, static assets |
| **SQS** | Queue | Async processing |
| **SNS** | Pub/Sub | Fan-out notifications |
| **EventBridge** | Event bus | Cross-service events |
| **Step Functions** | Orchestration | Complex workflows |

---

## 2. Lambda Design Principles

### Function Design

| Principle | Application |
|-----------|-------------|
| **Single responsibility** | One function, one purpose |
| **Stateless** | No local state between invocations |
| **Idempotent** | Safe to retry |
| **Fast startup** | Minimize cold start impact |
| **Small package** | Only include what's needed |

### Cold Start Optimization

| Strategy | Impact |
|----------|--------|
| Smaller runtime (Node.js, Python) | Lower cold start |
| Minimize dependencies | Faster init |
| Provisioned concurrency | Eliminate cold starts |
| SnapStart (Java) | 10x faster Java cold starts |
| ARM (Graviton2) | 20% cheaper, similar performance |

### Memory & Timeout

```
Memory Decision:
├── CPU-bound → More memory = more CPU = faster
├── IO-bound → Minimum memory needed
└── Sweet spot: Profile and benchmark

Timeout Decision:
├── API response → 3-10 seconds max
├── Background processing → up to 15 minutes
└── Always set explicit timeout (never default)
```

---

## 3. API Gateway Patterns

### API Design

| Pattern | Use Case |
|---------|----------|
| **REST API** | Standard CRUD, caching |
| **HTTP API** | Simple proxy, lower cost |
| **WebSocket** | Real-time, chat, notifications |

### Best Practices

- Use request validation (models/schemas)
- Enable throttling and usage plans
- Implement API keys for external clients
- Use stages for dev/staging/prod
- Enable access logging

---

## 4. DynamoDB Patterns

### Data Modeling

| Pattern | Use Case |
|---------|----------|
| **Single table** | Related entities, access patterns known |
| **Multi-table** | Independent domains |
| **GSI overloading** | Multiple query patterns |

### Access Pattern Design

| Principle | Application |
|-----------|-------------|
| **Design for queries** | Know access patterns first |
| **Partition key** | High cardinality, even distribution |
| **Sort key** | Range queries, hierarchies |
| **GSI** | Alternative query patterns |
| **TTL** | Auto-expire old data |

---

## 5. Infrastructure as Code

### SAM vs CDK

| Factor | SAM | CDK |
|--------|-----|-----|
| **Learning curve** | Low | Medium |
| **Flexibility** | Template-based | Full programming language |
| **Local testing** | `sam local invoke` | Limited |
| **Best for** | Simple serverless | Complex architectures |

---

## 6. Security

| Layer | Practice |
|-------|----------|
| **IAM** | Least privilege per function |
| **VPC** | Only if accessing private resources |
| **Encryption** | At rest + in transit |
| **Secrets** | Parameter Store / Secrets Manager |
| **WAF** | On API Gateway for public APIs |

---

## 7. Cost Optimization

| Strategy | Savings |
|----------|---------|
| ARM/Graviton2 | 20% cheaper |
| Right-size memory | Pay only for what you need |
| Reserved capacity (DynamoDB) | Up to 77% |
| S3 Intelligent Tiering | Auto-optimize storage cost |
| Avoid over-provisioning | Use on-demand, scale naturally |

---

## 8. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Monolith in a Lambda | Small, focused functions |
| Sync calls between Lambdas | Use queues (SQS) or events |
| Store state in Lambda | Use DynamoDB, S3, or ElastiCache |
| Ignore cold starts | Optimize package size, use provisioned |
| Default IAM permissions | Least privilege per function |

---

> **Remember:** Serverless is not "no servers" — it's "not your problem." Focus on business logic, let AWS handle scaling.
