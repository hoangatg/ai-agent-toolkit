---
description: Project scaffolding workflow. Generate project structure, boilerplate, and configuration from templates.
---

# /scaffold - Project Scaffolding

$ARGUMENTS

---

## Task

Generate a project structure with best-practice configuration.

### Steps:

1. **Requirements**
   - Determine project type (web, api, mobile, fullstack)
   - Select tech stack and tools

2. **Structure**
   - Create directory structure following conventions
   - Set up configuration files (tsconfig, eslint, prettier)

3. **Boilerplate**
   - Generate starter code and entry points
   - Set up environment variables (.env.example)

4. **Tooling**
   - Configure testing framework
   - Set up CI/CD pipeline templates
   - Add Git hooks (husky, lint-staged)

5. **Documentation**
   - Generate README with setup instructions
   - Create contributing guidelines

---

## Usage Examples

```
/scaffold nextjs           # Next.js project
/scaffold api express      # Express API project
/scaffold monorepo         # Turborepo monorepo
```
