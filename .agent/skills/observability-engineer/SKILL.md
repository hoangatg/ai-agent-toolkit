---
name: observability-engineer
description: Comprehensive monitoring, logging, and alerting systems. Prometheus, Grafana, OpenTelemetry, and incident detection. Use when building production observability.
---

# Observability Engineer

> If you can't see it, you can't fix it. If you can't measure it, you can't improve it.

---

## 1. Three Pillars

| Pillar | Purpose | Tools |
|--------|---------|-------|
| **Metrics** | What's happening (numbers) | Prometheus, Datadog, CloudWatch |
| **Logging** | Why it happened (events) | ELK, Loki, CloudWatch Logs |
| **Tracing** | How it happened (flow) | Jaeger, Tempo, X-Ray |

---

## 2. Metrics Design

### RED Method (Services)

| Metric | Measures |
|--------|---------|
| **Rate** | Requests per second |
| **Errors** | Failed requests per second |
| **Duration** | Latency distribution (p50, p95, p99) |

### USE Method (Resources)

| Metric | Measures |
|--------|---------|
| **Utilization** | % time resource is busy |
| **Saturation** | Queue depth / backlog |
| **Errors** | Error count |

### Golden Signals

| Signal | Question |
|--------|----------|
| **Latency** | How long do requests take? |
| **Traffic** | How much demand? |
| **Errors** | What's failing? |
| **Saturation** | How full is the system? |

---

## 3. Logging Best Practices

| Principle | Application |
|-----------|-------------|
| **Structured** | JSON format, not free text |
| **Leveled** | DEBUG, INFO, WARN, ERROR, FATAL |
| **Contextual** | Include requestId, userId, traceId |
| **Sampling** | High-volume logs: sample, don't log all |
| **Retention** | Define tiered retention policies |

### What to Log

| ✅ Do Log | ❌ Don't Log |
|----------|-------------|
| Request/response metadata | Sensitive data (PII, secrets) |
| Error details with stack | Successful health checks |
| State transitions | Every database query |
| Authentication events | Request/response bodies (usually) |

---

## 4. Alerting Strategy

### Alert Design

| Principle | Application |
|-----------|-------------|
| **Symptom-based** | Alert on user impact, not causes |
| **Actionable** | Every alert must have a runbook |
| **Tiered severity** | P1 (page now) → P4 (review later) |
| **Low noise** | Tune to avoid alert fatigue |

### Severity Levels

| Level | Response | Channel |
|-------|----------|---------|
| **P1 Critical** | Wake someone up | PagerDuty, phone |
| **P2 High** | Fix during business hours | Slack urgent |
| **P3 Medium** | Fix this sprint | Ticket |
| **P4 Low** | Track and batch | Dashboard |

---

## 5. OpenTelemetry

| Component | Purpose |
|-----------|---------|
| **SDK** | Instrument your application |
| **Collector** | Receive, process, export telemetry |
| **Exporters** | Send to backends (Jaeger, Prometheus) |
| **Auto-instrumentation** | Zero-code instrumentation |

---

## 6. Dashboard Design

| Principle | Application |
|-----------|-------------|
| **Overview first** | High-level health at a glance |
| **Drill down** | Click through to details |
| **Time context** | Always show time range |
| **Annotations** | Mark deployments, incidents |
| **SLO tracking** | Error budget burn rate |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Alert on every error | Alert on user-facing symptoms |
| Unstructured logs | JSON with consistent fields |
| No correlation IDs | Trace ID in every log and span |
| Dashboard overload | One dashboard per service/domain |
| Monitor in production only | Observability in staging too |

---

> **Remember:** Observability is not about collecting data — it's about being able to answer questions you haven't thought of yet.
