---
name: docker-expert
description: Container orchestration principles. Docker, multi-stage builds, Compose, image optimization, and security hardening. Use when containerizing applications or optimizing Docker workflows.
---

# Docker Expert

> Containers should be small, fast, and secure. Everything else is configuration.

---

## 1. Dockerfile Principles

### Multi-Stage Build Pattern

```
Stage 1: Build (heavy, all dependencies)
  └── Compile, test, build artifacts
Stage 2: Production (minimal, runtime only)
  └── Copy artifacts, set entrypoint
```

### Layer Optimization

| Principle | Application |
|-----------|-------------|
| **Order matters** | Least-changing layers first |
| **Combine RUN** | Reduce layers with `&&` |
| **Clean up** | Remove cache/temp in same layer |
| **Use .dockerignore** | Exclude node_modules, .git, etc. |

### Base Image Selection

| Need | Image | Size |
|------|-------|------|
| **Minimal** | `alpine`, `distroless` | 5-50MB |
| **Standard** | `slim` variants | 50-200MB |
| **Full** | `bullseye`, `bookworm` | 200MB+ |
| **Specific runtime** | `node:20-alpine`, `python:3.12-slim` | Varies |

---

## 2. Image Size Optimization

### Size Reduction Checklist

| Technique | Impact |
|-----------|--------|
| Multi-stage builds | 50-90% reduction |
| Alpine/slim base | 60-80% reduction |
| .dockerignore | Varies (often 50%+) |
| Remove dev dependencies | 20-40% reduction |
| Combine and clean RUN layers | 10-30% reduction |

---

## 3. Docker Compose Patterns

### Service Design

| Principle | Application |
|-----------|-------------|
| **One process per container** | Don't run nginx + app together |
| **Named volumes** | Persist data explicitly |
| **Health checks** | Define liveness probes |
| **Dependency order** | `depends_on` with conditions |
| **Environment files** | `.env` for secrets (not committed) |

### Networking

| Network Type | Use Case |
|-------------|----------|
| **Bridge** | Default, container-to-container |
| **Host** | Performance-critical, no isolation |
| **Overlay** | Multi-host (Swarm/K8s) |
| **None** | Maximum isolation |

---

## 4. Security Hardening

### Container Security

| Practice | Why |
|----------|-----|
| **Non-root user** | Limit blast radius |
| **Read-only filesystem** | Prevent tampering |
| **No new privileges** | Block privilege escalation |
| **Scan images** | Detect known CVEs |
| **Pin versions** | Reproducible builds |

### Secret Management

| ❌ Don't | ✅ Do |
|----------|-------|
| ENV vars in Dockerfile | Docker secrets or vault |
| Hardcode credentials | Mount at runtime |
| Build with secrets | Multi-stage, secrets in build stage only |

---

## 5. Performance

### Build Performance

| Technique | Effect |
|-----------|--------|
| **BuildKit** | Parallel builds, caching |
| **Cache mounts** | Persist package manager cache |
| **Layer ordering** | Dependencies before source code |
| **Multi-platform** | `--platform` for ARM/AMD64 |

### Runtime Performance

- Limit CPU and memory resources
- Use tmpfs for temporary storage
- Optimize health check intervals
- Use appropriate restart policies

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Use `latest` tag | Pin specific versions |
| Run as root | Create non-root user |
| Store data in containers | Use named volumes |
| One giant Dockerfile | Multi-stage builds |
| Ignore .dockerignore | Exclude build artifacts and deps |

---

> **Remember:** The best container is the smallest one that runs your app correctly. Every MB matters in production.
