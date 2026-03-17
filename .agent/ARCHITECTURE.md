# AI Agent Toolkit Architecture

> The Ultimate AI Agent Skills Toolkit — Production-Ready for Full-Stack Development

---

## 📋 Overview

AI Agent Toolkit is a modular system consisting of:

- **43 Specialist Agents** — Role-based AI personas with domain expertise
- **95 Skills** — Domain-specific knowledge modules loaded on-demand
- **37 Workflows** — Slash command procedures for common development tasks

---

## 🏗️ Directory Structure

```plaintext
.agent/
├── ARCHITECTURE.md          # This file
├── agents/                  # 43 Specialist Agents
├── skills/                  # 95 Skills
├── workflows/               # 37 Slash Commands
├── rules/                   # Global Rules
└── scripts/                 # Master Validation Scripts
```

---

## 🤖 Agents (43)

Specialist AI personas for different domains. Each agent has a defined focus area and loads specific skills on-demand.

### Core & Orchestration (3)

| Agent | Focus | Skills |
|-------|-------|--------|
| `orchestrator` | Multi-agent coordination | parallel-agents, behavioral-modes, plan-writing |
| `project-planner` | Discovery, task planning | brainstorming, plan-writing, architecture |
| `codebase-explorer` | Codebase analysis, discovery | — |

### Frontend & UI (2)

| Agent | Focus | Skills |
|-------|-------|--------|
| `frontend-specialist` | Web UI/UX, React, Next.js | frontend-design, react-best-practices, tailwind-patterns, 3d-web-experience, scroll-experience, nextjs-app-router, vue-nuxt-expert |
| `accessibility-expert` | WCAG compliance, inclusive design | web-design-guidelines, frontend-design |

### Backend & API (3)

| Agent | Focus | Skills |
|-------|-------|--------|
| `backend-specialist` | API, business logic, server | api-patterns, nodejs-best-practices, database-design, fastapi-pro, graphql-expert |
| `api-designer` | API contracts, OpenAPI specs | api-patterns, graphql-expert, documentation-templates |
| `fullstack-developer` | End-to-end feature development | react-best-practices, nextjs-app-router, api-patterns, database-design, typescript-expert |

### Data & Database (3)

| Agent | Focus | Skills |
|-------|-------|--------|
| `database-architect` | Schema, SQL, optimization | database-design, domain-driven-design, redis-caching |
| `data-engineer` | Data pipelines, ETL, analytics | data-engineering, database-design, python-patterns |
| `data-scientist` | ML models, analysis, experiments | python-patterns, data-engineering |

### AI & Machine Learning (1)

| Agent | Focus | Skills |
|-------|-------|--------|
| `ai-ml-engineer` | LLM integration, RAG, agents | ai-agents-architect, rag-engineer, llm-app-patterns, prompt-engineering, mcp-builder |

### Mobile & Desktop (3)

| Agent | Focus | Skills |
|-------|-------|--------|
| `mobile-developer` | iOS, Android, RN, Flutter | mobile-design, react-native-expert, flutter-expert |
| `desktop-developer` | Electron, Tauri, cross-platform | electron-tauri, typescript-expert |
| `game-developer` | Game logic, mechanics | game-development |

### Cloud & Infrastructure (3)

| Agent | Focus | Skills |
|-------|-------|--------|
| `devops-engineer` | CI/CD, Docker, Cloud | deployment-procedures, docker-expert, aws-serverless, kubernetes-architect, terraform-specialist, ci-cd-pipelines, vercel-deployment |
| `cloud-architect` | Multi-cloud, serverless strategy | aws-serverless, kubernetes-architect, terraform-specialist, docker-expert, ci-cd-pipelines |
| `monorepo-architect` | Monorepo strategy, workspaces | monorepo-management, ci-cd-pipelines, typescript-expert |

### Architecture & Design (2)

| Agent | Focus | Skills |
|-------|-------|--------|
| `solutions-architect` | System design, trade-offs, ADRs | architecture, microservices-patterns, domain-driven-design, event-sourcing-architect, aws-serverless |
| `code-archaeologist` | Legacy code, refactoring | clean-code, code-review-checklist |

### Security (1)

| Agent | Focus | Skills |
|-------|-------|--------|
| `security-auditor` | Security + penetration testing | vulnerability-scanner, red-team-tactics, oauth-authentication |

### Testing & Quality (3)

| Agent | Focus | Skills |
|-------|-------|--------|
| `test-engineer` | Testing strategies | testing-patterns, tdd-workflow, webapp-testing |
| `qa-automation-engineer` | E2E testing, CI pipelines | webapp-testing, testing-patterns |
| `code-reviewer` | Code quality, PR reviews | code-review-checklist, clean-code, testing-patterns |

### Performance & Reliability (3)

| Agent | Focus | Skills |
|-------|-------|--------|
| `performance-optimizer` | Speed, Web Vitals | performance-profiling, observability-engineer |
| `reliability-engineer` | SRE, uptime, incident response | incident-responder, observability-engineer, server-management |
| `debugger` | Root cause analysis | systematic-debugging |

### Product & Content (4)

| Agent | Focus | Skills |
|-------|-------|--------|
| `product-manager` | Requirements, user stories, strategy | plan-writing, brainstorming, product-manager-toolkit, pricing-strategy, copywriting |
| `ux-researcher` | User research, usability testing | brainstorming, product-manager-toolkit, frontend-design |
| `content-strategist` | SEO content, marketing, growth | copywriting, seo-fundamentals, geo-fundamentals, analytics-tracking |
| `seo-specialist` | Ranking, visibility | seo-fundamentals, geo-fundamentals, analytics-tracking |

### Documentation & Communication (2)

| Agent | Focus | Skills |
|-------|-------|--------|
| `documentation-writer` | Manuals, docs | documentation-templates |
| `technical-writer` | API docs, guides, tutorials | documentation-templates, copywriting |

### Operations & Specialized (4)

| Agent | Focus | Skills |
|-------|-------|--------|
| `release-manager` | Versioning, changelogs, releases | git-workflow, create-pr, ci-cd-pipelines, deployment-procedures |
| `migration-specialist` | Database/framework migrations | database-design, architecture, testing-patterns |
| `i18n-specialist` | Internationalization, localization | i18n-localization, frontend-design |
| `web3-developer` | Blockchain, smart contracts | web3-blockchain, typescript-expert |

### Real-time (1)

| Agent | Focus | Skills |
|-------|-------|--------|
| `realtime-engineer` | WebSocket, streaming, live features | websocket-realtime, message-queues, redis-caching |

---

## 🧩 Skills (95)

Modular knowledge domains that agents can load on-demand based on task context.

### Frontend & UI

| Skill | Description |
|-------|-------------|
| `react-best-practices` | React & Next.js performance optimization (Vercel - 57 rules) |
| `web-design-guidelines` | Web UI audit - 100+ rules for accessibility, UX, performance (Vercel) |
| `tailwind-patterns` | Tailwind CSS v4 utilities |
| `frontend-design` | UI/UX patterns, design systems |
| `ui-ux-pro-max` | 50 styles, 21 palettes, 50 fonts |
| `3d-web-experience` | Three.js, React Three Fiber, WebGL |
| `scroll-experience` | Scroll-driven animations, GSAP, parallax |
| `design-system-builder` | Component libraries, design tokens, team adoption |

### Backend & API

| Skill | Description |
|-------|-------------|
| `api-patterns` | REST, GraphQL, tRPC |
| `nodejs-best-practices` | Node.js async, modules |
| `python-patterns` | Python standards |
| `fastapi-pro` | FastAPI async APIs, Pydantic v2 |
| `graphql-expert` | Schema design, resolvers, federation |

### Database

| Skill | Description |
|-------|-------------|
| `database-design` | Schema design, optimization |
| `redis-caching` | Redis patterns, caching, pub/sub |
| `supabase-firebase` | BaaS: Supabase + Firebase patterns |

### Languages

| Skill | Description |
|-------|-------------|
| `typescript-expert` | Advanced types, generics, type gymnastics |
| `rust-pro` | Rust 1.75+, async, systems programming |
| `golang-pro` | Go concurrency, error handling |

### Frameworks

| Skill | Description |
|-------|-------------|
| `nextjs-app-router` | Next.js 14+ App Router, Server Components |
| `vue-nuxt-expert` | Vue 3 Composition API, Nuxt 3 patterns |
| `react-native-expert` | React Native, Expo, mobile patterns |
| `flutter-expert` | Flutter/Dart, widget architecture |

### AI & LLM

| Skill | Description |
|-------|-------------|
| `prompt-engineering` | Prompt strategies, chaining, few-shot patterns |
| `rag-engineer` | RAG pipelines, vector search, chunking |
| `ai-agents-architect` | Multi-agent systems, tool use, safety |
| `llm-app-patterns` | Production LLM: streaming, caching, fallbacks |
| `mcp-builder` | Model Context Protocol server building |

### Cloud & Infrastructure

| Skill | Description |
|-------|-------------|
| `docker-expert` | Containers, multi-stage builds |
| `aws-serverless` | Lambda, DynamoDB, API Gateway, SAM |
| `kubernetes-architect` | K8s architecture, Helm, GitOps |
| `terraform-specialist` | Infrastructure as Code, modules |
| `deployment-procedures` | CI/CD, deploy workflows |
| `server-management` | Infrastructure management |
| `ci-cd-pipelines` | GitHub Actions, GitLab CI, automation |
| `vercel-deployment` | Vercel: preview, edge, ISR |
| `monorepo-management` | Turborepo, Nx, pnpm workspaces |

### Architecture & Design Patterns

| Skill | Description |
|-------|-------------|
| `architecture` | System design patterns |
| `microservices-patterns` | Service decomposition, resilience |
| `domain-driven-design` | Bounded contexts, aggregates, DDD |
| `event-sourcing-architect` | Event sourcing, CQRS, projections |
| `app-builder` | Full-stack app scaffolding |

### Testing & Quality

| Skill | Description |
|-------|-------------|
| `testing-patterns` | Jest, Vitest, strategies |
| `webapp-testing` | E2E, Playwright |
| `tdd-workflow` | Test-driven development |
| `code-review-checklist` | Code review standards |
| `lint-and-validate` | Linting, validation |

### Security

| Skill | Description |
|-------|-------------|
| `vulnerability-scanner` | Security auditing, OWASP |
| `red-team-tactics` | Offensive security |
| `oauth-authentication` | OAuth 2.0, JWT, SSO, RBAC |

### Real-time & Communication

| Skill | Description |
|-------|-------------|
| `websocket-realtime` | WebSocket, SSE, live collaboration |
| `message-queues` | Kafka, RabbitMQ, event streaming |
| `email-development` | HTML email, deliverability, templates |

### Observability & Reliability

| Skill | Description |
|-------|-------------|
| `observability-engineer` | Monitoring, logging, alerting, dashboards |
| `incident-responder` | Incident response, runbooks, postmortems |

### Business & Product

| Skill | Description |
|-------|-------------|
| `product-manager-toolkit` | PRD, RICE prioritization, user stories |
| `copywriting` | Marketing copy, landing pages, CTAs |
| `pricing-strategy` | SaaS pricing models, tier design |
| `analytics-tracking` | GA4, PostHog, conversion tracking |

### Data Engineering

| Skill | Description |
|-------|-------------|
| `data-engineering` | ETL/ELT, dbt, pipelines, warehousing |

### SEO & Growth

| Skill | Description |
|-------|-------------|
| `seo-fundamentals` | SEO, E-E-A-T, Core Web Vitals |
| `geo-fundamentals` | GenAI optimization |

### Integration & Payments

| Skill | Description |
|-------|-------------|
| `stripe-integration` | Checkout, subscriptions, webhooks |

### Desktop & Specialty

| Skill | Description |
|-------|-------------|
| `electron-tauri` | Desktop apps: Electron + Tauri |
| `web3-blockchain` | Smart contracts, dApps, Web3 |

### Mobile

| Skill | Description |
|-------|-------------|
| `mobile-design` | Mobile UI/UX patterns |

### Game Development

| Skill | Description |
|-------|-------------|
| `game-development` | Game logic, mechanics |

### Planning & Workflow

| Skill | Description |
|-------|-------------|
| `plan-writing` | Task planning, breakdown |
| `brainstorming` | Socratic questioning |
| `git-workflow` | Branching, commits, PR process |
| `create-pr` | Clean PR creation, changelogs |

### Shell/CLI

| Skill | Description |
|-------|-------------|
| `bash-linux` | Linux commands, scripting |
| `powershell-windows` | Windows PowerShell |

### Other

| Skill | Description |
|-------|-------------|
| `clean-code` | Coding standards (Global) |
| `behavioral-modes` | Agent personas |
| `parallel-agents` | Multi-agent patterns |
| `intelligent-routing` | Auto agent selection |
| `documentation-templates` | Doc formats |
| `i18n-localization` | Internationalization |
| `performance-profiling` | Web Vitals, optimization |
| `systematic-debugging` | Troubleshooting |

---

## 🔄 Workflows (37)

Slash command procedures. Invoke with `/command`.

### Development (8)

| Command | Description |
|---------|-------------|
| `/create` | Create new application |
| `/enhance` | Improve existing code |
| `/feature` | End-to-end feature development |
| `/component` | Design, build, test UI components |
| `/scaffold` | Project scaffolding and boilerplate |
| `/api` | API design and documentation |
| `/refactor` | Code refactoring with safety nets |
| `/design` | Design with 50 styles (UI/UX Pro Max) |

### Quality & Review (5)

| Command | Description |
|---------|-------------|
| `/review` | Systematic code review |
| `/test` | Run and generate tests |
| `/lint` | Lint and auto-fix issues |
| `/security` | Full security audit |
| `/accessibility` | WCAG compliance audit |

### Planning & Discovery (3)

| Command | Description |
|---------|-------------|
| `/plan` | Task breakdown and planning |
| `/brainstorm` | Socratic discovery and ideation |
| `/orchestrate` | Multi-agent coordination |

### Operations & Release (5)

| Command | Description |
|---------|-------------|
| `/deploy` | Deploy application |
| `/release` | Version bump, changelog, tag |
| `/migrate` | Database/framework migration |
| `/monitor` | Setup monitoring and alerts |
| `/backup` | Backup and disaster recovery |

### Documentation (3)

| Command | Description |
|---------|-------------|
| `/docs` | Auto-generate documentation |
| `/changelog` | Generate changelog from commits |
| `/readme` | Create/update project README |

### AI & Data (3)

| Command | Description |
|---------|-------------|
| `/ai` | Add AI features (chat, RAG, embeddings) |
| `/data` | Data pipeline setup |
| `/prompt` | Prompt engineering and optimization |

### Performance & Debug (4)

| Command | Description |
|---------|-------------|
| `/performance` | Lighthouse, profiling, optimization |
| `/debug` | Systematic debugging |
| `/preview` | Preview changes locally |
| `/status` | Check project status |

---

## 🎯 Skill Loading Protocol

```plaintext
User Request → Skill Description Match → Load SKILL.md
                                            ↓
                                    Read references/
                                            ↓
                                    Read scripts/
```

### Skill Structure

```plaintext
skill-name/
├── SKILL.md           # (Required) Metadata & instructions
├── scripts/           # (Optional) Python/Bash scripts
├── references/        # (Optional) Templates, docs
└── assets/            # (Optional) Images, logos
```

### Enhanced Skills (with scripts/references)

| Skill | Files | Coverage |
|-------|-------|----------|
| `ui-ux-pro-max` | 27 | 50 styles, 21 palettes, 50 fonts |
| `app-builder` | 20 | Full-stack scaffolding |

---

## 🛠 Scripts (2)

Master validation scripts that orchestrate skill-level scripts.

### Master Scripts

| Script | Purpose | When to Use |
|--------|---------|-------------|
| `checklist.py` | Priority-based validation (Core checks) | Development, pre-commit |
| `verify_all.py` | Comprehensive verification (All checks) | Pre-deployment, releases |

### Usage

```bash
# Quick validation during development
python .agent/scripts/checklist.py .

# Full verification before deployment
python .agent/scripts/verify_all.py . --url http://localhost:3000
```

### What They Check

**checklist.py** (Core checks):

- Security (vulnerabilities, secrets)
- Code Quality (lint, types)
- Schema Validation
- Test Suite
- UX Audit
- SEO Check

**verify_all.py** (Full suite):

- Everything in checklist.py PLUS:
- Lighthouse (Core Web Vitals)
- Playwright E2E
- Bundle Analysis
- Mobile Audit
- i18n Check

For details, see [scripts/README.md](scripts/README.md)

---

## 📊 Statistics

| Metric | Value |
|--------|-------|
| **Total Agents** | 43 |
| **Total Skills** | 95 |
| **Total Workflows** | 37 |
| **Total Scripts** | 2 (master) + 18 (skill-level) |
| **Coverage** | ~99% full-stack development |

---

## 🔗 Quick Reference

| Need | Agent | Key Skills |
|------|-------|------------|
| Web App | `frontend-specialist` | react-best-practices, frontend-design |
| API | `backend-specialist` | api-patterns, nodejs-best-practices |
| Full Feature | `fullstack-developer` | react-best-practices, api-patterns, database-design |
| Mobile | `mobile-developer` | mobile-design, react-native-expert |
| Desktop | `desktop-developer` | electron-tauri |
| Database | `database-architect` | database-design |
| Security | `security-auditor` | vulnerability-scanner, red-team-tactics |
| Testing | `test-engineer` | testing-patterns, webapp-testing |
| Debug | `debugger` | systematic-debugging |
| Plan | `project-planner` | brainstorming, plan-writing |
| AI/LLM | `ai-ml-engineer` | rag-engineer, llm-app-patterns, prompt-engineering |
| DevOps | `devops-engineer` | docker-expert, aws-serverless, terraform-specialist |
| Cloud | `cloud-architect` | aws-serverless, kubernetes-architect |
| Product | `product-manager` | product-manager-toolkit, pricing-strategy |
| Data | `data-engineer` | data-engineering |
| Payments | `backend-specialist` | stripe-integration |
| a11y | `accessibility-expert` | web-design-guidelines |
| SRE | `reliability-engineer` | incident-responder, observability-engineer |
| Review | `code-reviewer` | code-review-checklist, clean-code |
| Release | `release-manager` | git-workflow, ci-cd-pipelines |
