---
name: domain-driven-design
description: Domain-Driven Design principles. Strategic and tactical patterns, bounded contexts, aggregates, and ubiquitous language. Use when modeling complex business domains.
---

# Domain-Driven Design

> Let the business domain drive your software design, not the other way around.

---

## 1. Strategic Design

### Core Concepts

| Concept | Purpose |
|---------|---------|
| **Ubiquitous Language** | Shared vocabulary between dev and business |
| **Bounded Context** | Clear boundary where a model applies |
| **Context Map** | How contexts relate to each other |
| **Subdomain** | Business capability classification |

### Subdomain Types

| Type | Characteristics | Investment |
|------|----------------|-----------|
| **Core** | Competitive advantage | Maximum |
| **Supporting** | Necessary but not differentiating | Moderate |
| **Generic** | Common across industries | Minimum (buy/outsource) |

---

## 2. Context Mapping

### Relationship Patterns

| Pattern | Relationship |
|---------|-------------|
| **Shared Kernel** | Two contexts share a subset |
| **Customer-Supplier** | Upstream serves downstream |
| **Conformist** | Downstream conforms to upstream |
| **Anti-Corruption Layer** | Translation between contexts |
| **Open Host Service** | Public API for consumers |
| **Published Language** | Standard data format |

---

## 3. Tactical Patterns

### Building Blocks

| Pattern | Purpose | Rule |
|---------|---------|------|
| **Entity** | Identity matters | Has unique ID, mutable |
| **Value Object** | Value matters | Immutable, no ID |
| **Aggregate** | Consistency boundary | One root, transactional |
| **Repository** | Persistence abstraction | Per aggregate root |
| **Domain Event** | Something happened | Past tense, immutable |
| **Domain Service** | Stateless logic | Doesn't belong to entity |
| **Factory** | Complex creation | Encapsulate construction |

### Aggregate Design Rules

| Rule | Why |
|------|-----|
| One aggregate root | Single entry point |
| Small aggregates | Performance, concurrency |
| Reference by ID | Not by object reference |
| Eventual consistency | Between aggregates |
| Transactional within | Strong consistency inside |

---

## 4. Implementation Guidelines

### Layered Architecture

```
Presentation → Application → Domain → Infrastructure
                                ↑
                         (Dependencies point inward)
```

| Layer | Contains | Depends On |
|-------|----------|-----------|
| **Domain** | Entities, Value Objects, Events | Nothing external |
| **Application** | Use cases, orchestration | Domain |
| **Infrastructure** | DB, APIs, frameworks | Application, Domain |
| **Presentation** | UI, Controllers | Application |

---

## 5. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Anemic domain model | Rich domain with behavior |
| CRUD-driven design | Behavior-driven design |
| One model for everything | Bounded contexts per domain |
| Technical-first naming | Ubiquitous language |
| Big aggregates | Small, focused aggregates |

---

> **Remember:** DDD is about understanding the business first, modeling second, coding third. If you skip understanding, no pattern will save you.
