---
name: incident-responder
description: Incident response, runbooks, severity classification, and blameless postmortems. Use when handling production incidents or building incident response processes.
---

# Incident Responder

> Stay calm. Communicate clearly. Fix it. Learn from it.

---

## 1. Incident Lifecycle

```
Detect → Triage → Mitigate → Resolve → Postmortem → Improve
```

---

## 2. Severity Classification

| Severity | Impact | Response Time | Communication |
|----------|--------|--------------|---------------|
| **SEV-1** | Service down, data loss | Immediate (24/7) | Exec + all stakeholders |
| **SEV-2** | Major degradation | < 30 min | Team leads |
| **SEV-3** | Minor impact | Business hours | Team channel |
| **SEV-4** | Cosmetic / low impact | Next sprint | Ticket |

---

## 3. Incident Roles

| Role | Responsibility |
|------|---------------|
| **Incident Commander** | Coordinates response, makes decisions |
| **Technical Lead** | Investigates and fixes |
| **Communications** | Updates stakeholders |
| **Scribe** | Documents timeline and actions |

---

## 4. Response Principles

| Principle | Application |
|-----------|-------------|
| **Mitigate first** | Stop bleeding before root cause |
| **Communicate early** | Status page update within 5 min |
| **Time-box investigation** | If no progress in 30 min, escalate |
| **Rollback is valid** | Revert is faster than forward-fix |
| **Document as you go** | Timeline of actions and findings |

---

## 5. Runbook Template

| Section | Content |
|---------|---------|
| **Symptom** | What the alert/report looks like |
| **Impact** | Who is affected, how badly |
| **Quick checks** | Dashboard URLs, common causes |
| **Mitigation steps** | Ordered actions to reduce impact |
| **Escalation** | Who to contact, when |
| **Resolution** | Steps to permanently fix |

---

## 6. Blameless Postmortem

### Structure

| Section | Focus |
|---------|-------|
| **Summary** | What happened in 2-3 sentences |
| **Impact** | Duration, affected users, revenue impact |
| **Timeline** | Minute-by-minute events |
| **Root cause** | Why it happened (5 Whys) |
| **What went well** | Things that worked |
| **What went wrong** | Things that didn't |
| **Action items** | Specific, assigned, deadlined |

### Principles

- Blame systems, not people
- Focus on "how" not "who"
- Share widely to spread learning
- Track action items to completion

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Blame individuals | Blameless culture |
| Skip postmortems | Learn from every SEV-1/2 |
| Hero culture (one person fixes all) | Documented runbooks anyone can follow |
| No status updates during incident | Regular updates every 15-30 min |
| Fix only symptoms | Address root causes |

---

> **Remember:** Incidents are inevitable. Good incident response turns failures into learning opportunities. The goal is not zero incidents — it's fast detection, fast recovery, and continuous improvement.
