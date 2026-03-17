# Contributing to AI Agent Toolkit

Thank you for your interest in contributing! This guide will help you get started.

---

## 🚀 Quick Start

1. **Fork** the repository
2. **Clone** your fork: `git clone https://github.com/YOUR_USERNAME/ai-agent-toolkit.git`
3. **Create** a branch: `git checkout -b feature/your-feature`
4. **Make** your changes
5. **Submit** a Pull Request

---

## 📁 What Can You Contribute?

### 🧩 New Skills

Create `.agent/skills/your-skill-name/SKILL.md`:

```markdown
---
name: your-skill-name
description: Brief description. When to use this skill.
---

# Skill Title

> Core philosophy

## Key Patterns
...

## Anti-Patterns
| ❌ Don't | ✅ Do |
|----------|-------|
| ... | ... |
```

### 🤖 New Agents

Create `.agent/agents/your-agent-name.md`:

```markdown
---
name: your-agent-name
description: What this agent does. Trigger keywords.
tools: Read, Grep, Glob, Bash, Edit, Write
model: inherit
skills: clean-code, relevant-skill-1, relevant-skill-2
---

# Agent Name

Brief description of expertise.

## Core Philosophy
> ...

## Expertise Areas
...
```

### ⚡ New Workflows

Create `.agent/workflows/your-workflow.md`:

```markdown
---
description: What this workflow does.
---

# /your-workflow - Title

## Steps:
1. ...
2. ...
3. ...
```

---

## 📝 Guidelines

- **Keep it concise** — Skills should teach principles, not be encyclopedias
- **Use tables** — Quick-reference tables are easier to scan than paragraphs
- **Include anti-patterns** — Show what NOT to do alongside best practices
- **Test your additions** — Verify the skill/agent works with at least one AI tool

---

## 🏷️ Commit Messages

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
feat(skills): add kubernetes-operator skill
fix(agents): update backend-specialist triggers
docs: update ARCHITECTURE.md with new counts
```

---

## 📄 License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
