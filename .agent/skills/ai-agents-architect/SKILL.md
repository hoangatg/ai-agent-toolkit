---
name: ai-agents-architect
description: Design autonomous AI agent systems. Multi-agent orchestration, tool use, memory, planning, and evaluation. Use when building AI-powered automation or agent workflows.
---

# AI Agents Architect

> Design systems where AI acts, not just responds.

---

## 1. Agent Architecture Patterns

### Single Agent

```
User → Agent → [Think → Act → Observe] → Response
```

### Multi-Agent

```
User → Orchestrator → [Agent A, Agent B, Agent C] → Merge → Response
```

### Pattern Selection

| Pattern | When to Use |
|---------|-------------|
| **Single agent** | Well-scoped tasks, clear tool set |
| **Sequential chain** | Pipeline workflows (A → B → C) |
| **Parallel fan-out** | Independent subtasks, merge results |
| **Hierarchical** | Complex tasks, manager + workers |
| **Debate/consensus** | Critical decisions, multiple perspectives |

---

## 2. Core Agent Components

| Component | Purpose | Design Question |
|-----------|---------|----------------|
| **Planner** | Break task into steps | How complex is decomposition? |
| **Memory** | Short-term + long-term context | What needs persisting? |
| **Tools** | External capabilities | What actions can agent take? |
| **Evaluator** | Assess quality/progress | How to know if done? |
| **Guardrails** | Safety and boundaries | What should agent NOT do? |

---

## 3. Tool Design for Agents

### Principles

| Principle | Application |
|-----------|-------------|
| **Clear naming** | `search_documents` not `do_thing` |
| **Typed inputs** | Schema with validation |
| **Bounded scope** | One action per tool |
| **Error messages** | Actionable, not cryptic |
| **Idempotent** | Safe to retry |

### Tool Categories

| Category | Examples |
|----------|---------|
| **Read** | Search, fetch, query database |
| **Write** | Create file, send email, update DB |
| **Transform** | Parse, convert, calculate |
| **Communicate** | Notify, ask user, delegate |

---

## 4. Memory Architecture

### Memory Types

| Type | Duration | Use Case |
|------|----------|----------|
| **Working** | Current task | Conversation context |
| **Episodic** | Past interactions | Learning from history |
| **Semantic** | Permanent knowledge | Domain expertise |
| **Procedural** | Learned workflows | Repeated task patterns |

### Implementation Patterns

| Pattern | Storage | Retrieval |
|---------|---------|-----------|
| **Buffer** | Last N messages | FIFO |
| **Summary** | Compressed history | Summarization |
| **Vector** | Embedded memories | Semantic search |
| **Knowledge graph** | Entity relationships | Graph traversal |

---

## 5. Planning Strategies

### Plan-and-Execute vs ReAct

| Strategy | Pros | Cons |
|----------|------|------|
| **ReAct** | Adaptive, handles surprises | Can loop, expensive |
| **Plan-Execute** | Efficient, predictable | Rigid, re-plan is costly |
| **Hybrid** | Best of both | More complex to implement |

### Planning Principles

- Decompose before executing
- Set maximum iteration limits
- Track progress against plan
- Allow re-planning on failure
- Make plans observable/debuggable

---

## 6. Safety & Guardrails

### Mandatory Guardrails

| Guardrail | Implementation |
|-----------|---------------|
| **Max iterations** | Hard limit on agent loops |
| **Token budget** | Cap total tokens per task |
| **Action allowlist** | Define permitted operations |
| **Human-in-the-loop** | Approval for destructive actions |
| **Output validation** | Verify before sending/executing |

### Risk Classification

```
Tool Risk Levels:
├── LOW:  Read-only operations (search, fetch)
├── MEDIUM: Reversible writes (create draft, stage)
├── HIGH: Irreversible actions (send email, deploy)
└── CRITICAL: Destructive (delete, financial transactions)
```

---

## 7. Evaluation & Debugging

### Agent Metrics

| Metric | Measures |
|--------|---------|
| **Task completion** | Did it finish the job? |
| **Step efficiency** | Minimum steps taken? |
| **Tool accuracy** | Right tool, right params? |
| **Cost** | Total tokens/API calls |
| **Safety** | Any guardrail violations? |

### Debugging Principles

- Log every thought-action-observation cycle
- Trace tool calls with inputs and outputs
- Identify where reasoning diverges
- Test with deterministic scenarios first
- Build regression tests from failures

---

## 8. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Let agents run unbounded | Set max iterations and token limits |
| Give agents too many tools | Start with 3-5, add as needed |
| Skip human approval for writes | Require confirmation for side effects |
| Trust agent self-evaluation | External validation and testing |
| Build complex multi-agent first | Start single agent, scale when needed |

---

> **Remember:** A good agent does the minimum necessary to complete the task safely. Autonomy should be earned through testing, not assumed.
