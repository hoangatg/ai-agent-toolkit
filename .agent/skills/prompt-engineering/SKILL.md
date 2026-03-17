---
name: prompt-engineering
description: Master the art of crafting effective prompts for LLMs. Chaining strategies, few-shot patterns, system prompts, and output control. Use when designing AI interactions or optimizing LLM responses.
---

# Prompt Engineering

> Design prompts that get reliable, high-quality results from LLMs.

---

## 1. Core Principles

| Principle | Description |
|-----------|-------------|
| **Clarity** | Unambiguous instructions, one interpretation |
| **Specificity** | Define format, length, tone, constraints |
| **Context** | Provide relevant background, not noise |
| **Examples** | Show desired output (few-shot) |
| **Iteration** | Test, measure, refine systematically |

---

## 2. Prompt Architecture

### Anatomy of a Good Prompt

```
[System Role] → Who the AI is
[Context]     → Background information
[Task]        → What to do
[Format]      → How to output
[Constraints] → What NOT to do
[Examples]    → Few-shot demonstrations
```

### System Prompt Design

| Component | Purpose |
|-----------|---------|
| **Persona** | Define expertise and behavior |
| **Scope** | Boundaries of what to handle |
| **Style** | Tone, formality, verbosity |
| **Rules** | Hard constraints and guardrails |

---

## 3. Prompting Strategies

### Strategy Selection

| Strategy | When to Use |
|----------|-------------|
| **Zero-shot** | Simple, well-defined tasks |
| **Few-shot** | Need consistent format/style |
| **Chain-of-Thought** | Complex reasoning, math, logic |
| **Self-Consistency** | High-stakes decisions (multiple runs) |
| **Tree-of-Thought** | Exploration, creative problem-solving |
| **ReAct** | Tool use, multi-step tasks |

### Chain-of-Thought Principles

- Ask model to "think step by step"
- Break complex problems into sub-problems
- Request reasoning before final answer
- Validate intermediate steps

---

## 4. Few-Shot Patterns

### Design Principles

| Principle | Application |
|-----------|-------------|
| Representative examples | Cover edge cases |
| Consistent format | Same structure each example |
| Diverse difficulty | Easy → Hard progression |
| Minimal examples | 2-5 usually sufficient |

### Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| 20+ examples (context waste) | 3-5 well-chosen examples |
| All similar examples | Diverse representative cases |
| Examples without labels | Clear input → output mapping |
| Ambiguous formatting | Explicit delimiters |

---

## 5. Output Control

### Structured Output

| Technique | Use Case |
|-----------|----------|
| **JSON mode** | API responses, data extraction |
| **XML tags** | Structured reasoning with sections |
| **Markdown** | Documentation, reports |
| **Delimiters** | Clear section boundaries |

### Constraining Output

- Specify exact format: "Respond with JSON only"
- Set length: "In 2-3 sentences"
- Define tone: "Professional, no jargon"
- Restrict scope: "Only discuss X, ignore Y"

---

## 6. Prompt Chaining

### When to Chain

```
Single prompt fails when:
├── Task has multiple distinct steps
├── Output of step N feeds step N+1
├── Different expertise needed per step
└── Quality degrades with complexity
```

### Chain Design

| Pattern | Structure |
|---------|-----------|
| **Sequential** | A → B → C (pipeline) |
| **Branching** | A → [B or C] based on condition |
| **Parallel** | A + B → merge → C |
| **Iterative** | A → B → refine → B → refine |

---

## 7. Common Mistakes

| Mistake | Impact | Fix |
|---------|--------|-----|
| Vague instructions | Inconsistent output | Be specific about format and constraints |
| Too much context | Diluted focus | Include only relevant information |
| No examples | Format guessing | Add 2-3 few-shot examples |
| Ignoring temperature | Random vs deterministic | Low temp for factual, high for creative |
| No eval criteria | Can't measure quality | Define success metrics upfront |

---

## 8. Evaluation Framework

### Measuring Prompt Quality

| Metric | How to Measure |
|--------|---------------|
| **Accuracy** | Does output match expected? |
| **Consistency** | Same input → similar output? |
| **Relevance** | Stays on topic? |
| **Format compliance** | Follows requested structure? |
| **Latency** | Response time acceptable? |
| **Token efficiency** | Minimal tokens for max quality? |

---

> **Remember:** The best prompt is the simplest one that reliably produces the desired output. Complexity should be earned, not assumed.
