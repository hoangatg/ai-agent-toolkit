---
name: terraform-specialist
description: Infrastructure as Code with Terraform. Module design, state management, multi-environment patterns, and best practices. Use when provisioning cloud infrastructure.
---

# Terraform Specialist

> Infrastructure should be code — versioned, tested, and reviewed.

---

## 1. Core Principles

| Principle | Application |
|-----------|-------------|
| **Declarative** | Describe desired state, not steps |
| **Idempotent** | Apply multiple times, same result |
| **Modular** | Reusable modules for common patterns |
| **Versioned** | Pin provider and module versions |
| **Reviewed** | Plan before apply, always |

---

## 2. Project Structure

### Layout Patterns

| Pattern | Best For |
|---------|----------|
| **Flat** | Small projects, single environment |
| **Environment dirs** | Multi-env (dev/staging/prod) |
| **Terragrunt** | Large-scale, DRY configuration |
| **Workspaces** | Simple env separation |

### Recommended Structure

```
infrastructure/
├── modules/           # Reusable modules
│   ├── networking/
│   ├── compute/
│   └── database/
├── environments/      # Environment configs
│   ├── dev/
│   ├── staging/
│   └── prod/
├── backend.tf         # State configuration
└── versions.tf        # Provider versions
```

---

## 3. State Management

### Backend Selection

| Backend | Use Case |
|---------|----------|
| **S3 + DynamoDB** | AWS, team collaboration |
| **GCS** | Google Cloud |
| **Azure Blob** | Azure |
| **Terraform Cloud** | Managed, any cloud |

### State Principles

| Principle | Why |
|-----------|-----|
| **Remote state** | Team collaboration, locking |
| **State locking** | Prevent concurrent modifications |
| **State encryption** | Secrets in state |
| **Minimal blast radius** | Separate state per component |

---

## 4. Module Design

### Good Module Design

| Principle | Application |
|-----------|-------------|
| **Single purpose** | One logical resource group |
| **Typed variables** | Explicit types, descriptions |
| **Sensible defaults** | Override only when needed |
| **Output useful values** | IDs, ARNs, endpoints |
| **Version pinning** | Exact or constrained versions |

---

## 5. Security

| Practice | Implementation |
|----------|---------------|
| **No secrets in code** | Use variables, vault, SSM |
| **Least privilege** | Minimal IAM for Terraform runner |
| **State encryption** | Encrypt at rest |
| **Drift detection** | Regular plan runs |
| **Policy as code** | Sentinel, OPA, or Checkov |

---

## 6. CI/CD Integration

### Pipeline Stages

```
PR Created → terraform fmt → terraform validate → terraform plan → Review
PR Merged → terraform plan → Approval → terraform apply
```

### Best Practices

- Auto-format in CI (`terraform fmt -check`)
- Plan on every PR, show diff in comments
- Require manual approval for apply
- Use separate credentials per environment
- Tag all resources for cost tracking

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| `terraform apply` without plan | Always review plan first |
| Local state files | Remote state with locking |
| Hardcoded values | Variables with defaults |
| One big state file | Separate by component/env |
| Skip version pinning | Pin provider and module versions |

---

> **Remember:** `terraform plan` is your safety net. Never apply without reviewing it. Infrastructure mistakes are expensive to fix.
