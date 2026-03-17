---
name: kubernetes-architect
description: Kubernetes architecture principles. Cluster design, Helm charts, GitOps, scaling strategies, and production operations. Use when deploying containerized applications at scale.
---

# Kubernetes Architect

> Orchestrate containers at scale with confidence.

---

## 1. K8s Architecture Decisions

### When to Use K8s

| Scenario | Use K8s? |
|----------|----------|
| Single app, low traffic | ❌ Overkill, use PaaS |
| Microservices, scaling needs | ✅ Sweet spot |
| Multi-cloud / hybrid | ✅ Portability |
| Team < 3 engineers | ⚠️ Consider managed services |
| Compliance / data sovereignty | ✅ Full control |

### Managed vs Self-Hosted

| Factor | Managed (EKS/GKE/AKS) | Self-Hosted |
|--------|----------------------|-------------|
| **Ops burden** | Low | High |
| **Cost** | Higher | Lower (if skilled team) |
| **Control** | Limited | Full |
| **Best for** | Most teams | Large infra teams |

---

## 2. Core Concepts

### Resource Hierarchy

```
Cluster
├── Namespace (logical isolation)
│   ├── Deployment (desired state)
│   │   └── ReplicaSet (manages pods)
│   │       └── Pod (smallest unit)
│   ├── Service (networking)
│   ├── ConfigMap / Secret (config)
│   └── Ingress (external traffic)
```

### Resource Sizing

| Resource | Start With | Adjust Based On |
|----------|-----------|-----------------|
| **Requests** | Actual usage (p50) | Profiling data |
| **Limits** | 2x requests | OOMKill frequency |
| **Replicas** | 2-3 minimum | Traffic patterns |
| **HPA** | CPU 70% target | Custom metrics |

---

## 3. Deployment Strategies

| Strategy | Risk | Downtime | Use When |
|----------|------|----------|----------|
| **Rolling** | Low | Zero | Default, most apps |
| **Blue/Green** | Low | Zero | Need instant rollback |
| **Canary** | Very Low | Zero | High-risk changes |
| **Recreate** | High | Brief | DB migrations, breaking changes |

---

## 4. Networking

### Service Types

| Type | Scope | Use Case |
|------|-------|----------|
| **ClusterIP** | Internal | Service-to-service |
| **NodePort** | Node-level | Development/testing |
| **LoadBalancer** | External | Direct external access |
| **Ingress** | External | HTTP routing, TLS |

---

## 5. GitOps Principles

| Principle | Application |
|-----------|-------------|
| **Declarative** | YAML defines desired state |
| **Versioned** | Git as single source of truth |
| **Automated** | Changes applied automatically |
| **Observable** | Drift detection and alerts |

### Tools

| Tool | Purpose |
|------|---------|
| **ArgoCD** | GitOps continuous delivery |
| **Flux** | GitOps toolkit |
| **Helm** | Package management |
| **Kustomize** | YAML overlay customization |

---

## 6. Security

| Layer | Practice |
|-------|----------|
| **RBAC** | Least privilege, namespace-scoped |
| **Network policies** | Restrict pod-to-pod traffic |
| **Pod security** | Non-root, read-only fs, no privilege escalation |
| **Secrets** | External secret operators (Vault, AWS SM) |
| **Image security** | Scan images, use signed images |

---

## 7. Observability

| Pillar | Tool Options |
|--------|-------------|
| **Metrics** | Prometheus + Grafana |
| **Logging** | EFK/ELK, Loki |
| **Tracing** | Jaeger, Tempo |
| **Alerting** | AlertManager, PagerDuty |

---

## 8. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Run without resource limits | Set requests AND limits |
| Single replica in production | Minimum 2-3 replicas |
| Store state in pods | Use external databases |
| Skip health checks | Liveness + readiness probes |
| Manual kubectl in prod | GitOps with ArgoCD/Flux |

---

> **Remember:** Kubernetes is an operating system for the cloud. Master the abstractions, not just the YAML.
