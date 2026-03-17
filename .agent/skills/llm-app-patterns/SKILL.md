---
name: llm-app-patterns
description: Production-ready LLM application patterns. Streaming, caching, rate limiting, fallbacks, cost optimization, and observability. Use when building apps powered by LLMs.
---

# LLM App Patterns

> Ship LLM features that are fast, reliable, and cost-effective in production.

---

## 1. Architecture Decisions

### Integration Patterns

| Pattern | Use Case | Complexity |
|---------|----------|-----------|
| **Direct API** | Simple chat, single model | Low |
| **Gateway/Proxy** | Multi-model, rate limiting | Medium |
| **Queue-based** | High throughput, async tasks | Medium |
| **Agent framework** | Complex reasoning, tool use | High |

### Model Selection

| Factor | Consideration |
|--------|--------------|
| **Task complexity** | Simple → small model, complex → large |
| **Latency** | Streaming for UX, batch for backend |
| **Cost** | Per-token pricing, caching potential |
| **Privacy** | Cloud vs self-hosted |
| **Reliability** | Uptime SLA, fallback models |

---

## 2. Streaming Patterns

### When to Stream

| Scenario | Stream? |
|----------|---------|
| User-facing chat | ✅ Always |
| Background processing | ❌ Batch |
| Function calling | ⚠️ Depends on framework |
| Structured output | ❌ Wait for complete JSON |

### Implementation Principles

- Use Server-Sent Events (SSE) for web
- Buffer partial tokens for smooth display
- Handle stream interruptions gracefully
- Implement cancel/abort mechanisms

---

## 3. Caching Strategies

### Cache Layers

| Layer | What to Cache | TTL |
|-------|--------------|-----|
| **Prompt cache** | Full prompt → response | Hours-Days |
| **Semantic cache** | Similar queries → cached response | Hours |
| **Embedding cache** | Text → vector | Days-Weeks |
| **Response cache** | API response → result | Minutes-Hours |

### Cache Decision

```
Should you cache?
├── Deterministic output? → Exact match cache
├── Similar queries common? → Semantic cache
├── Expensive computation? → Result cache
└── High latency API? → Response cache
```

---

## 4. Error Handling & Resilience

### Failure Modes

| Failure | Strategy |
|---------|---------|
| Rate limited | Exponential backoff + queue |
| Timeout | Set deadline, return partial |
| Model down | Fallback to alternative model |
| Bad output | Retry with rephrased prompt |
| Token overflow | Truncate context intelligently |

### Fallback Chain

```
Primary Model (GPT-4o)
  └── Fallback 1 (Claude 3.5)
        └── Fallback 2 (Gemini Pro)
              └── Graceful degradation (cached/static)
```

---

## 5. Cost Optimization

### Cost Reduction Strategies

| Strategy | Savings | Trade-off |
|----------|---------|-----------|
| **Prompt caching** | 50-90% | Stale responses |
| **Model routing** | 40-60% | Complexity |
| **Shorter prompts** | 20-40% | Less context |
| **Batch processing** | 30-50% | Higher latency |
| **Fine-tuning** | 50-70% | Training cost upfront |

### Model Routing

```
Route by complexity:
├── Simple (FAQ, classification) → Small model (Flash/Haiku)
├── Medium (summarization, editing) → Mid model (Sonnet/GPT-4o-mini)
└── Complex (reasoning, coding) → Large model (Opus/GPT-4o)
```

---

## 6. Observability

### What to Track

| Metric | Why |
|--------|-----|
| **Latency** (p50, p95, p99) | User experience |
| **Token usage** | Cost control |
| **Error rate** | Reliability |
| **Cache hit rate** | Efficiency |
| **User satisfaction** | Quality signal |

### Logging Principles

- Log prompt + response (redact PII)
- Track model version and parameters
- Record latency per component
- Tag by feature/user segment
- Use structured logging (JSON)

---

## 7. Security Considerations

### Prompt Injection Defense

| Layer | Defense |
|-------|---------|
| **Input** | Sanitize, validate, length limit |
| **System prompt** | Separate from user input |
| **Output** | Validate before executing |
| **Monitoring** | Detect anomalous patterns |

### Data Privacy

- Never log PII without consent
- Use data processing agreements (DPA)
- Consider data residency requirements
- Implement right to deletion

---

## 8. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Call LLM for every request | Cache aggressively |
| Use largest model for everything | Route by complexity |
| Ignore token limits | Track and budget tokens |
| Trust LLM output blindly | Validate and constrain |
| Skip monitoring | Track cost, latency, errors from day 1 |

---

> **Remember:** Production LLM apps are 10% prompt engineering and 90% engineering. Treat the LLM as an unreliable, expensive database that sometimes gives brilliant answers.
