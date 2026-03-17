---
name: spec-driven-development
description: Spec-driven development methodology. Define requirements before code, use structured specs as source of truth for AI agents. Planning files, acceptance criteria, and systematic delivery. Use when starting new features, complex implementations, or multi-step projects.
---

# Spec-Driven Development (SDD)

> The #1 trending methodology for AI-assisted development in 2026. Define specs first, then let AI build.

## Core Principle

> "Specs are not documentation — they are executable truth. Define WHAT before HOW."

## Why SDD?

| Problem Without SDD | SDD Solution |
|---------------------|--------------|
| AI generates wrong code | Spec constrains AI behavior |
| Scope creep | Spec defines boundaries |
| Context loss in long sessions | Planning files persist context |
| Inconsistent output | Structured criteria ensure quality |
| "Vibe coding" | Systematic, reviewable process |

---

## SDD Workflow

```
1. SPECIFY
   └── Write high-level specification (problem, goals, constraints)

2. PLAN
   └── Break into technical tasks with acceptance criteria

3. TASK
   └── Generate actionable chunks with clear inputs/outputs

4. IMPLEMENT
   └── AI executes tasks against spec, validates against criteria

5. VERIFY
   └── Check implementation matches spec
```

---

## Spec File Format

### Feature Spec (`specs/{feature-name}.md`)

```markdown
# Feature: [Name]

## Problem Statement
[What problem does this solve?]

## Goals
- [ ] Goal 1 — [Measurable outcome]
- [ ] Goal 2 — [Measurable outcome]

## Non-Goals (Out of Scope)
- [Explicitly excluded items]

## Technical Requirements
- [Specific technical constraints]

## Acceptance Criteria
- Given [context], When [action], Then [outcome]

## Dependencies
- [External services, APIs, packages]

## Risks & Mitigations
| Risk | Likelihood | Mitigation |
|------|-----------|------------|
| [Risk] | High/Med/Low | [Plan] |
```

---

## Planning Files (Manus-Style)

Persist AI context across sessions using planning files:

### `project-plan.md`
```markdown
# Project Plan

## Current Status: [Phase]

## Completed
- [x] Task 1

## In Progress
- [/] Task 2 — [details]

## Upcoming
- [ ] Task 3

## Decisions Made
- Decision 1: [rationale]

## Lessons Learned
- [Key insights from implementation]
```

### `lessons-learned.md`
```markdown
# Lessons Learned

## [Date] — [Topic]
**Problem**: [What went wrong]
**Solution**: [What fixed it]
**Prevention**: [How to avoid in future]
```

---

## Best Practices

| Practice | Description |
|----------|-------------|
| **Spec before code** | Write spec → review → then implement |
| **Living documents** | Update specs as requirements evolve |
| **Explicit non-goals** | Prevent scope creep by defining boundaries |
| **Measurable criteria** | Every goal must be verifiable |
| **Small chunks** | Break specs into tasks ≤ 1 hour each |
| **Decision log** | Record WHY for architecture choices |

---

## Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Start coding without spec | Write spec first, even brief |
| Write vague goals ("make it fast") | Use measurable criteria ("< 200ms p95") |
| Ignore scope creep | Update spec and get approval |
| Let specs go stale | Treat specs as living documents |
| Skip non-goals section | Explicitly define boundaries |
