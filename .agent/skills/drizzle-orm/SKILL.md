---
name: drizzle-orm
description: Drizzle ORM patterns for TypeScript. Type-safe SQL queries, schema definitions, migrations, and relational queries. Use when building type-safe database layers in TypeScript projects.
---

# Drizzle ORM

> Type-safe SQL in TypeScript. If you know SQL, you know Drizzle.

## Why Drizzle?

| Feature | Prisma | Drizzle |
|---------|--------|---------|
| **Approach** | Schema-first, client gen | SQL-like API |
| **Bundle size** | Heavy (engine) | Lightweight (~30kb) |
| **SQL control** | Abstracted | Full SQL access |
| **Edge compatible** | Limited | Full support |
| **Type safety** | Schema-derived | Inferred from schema |

---

## Schema Definition

```typescript
import { pgTable, serial, text, timestamp } from 'drizzle-orm/pg-core'

export const users = pgTable('users', {
  id: serial('id').primaryKey(),
  name: text('name').notNull(),
  email: text('email').notNull().unique(),
  createdAt: timestamp('created_at').defaultNow(),
})
```

## Query Patterns

- **Select**: `db.select().from(users).where(eq(users.id, 1))`
- **Insert**: `db.insert(users).values({ name, email })`
- **Relations**: `db.query.users.findMany({ with: { posts: true } })`
- **Raw SQL**: `sql\`SELECT * FROM users WHERE id = ${id}\``

---

## Best Practices

| Practice | Why |
|----------|-----|
| Use `drizzle-kit` for migrations | Type-safe schema evolution |
| Infer types from schema | `typeof users.$inferSelect` |
| Use transactions | `db.transaction(async (tx) => { ... })` |
| Edge-ready | Works with D1, PlanetScale, Neon, Turso |
