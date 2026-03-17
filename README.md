<div align="center">

# 🧠 AI Agent Toolkit

### Turn Any AI Coding Assistant Into a Domain Expert

**43 Specialist Agents · 95 Skills · 37 Workflows**

The most comprehensive, open-source rules & skills collection for AI coding assistants.
Works with **Cursor**, **Claude Code**, **Gemini CLI**, **GitHub Copilot**, and more.

---

[![Stars](https://img.shields.io/github/stars/hoangatg/ai-agent-toolkit?style=for-the-badge&logo=github&color=yellow)](https://github.com/hoangatg/ai-agent-toolkit/stargazers)
[![Forks](https://img.shields.io/github/forks/hoangatg/ai-agent-toolkit?style=for-the-badge&logo=github&color=blue)](https://github.com/hoangatg/ai-agent-toolkit/network)
[![Issues](https://img.shields.io/github/issues/hoangatg/ai-agent-toolkit?style=for-the-badge&logo=github&color=green)](https://github.com/hoangatg/ai-agent-toolkit/issues)
[![Last Commit](https://img.shields.io/github/last-commit/hoangatg/ai-agent-toolkit?style=for-the-badge&logo=github&color=purple)](https://github.com/hoangatg/ai-agent-toolkit/commits)

[**Getting Started**](#-getting-started) · [**Agents**](#-agents-43) · [**Skills**](#-skills-95) · [**Workflows**](#-workflows-37) · [**FAQ**](#-faq)

</div>

---

## ⚡ Why AI Agent Toolkit?

Most AI coding assistants give **generic** answers. With AI Agent Toolkit, they become **domain experts** — automatically selecting the right persona, loading specialized knowledge, and following proven workflows.

```
❌ Without Toolkit:  "Build me an API"  →  Generic boilerplate code
✅ With Toolkit:     "Build me an API"  →  Auto-selects backend-specialist agent
                                          →  Loads api-patterns + database-design skills
                                          →  Follows REST best practices, adds validation,
                                             error handling, OpenAPI docs, and tests
```

### Key Features

| Feature | Description |
|---------|-------------|
| 🤖 **43 Specialist Agents** | Auto-selected by task context — from frontend to DevOps to AI/ML |
| 🧩 **95 Domain Skills** | Deep expertise modules loaded on-demand (not all at once) |
| ⚡ **37 Slash Workflows** | Type `/deploy`, `/review`, `/security` — instant structured processes |
| 🧠 **Intelligent Routing** | AI automatically picks the right agent + skills for your request |
| 🛡️ **Socratic Gate** | Asks clarifying questions before building — prevents wasted effort |
| 📋 **Spec-Driven Dev** | Define requirements first with `/spec` — the #1 trending AI methodology |

---

## 🚀 Getting Started

### 1. Clone the Toolkit

```bash
git clone https://github.com/hoangatg/ai-agent-toolkit.git
```

### 2. Copy `.agent/` to Your Project

```bash
cp -r ai-agent-toolkit/.agent /path/to/your/project/
```

### 3. Add `GEMINI.md` to Your Project Root

```bash
cp ai-agent-toolkit/GEMINI.md /path/to/your/project/
```

### 4. Start Coding with AI

Open your project in **Cursor**, **VS Code + Copilot**, or use **Claude Code** / **Gemini CLI**. The toolkit activates automatically.

> 💡 **That's it!** The AI reads `GEMINI.md` → auto-routes to the right agent → loads relevant skills → gives expert-level responses.

---

## 🏗️ How It Works

```
┌──────────────────────────────────────────────────────┐
│                    YOUR REQUEST                       │
│              "Add authentication to my app"           │
└──────────────────────┬───────────────────────────────┘
                       │
                       ▼
┌──────────────────────────────────────────────────────┐
│              🧠 INTELLIGENT ROUTING                   │
│  Analyzes request → Selects best agent automatically  │
└──────────────────────┬───────────────────────────────┘
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
    ┌──────────┐ ┌──────────┐ ┌──────────┐
    │  Agent   │ │  Skills  │ │ Workflow │
    │ backend  │ │ oauth    │ │ /feature │
    │specialist│ │ api      │ │          │
    └──────────┘ └──────────┘ └──────────┘
          │            │            │
          └────────────┼────────────┘
                       ▼
┌──────────────────────────────────────────────────────┐
│              ✅ EXPERT-LEVEL OUTPUT                    │
│  Structured code + tests + docs + security review     │
└──────────────────────────────────────────────────────┘
```

---

## 🤖 Agents (43)

Specialist AI personas auto-selected based on your task.

### Core & Orchestration

| Agent | Focus |
|-------|-------|
| `orchestrator` | Multi-agent coordination for complex tasks |
| `project-planner` | Discovery, planning, and task breakdown |
| `codebase-explorer` | Codebase analysis and navigation |

### Frontend & UI

| Agent | Focus |
|-------|-------|
| `frontend-specialist` | React, Next.js, Vue, web UI/UX |
| `angular-developer` | Angular 17+, signals, standalone components |
| `svelte-developer` | Svelte 5, SvelteKit, runes |
| `accessibility-expert` | WCAG compliance, inclusive design |

### Backend & API

| Agent | Focus |
|-------|-------|
| `backend-specialist` | Node.js, Express, API design |
| `api-designer` | API contracts, OpenAPI, GraphQL schemas |
| `java-developer` | Spring Boot, JPA, enterprise Java |
| `php-developer` | Laravel, Eloquent, modern PHP |
| `fullstack-developer` | End-to-end feature delivery |

### Data & AI

| Agent | Focus |
|-------|-------|
| `ai-ml-engineer` | LLM integration, RAG, AI agents |
| `data-engineer` | ETL pipelines, data warehousing |
| `data-scientist` | ML models, analysis, experiments |
| `database-architect` | Schema design, SQL optimization |

### Cloud & DevOps

| Agent | Focus |
|-------|-------|
| `devops-engineer` | CI/CD, Docker, Kubernetes |
| `cloud-architect` | AWS, GCP, Azure, multi-cloud |
| `edge-engineer` | Cloudflare Workers, Vercel Edge |
| `reliability-engineer` | SRE, monitoring, incident response |

### Mobile & Desktop

| Agent | Focus |
|-------|-------|
| `mobile-developer` | React Native, Flutter, iOS, Android |
| `desktop-developer` | Electron, Tauri cross-platform |
| `game-developer` | Game logic, mechanics |

### Security & Quality

| Agent | Focus |
|-------|-------|
| `security-auditor` | OWASP, penetration testing, red team |
| `test-engineer` | Testing strategies, TDD |
| `qa-automation-engineer` | E2E testing, Playwright |
| `code-reviewer` | PR reviews, code quality |
| `performance-optimizer` | Web Vitals, Lighthouse |

### Architecture & Operations

| Agent | Focus |
|-------|-------|
| `solutions-architect` | System design, ADRs, trade-offs |
| `monorepo-architect` | Turborepo, Nx, shared packages |
| `release-manager` | Versioning, changelogs, deployment |
| `migration-specialist` | Database & framework migrations |
| `code-archaeologist` | Legacy code analysis, refactoring |

### Product & Content

| Agent | Focus |
|-------|-------|
| `product-manager` | Requirements, user stories, PRDs |
| `ux-researcher` | User research, usability testing |
| `content-strategist` | SEO content, marketing copy |
| `seo-specialist` | Search ranking, visibility |
| `technical-writer` | Documentation, tutorials |
| `documentation-writer` | Project docs, manuals |

### Specialized

| Agent | Focus |
|-------|-------|
| `web3-developer` | Blockchain, smart contracts |
| `realtime-engineer` | WebSocket, live features |
| `i18n-specialist` | Internationalization |
| `debugger` | Root cause analysis |

---

## 🧩 Skills (95)

Domain-specific knowledge modules. Agents load only what's needed — keeping context efficient.

<details>
<summary><b>🎨 Frontend & UI (14 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `react-best-practices` | React & Next.js optimization (57 Vercel rules) |
| `nextjs-app-router` | Next.js 14+ App Router, Server Components |
| `vue-nuxt-expert` | Vue 3 Composition API, Nuxt 3 |
| `angular-expert` | Angular 17+ signals, standalone components |
| `svelte-expert` | Svelte 5 runes, SvelteKit |
| `astro-ssr` | Astro 4+ islands architecture |
| `htmx-alpine` | HTMX + Alpine.js lightweight interactivity |
| `tailwind-patterns` | Tailwind CSS v4 patterns |
| `frontend-design` | UI/UX design principles |
| `shadcn-radix-ui` | shadcn/ui + Radix accessible components |
| `design-system-builder` | Component libraries, design tokens |
| `3d-web-experience` | Three.js, React Three Fiber, WebGL |
| `scroll-experience` | Scroll-driven animations, GSAP, parallax |
| `web-design-guidelines` | 100+ accessibility & UX rules |

</details>

<details>
<summary><b>⚙️ Backend & API (8 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `api-patterns` | REST, GraphQL, tRPC design |
| `nodejs-best-practices` | Node.js async, security, architecture |
| `python-patterns` | Python standards, project structure |
| `fastapi-pro` | FastAPI async APIs, Pydantic v2 |
| `graphql-expert` | Schema design, resolvers, federation |
| `java-spring-boot` | Spring Boot 3.x, JPA, Spring Security |
| `php-laravel` | Laravel 11+, Eloquent, Livewire |
| `api-rate-limiting` | Rate limiting, throttling patterns |

</details>

<details>
<summary><b>🗄️ Database & ORM (4 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `database-design` | Schema design, indexing, optimization |
| `drizzle-orm` | Type-safe SQL, migrations |
| `redis-caching` | Redis patterns, caching, pub/sub |
| `supabase-firebase` | BaaS: Supabase + Firebase |

</details>

<details>
<summary><b>🤖 AI & LLM (5 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `prompt-engineering` | Prompt strategies, chaining, few-shot |
| `rag-engineer` | RAG pipelines, vector search, chunking |
| `ai-agents-architect` | Multi-agent systems, tool use |
| `llm-app-patterns` | Production LLM: streaming, caching, fallbacks |
| `mcp-builder` | Model Context Protocol server building |

</details>

<details>
<summary><b>☁️ Cloud & Infrastructure (11 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `docker-expert` | Containers, multi-stage builds |
| `aws-serverless` | Lambda, DynamoDB, API Gateway |
| `kubernetes-architect` | K8s, Helm, GitOps |
| `terraform-specialist` | Infrastructure as Code |
| `edge-computing` | Cloudflare Workers, Vercel Edge, Deno Deploy |
| `ci-cd-pipelines` | GitHub Actions, GitLab CI |
| `vercel-deployment` | Vercel: preview, edge, ISR |
| `monorepo-management` | Turborepo, Nx, pnpm workspaces |
| `deployment-procedures` | Safe deployment workflows |
| `server-management` | Infrastructure management |
| `deno-bun-runtime` | Deno 2 & Bun modern runtimes |

</details>

<details>
<summary><b>🔒 Security (3 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `vulnerability-scanner` | OWASP 2025, supply chain security |
| `red-team-tactics` | Offensive security, MITRE ATT&CK |
| `oauth-authentication` | OAuth 2.0, JWT, SSO, RBAC |

</details>

<details>
<summary><b>🧪 Testing & Quality (6 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `testing-patterns` | Unit, integration, mocking strategies |
| `webapp-testing` | E2E with Playwright |
| `tdd-workflow` | Test-driven development |
| `visual-regression-testing` | Screenshot comparison, Chromatic |
| `code-review-checklist` | Code review standards |
| `lint-and-validate` | Linting, validation |

</details>

<details>
<summary><b>📱 Mobile & Desktop (4 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `mobile-design` | Mobile UI/UX patterns |
| `react-native-expert` | React Native, Expo |
| `flutter-expert` | Flutter/Dart, widget architecture |
| `electron-tauri` | Desktop apps: Electron + Tauri |

</details>

<details>
<summary><b>🏛️ Architecture (6 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `architecture` | System design patterns |
| `microservices-patterns` | Service decomposition, resilience |
| `domain-driven-design` | Bounded contexts, DDD |
| `event-sourcing-architect` | Event sourcing, CQRS |
| `spec-driven-development` | Specs-first, Manus-style planning |
| `app-builder` | Full-stack app scaffolding |

</details>

<details>
<summary><b>🛠️ Languages & Runtime (6 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `typescript-expert` | Advanced types, generics |
| `rust-pro` | Rust 1.75+, async, systems |
| `golang-pro` | Go concurrency, error handling |
| `zod-validation` | Zod schema validation |
| `zustand-state-management` | Zustand React state |
| `bash-linux` | Linux commands, scripting |

</details>

<details>
<summary><b>💼 Business & Product (6 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `product-manager-toolkit` | PRD, RICE, user stories |
| `copywriting` | Marketing copy, landing pages |
| `pricing-strategy` | SaaS pricing, tier design |
| `analytics-tracking` | GA4, PostHog, conversion |
| `seo-fundamentals` | SEO, E-E-A-T, Core Web Vitals |
| `geo-fundamentals` | GenAI search optimization |

</details>

<details>
<summary><b>📡 Real-time & Communication (3 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `websocket-realtime` | WebSocket, SSE, live collaboration |
| `message-queues` | Kafka, RabbitMQ, event streaming |
| `email-development` | HTML email, deliverability |

</details>

<details>
<summary><b>🔧 Observability & Operations (3 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `observability-engineer` | Monitoring, logging, alerting |
| `incident-responder` | Incident response, runbooks |
| `performance-profiling` | Web Vitals, optimization |

</details>

<details>
<summary><b>💳 Integrations (3 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `stripe-integration` | Payments, subscriptions |
| `web3-blockchain` | Smart contracts, dApps |
| `i18n-localization` | Internationalization, RTL |

</details>

<details>
<summary><b>📝 Workflow & Planning (8 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `clean-code` | Coding standards (global) |
| `plan-writing` | Task planning, breakdown |
| `brainstorming` | Socratic questioning |
| `git-workflow` | Branching, commits, PR |
| `create-pr` | Clean PR creation |
| `documentation-templates` | Doc formats |
| `behavioral-modes` | Agent operational modes |
| `intelligent-routing` | Auto agent selection |

</details>

<details>
<summary><b>🎮 Game & Specialty (3 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `game-development` | Game logic, mechanics |
| `parallel-agents` | Multi-agent orchestration |
| `powershell-windows` | Windows PowerShell |

</details>

<details>
<summary><b>🔍 Debugging (2 skills)</b></summary>

| Skill | Description |
|-------|-------------|
| `systematic-debugging` | 4-phase debugging methodology |
| `ui-ux-pro-max` | 50 styles, 21 palettes, 50 fonts |

</details>

---

## ⚡ Workflows (37)

Type a slash command. Get a structured workflow. Instant productivity.

### Development

| Command | Description |
|---------|-------------|
| `/create` | Create new application from scratch |
| `/enhance` | Improve existing code |
| `/feature` | End-to-end feature development |
| `/component` | Design, build, test UI components |
| `/scaffold` | Project scaffolding and boilerplate |
| `/api` | API design and documentation |
| `/refactor` | Code refactoring with safety nets |
| `/design` | UI/UX design with 50 styles |

### Quality & Review

| Command | Description |
|---------|-------------|
| `/review` | Systematic code review |
| `/test` | Generate and run tests |
| `/lint` | Lint and auto-fix issues |
| `/security` | Full security audit (OWASP) |
| `/accessibility` | WCAG compliance audit |
| `/performance` | Lighthouse + profiling |
| `/optimize` | Bundle size + performance optimization |
| `/storybook` | Component story creation |
| `/dependency` | Dependency audit + updates |

### Planning & Discovery

| Command | Description |
|---------|-------------|
| `/plan` | Task breakdown and planning |
| `/spec` | Spec-driven development (Manus-style) |
| `/brainstorm` | Socratic discovery and ideation |
| `/orchestrate` | Multi-agent coordination |

### Operations & Release

| Command | Description |
|---------|-------------|
| `/deploy` | Deploy to production |
| `/release` | Version bump + changelog + tag |
| `/migrate` | Database/framework migration |
| `/monitor` | Setup monitoring and alerts |
| `/backup` | Backup and disaster recovery |
| `/i18n` | Internationalization setup |

### Documentation

| Command | Description |
|---------|-------------|
| `/docs` | Auto-generate documentation |
| `/changelog` | Generate changelog from commits |
| `/readme` | Create/update project README |

### AI & Data

| Command | Description |
|---------|-------------|
| `/ai` | Add AI features (chat, RAG, embeddings) |
| `/data` | Data pipeline setup |
| `/prompt` | Prompt engineering + optimization |

### Utilities

| Command | Description |
|---------|-------------|
| `/debug` | Systematic debugging |
| `/preview` | Preview changes locally |
| `/status` | Check project status |

---

## 🔧 Compatibility

| Tool | Status | How |
|------|--------|-----|
| **Cursor** | ✅ Full support | Reads `.agent/` directory natively |
| **Claude Code** | ✅ Full support | Uses SKILL.md + agent files |
| **Gemini CLI** | ✅ Full support | Reads `GEMINI.md` as entry point |
| **GitHub Copilot** | ✅ Works | Reads markdown rules |
| **Windsurf** | ✅ Works | Compatible with .cursorrules format |
| **Any AI IDE** | ✅ Works | Standard markdown format |

---

## 📁 Project Structure

```
your-project/
├── GEMINI.md                    # Entry point (AI reads this first)
└── .agent/
    ├── ARCHITECTURE.md          # Full system reference
    ├── agents/                  # 43 specialist agents
    │   ├── frontend-specialist.md
    │   ├── backend-specialist.md
    │   ├── ai-ml-engineer.md
    │   └── ...
    ├── skills/                  # 95 domain skills
    │   ├── react-best-practices/
    │   │   └── SKILL.md
    │   ├── api-patterns/
    │   │   └── SKILL.md
    │   └── ...
    ├── workflows/               # 37 slash commands
    │   ├── create.md
    │   ├── deploy.md
    │   └── ...
    ├── scripts/                 # Validation scripts
    └── rules/                   # Global rules
```

---

## 🤝 Contributing

We welcome contributions! Here's how:

1. **🍴 Fork** this repository
2. **🌿 Create** a feature branch (`git checkout -b feature/amazing-skill`)
3. **💾 Commit** your changes (`git commit -m 'Add amazing skill'`)
4. **🚀 Push** to the branch (`git push origin feature/amazing-skill`)
5. **📝 Open** a Pull Request

### Adding a New Skill

Create `skills/your-skill-name/SKILL.md`:

```markdown
---
name: your-skill-name
description: Brief description of what this skill does.
---

# Your Skill Name

> Core philosophy or guiding principle

## Key Patterns
...

## Anti-Patterns
...
```

---

## ❓ FAQ

<details>
<summary><b>Does it slow down my AI assistant?</b></summary>

No. Skills are loaded **on-demand** based on task context. Only 2-3 skills are active at a time, not all 95.

</details>

<details>
<summary><b>Do I need all 43 agents?</b></summary>

No. The intelligent routing system automatically selects the right agent. You never need to manually choose one.

</details>

<details>
<summary><b>Can I customize agents and skills?</b></summary>

Yes! Everything is plain markdown — edit, add, or remove anything to fit your team's needs.

</details>

<details>
<summary><b>Does it work with my language/framework?</b></summary>

The toolkit covers: JavaScript/TypeScript, Python, Go, Rust, Java, PHP, React, Next.js, Vue, Angular, Svelte, Astro, Flutter, React Native, and more. If it's not covered, you can add your own skill in minutes.

</details>

<details>
<summary><b>Is it free?</b></summary>

Yes! This is 100% open source and free to use.

</details>

---

<div align="center">

### ☕ Support This Project

If AI Agent Toolkit saves you time, consider supporting its development!

[![Ko-fi](https://img.shields.io/badge/Ko--fi-Support%20Me-F16061?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/hoangatg)

Your support helps maintain and expand the toolkit with new agents, skills, and workflows.

---

### ⭐ If this toolkit improves your AI coding workflow, give it a star!

**It helps others discover the project and motivates continued development.**

[![Star History Chart](https://api.star-history.com/svg?repos=hoangatg/ai-agent-toolkit&type=Date)](https://star-history.com/#hoangatg/ai-agent-toolkit)

---

**Built with ❤️ for the AI-assisted development community**

[Report Bug](https://github.com/hoangatg/ai-agent-toolkit/issues) · [Request Feature](https://github.com/hoangatg/ai-agent-toolkit/issues) · [Discussions](https://github.com/hoangatg/ai-agent-toolkit/discussions)

</div>

