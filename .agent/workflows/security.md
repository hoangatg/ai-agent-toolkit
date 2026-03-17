---
description: Security audit workflow. Full security scan with vulnerability analysis and remediation.
---

# /security - Security Audit

$ARGUMENTS

---

## Task

Perform comprehensive security audit.

### Steps:

1. **Scan** - Run security scanner on codebase
2. **Analyze** - Use `security-auditor` agent for deep analysis
3. **Prioritize** - Rank findings by severity (Critical → Low)
4. **Remediate** - Fix critical and high severity issues
5. **Verify** - Re-scan to confirm fixes

---

## Usage Examples

```
/security                  # Full security audit
/security src/auth/        # Audit auth module
/security --owasp          # OWASP Top 10 focused audit
```
