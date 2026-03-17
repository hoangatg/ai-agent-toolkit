---
description: Migration workflow. Plan and execute database or framework migrations safely.
---

# /migrate - Migration

$ARGUMENTS

---

## Task

Plan and execute a safe migration with rollback capability.

### Steps:

1. **Analyze** - Identify what needs to migrate and impact
2. **Plan** - Create step-by-step migration plan with rollback
3. **Test** - Run migration in test environment
4. **Execute** - Apply migration with monitoring
5. **Verify** - Validate data integrity and functionality

---

## Usage Examples

```
/migrate database          # Database schema migration
/migrate nextjs 14         # Upgrade Next.js to v14
/migrate prisma drizzle    # Migrate ORM from Prisma to Drizzle
```
