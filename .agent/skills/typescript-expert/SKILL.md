---
name: typescript-expert
description: Advanced TypeScript patterns and type system mastery. Generics, utility types, conditional types, and type-safe architecture. Use when writing complex TypeScript or designing type-safe APIs.
---

# TypeScript Expert

> Types are documentation that the compiler enforces.

---

## 1. Type System Mastery

### Utility Type Selection

| Need | Utility Type |
|------|-------------|
| Make all optional | `Partial<T>` |
| Make all required | `Required<T>` |
| Make all readonly | `Readonly<T>` |
| Pick specific keys | `Pick<T, K>` |
| Remove specific keys | `Omit<T, K>` |
| Extract from union | `Extract<T, U>` |
| Exclude from union | `Exclude<T, U>` |
| Get return type | `ReturnType<T>` |
| Get parameter types | `Parameters<T>` |
| Non-nullable | `NonNullable<T>` |
| Get awaited type | `Awaited<T>` |

---

## 2. Advanced Generics

### Constrained Generics

| Pattern | Use When |
|---------|----------|
| `<T extends object>` | Must be object type |
| `<T extends string>` | String literal types |
| `<T extends keyof U>` | Key of another type |
| `<T extends (...args) => any>` | Must be function |

### Generic Inference

| Principle | Application |
|-----------|-------------|
| **Infer from usage** | Let TS infer when possible |
| **Constrain, don't assert** | Use `extends`, not `as` |
| **Default types** | `<T = string>` for convenience |
| **Multiple generics** | `<TInput, TOutput>` when needed |

---

## 3. Conditional Types

### Pattern

```
type Result<T> = T extends string ? StringResult : OtherResult
```

### Common Patterns

| Pattern | Purpose |
|---------|---------|
| `T extends infer U ? ... : ...` | Extract nested types |
| Distributive conditionals | Apply to each union member |
| Mapped conditional | Transform object types |
| Template literal types | String manipulation at type level |

---

## 4. Type-Safe Patterns

### Discriminated Unions

| Component | Purpose |
|-----------|---------|
| **Tag field** | Common literal field for discrimination |
| **Exhaustive check** | `never` for unhandled cases |
| **Type narrowing** | Automatic narrowing in switch/if |

### Branded Types

| Use Case | Pattern |
|----------|---------|
| Prevent ID mixing | `type UserId = string & { _brand: 'UserId' }` |
| Unit safety | `type Pixels = number & { _brand: 'Pixels' }` |
| Validation proof | `type ValidEmail = string & { _brand: 'ValidEmail' }` |

---

## 5. Strict Mode Best Practices

| Flag | Effect |
|------|--------|
| `strict: true` | Enable all strict checks |
| `noUncheckedIndexedAccess` | Array/object index returns `T \| undefined` |
| `exactOptionalPropertyTypes` | Distinguish `undefined` from missing |
| `noPropertyAccessFromIndexSignature` | Force bracket notation for dynamic keys |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| `any` everywhere | `unknown` + type guards |
| Type assertions (`as`) | Proper type narrowing |
| `@ts-ignore` | Fix the type issue |
| `interface` for everything | `type` for unions, `interface` for extension |
| Over-complex generics | Simple types first, generalize when needed |

---

> **Remember:** The best TypeScript code reads like documentation. If your types are too complex to understand, simplify your design.
