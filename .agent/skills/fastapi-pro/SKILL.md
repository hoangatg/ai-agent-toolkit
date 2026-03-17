---
name: fastapi-pro
description: FastAPI development expertise. Async APIs, dependency injection, Pydantic v2, middleware, and production patterns. Use when building high-performance Python APIs.
---

# FastAPI Pro

> Modern Python APIs — fast to write, fast to run.

---

## 1. Architecture Decisions

### When to Use FastAPI

| Factor | FastAPI | Django | Flask |
|--------|---------|--------|-------|
| **Performance** | ✅ Async, fast | ❌ Sync by default | ❌ Sync |
| **Type safety** | ✅ Pydantic built-in | ⚠️ Add-on | ❌ Manual |
| **Auto docs** | ✅ Swagger + ReDoc | ❌ Add-on | ❌ Add-on |
| **Learning curve** | Low-Medium | Medium-High | Low |
| **Ecosystem** | Growing | Mature | Mature |

---

## 2. Project Structure

```
app/
├── main.py          # FastAPI app, startup
├── api/
│   ├── routes/      # Route handlers
│   └── deps.py      # Dependencies
├── core/
│   ├── config.py    # Settings (pydantic-settings)
│   └── security.py  # Auth logic
├── models/          # SQLAlchemy/DB models
├── schemas/         # Pydantic schemas
├── services/        # Business logic
└── tests/
```

---

## 3. Pydantic v2 Patterns

| Feature | Usage |
|---------|-------|
| **BaseModel** | Request/response schemas |
| **Field validators** | Custom validation logic |
| **model_validator** | Cross-field validation |
| **Settings** | Environment config with `.env` |
| **Computed fields** | Derived values |
| **Strict mode** | No type coercion |

---

## 4. Dependency Injection

### DI Patterns

| Pattern | Use Case |
|---------|----------|
| **Function deps** | DB session, current user |
| **Class deps** | Configurable, stateful |
| **Yield deps** | Resource cleanup (DB, files) |
| **Nested deps** | Composition (auth → user → permissions) |

### Principles

| Principle | Application |
|-----------|-------------|
| **Single responsibility** | One dep, one concern |
| **Testable** | Override deps in tests |
| **Cacheable** | `use_cache=True` for expensive |
| **Async-friendly** | Use `async def` for IO deps |

---

## 5. Async Patterns

| Pattern | When |
|---------|------|
| **async def** | IO-bound routes (DB, HTTP calls) |
| **def** (sync) | CPU-bound, blocking libraries |
| **Background tasks** | Fire-and-forget after response |
| **asyncio.gather** | Parallel async operations |

---

## 6. Security

| Feature | Implementation |
|---------|---------------|
| **JWT auth** | OAuth2PasswordBearer + jose |
| **API keys** | Header-based authentication |
| **CORS** | CORSMiddleware with specific origins |
| **Rate limiting** | slowapi or custom middleware |
| **Input validation** | Pydantic does this automatically |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Business logic in routes | Separate service layer |
| Sync DB calls in async routes | Use async DB drivers |
| Skip Pydantic schemas | Always validate input/output |
| Global state | Dependency injection |
| Ignore startup/shutdown | Use lifespan events |

---

> **Remember:** FastAPI's power is in Pydantic + async + dependency injection. Master these three, and your APIs will be fast, safe, and maintainable.
