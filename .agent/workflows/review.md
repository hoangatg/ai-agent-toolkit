---
description: Code review workflow. Systematic review of code changes for quality, security, and best practices.
---

# /review - Code Review

$ARGUMENTS

---

## Task

Perform a systematic code review following best practices.

### Steps:

1. **Scope Analysis**
   - Identify changed files and affected areas
   - Determine review focus (security, performance, quality)

2. **Code Quality Check**
   - Use `code-reviewer` agent for systematic review
   - Check naming, structure, complexity
   - Identify code smells and anti-patterns

3. **Security Scan**
   - Use `security-auditor` agent for security review
   - Check input validation, auth, injection risks

4. **Test Coverage**
   - Use `test-engineer` agent for test analysis
   - Verify edge cases and error handling

5. **Report**
   - Summarize findings with severity levels
   - Provide actionable improvement suggestions

---

## Usage Examples

```
/review                    # Review recent changes
/review src/auth/          # Review specific directory
/review --security         # Focus on security review
```
