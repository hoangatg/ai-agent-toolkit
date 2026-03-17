---
name: zod-validation
description: Zod schema validation patterns. Runtime type checking, form validation, API validation, and type inference. Use when implementing data validation in TypeScript applications.
---

# Zod Validation

> TypeScript-first schema validation with static type inference.

## Core Patterns

```typescript
import { z } from 'zod'

// Schema definition
const UserSchema = z.object({
  name: z.string().min(2).max(100),
  email: z.string().email(),
  age: z.number().int().positive().optional(),
  role: z.enum(['admin', 'user', 'editor']),
})

// Type inference
type User = z.infer<typeof UserSchema>

// Validation
const result = UserSchema.safeParse(data)
if (result.success) {
  // result.data is typed as User
}
```

---

## Use Cases

| Use Case | Pattern |
|----------|---------|
| **API validation** | Validate request body/params |
| **Form validation** | React Hook Form + Zod |
| **Environment vars** | `z.object({ PORT: z.coerce.number() })` |
| **Config files** | Validate JSON/YAML configs |
| **tRPC** | Input/output validation |

## Integration with Frameworks

| Framework | Integration |
|-----------|-------------|
| **React Hook Form** | `@hookform/resolvers/zod` |
| **Next.js** | Server Actions validation |
| **tRPC** | Input/output schemas |
| **Express** | Middleware validation |
| **Hono** | `@hono/zod-validator` |
