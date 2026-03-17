---
description: Performance audit workflow. Lighthouse, profiling, optimization recommendations.
---

# /performance - Performance Audit

$ARGUMENTS

---

## Task

Analyze and optimize application performance.

### Steps:

1. **Measure** - Run Lighthouse and performance profiling
2. **Analyze** - Use `performance-optimizer` agent to interpret results
3. **Identify** - Find bottlenecks (bundle, rendering, API, DB)
4. **Optimize** - Apply targeted optimizations
5. **Verify** - Re-measure to confirm improvements

---

## Usage Examples

```
/performance               # Full performance audit
/performance --bundle      # Focus on bundle size
/performance --vitals      # Core Web Vitals analysis
```
