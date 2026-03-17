---
name: golang-pro
description: Go development expertise. Concurrency patterns, error handling, project structure, and performance optimization. Use when building Go services, CLIs, or systems tools.
---

# Golang Pro

> Simple, fast, and concurrent. Go gets out of your way.

---

## 1. Project Structure

### Standard Layout

```
myapp/
├── cmd/           # Entry points
│   └── myapp/
│       └── main.go
├── internal/      # Private packages
│   ├── handler/
│   ├── service/
│   └── repository/
├── pkg/           # Public packages
├── api/           # API definitions (OpenAPI, proto)
├── go.mod
└── go.sum
```

---

## 2. Concurrency Patterns

### Pattern Selection

| Pattern | Use When |
|---------|----------|
| **Goroutine + channel** | Producer-consumer, pipeline |
| **WaitGroup** | Wait for N tasks to complete |
| **Mutex** | Protect shared state |
| **Context** | Cancellation, timeouts, values |
| **errgroup** | Concurrent tasks with error handling |
| **semaphore** | Limit concurrent goroutines |

### Channel Patterns

| Pattern | Description |
|---------|-------------|
| **Fan-out** | One producer, many consumers |
| **Fan-in** | Many producers, one consumer |
| **Pipeline** | Chain of processing stages |
| **Done channel** | Cancellation signal |

---

## 3. Error Handling

### Principles

| Principle | Application |
|-----------|-------------|
| **Explicit errors** | Return `error` as last return value |
| **Wrap with context** | `fmt.Errorf("parsing config: %w", err)` |
| **Custom errors** | Implement `error` interface |
| **errors.Is/As** | Type-safe error checking |
| **Don't panic** | Reserve for truly unrecoverable |

---

## 4. Interface Design

| Principle | Application |
|-----------|-------------|
| **Small interfaces** | 1-3 methods ideal |
| **Accept interfaces** | Function params as interfaces |
| **Return structs** | Function returns as concrete types |
| **Implicit implementation** | No `implements` keyword needed |
| **io.Reader/Writer** | Compose with standard interfaces |

---

## 5. Performance

| Technique | When |
|-----------|------|
| **sync.Pool** | Reduce GC pressure for temp objects |
| **Buffered channels** | Reduce goroutine blocking |
| **Strings.Builder** | Efficient string concatenation |
| **Pre-allocate slices** | `make([]T, 0, expectedCap)` |
| **pprof** | Profile CPU, memory, goroutines |
| **Benchmarks** | `func BenchmarkX(b *testing.B)` |

---

## 6. Testing

| Type | Tool |
|------|------|
| **Unit tests** | `testing` package, `_test.go` |
| **Table-driven** | Slice of test cases |
| **Mocks** | Interfaces + manual mocks |
| **Benchmarks** | `testing.B` |
| **Race detection** | `go test -race` |
| **Coverage** | `go test -cover` |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Goroutine leak | Always have exit path |
| Naked goroutine | Use errgroup or context |
| Ignore errors | Handle or wrap every error |
| Large interfaces | Small, focused interfaces |
| Global mutable state | Dependency injection |

---

> **Remember:** Go is opinionated for a reason. Embrace simplicity — if your code needs clever abstractions, you might be fighting the language.
