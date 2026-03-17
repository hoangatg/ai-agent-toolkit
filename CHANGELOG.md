# Changelog

All notable changes to the AI Agent Toolkit will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/2.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]


## [3.1.0] - 2026-03-17

### Added (GitHub Research Expansion)

- **15 New Skills** based on community research (Anthropic, VoltAgent, alirezarezvani/claude-skills):
    - **Trending**: `spec-driven-development` (Manus-style planning, #1 trending AI dev methodology)
    - **Language Ecosystems**: `java-spring-boot`, `php-laravel`
    - **Frameworks**: `angular-expert`, `svelte-expert`, `astro-ssr`, `htmx-alpine`
    - **Modern Runtime**: `deno-bun-runtime`
    - **UI Libraries**: `shadcn-radix-ui`
    - **State & Data**: `zustand-state-management`, `drizzle-orm`, `zod-validation`
    - **Infrastructure**: `edge-computing`, `api-rate-limiting`
    - **Testing**: `visual-regression-testing`
- **5 New Agents**: `java-developer`, `php-developer`, `angular-developer`, `svelte-developer`, `edge-engineer`
- **5 New Workflows**: `/spec`, `/storybook`, `/optimize`, `/dependency`, `/i18n`
- **Final counts**: 43 Agents · 95 Skills · 37 Workflows


## [3.0.0] - 2026-03-15

### Added

- **20 New Specialist Agents**: `ai-ml-engineer`, `data-engineer`, `data-scientist`, `solutions-architect`, `api-designer`, `cloud-architect`, `accessibility-expert`, `reliability-engineer`, `code-reviewer`, `technical-writer`, `ux-researcher`, `content-strategist`, `desktop-developer`, `web3-developer`, `fullstack-developer`, `realtime-engineer`, `release-manager`, `migration-specialist`, `i18n-specialist`, `monorepo-architect`
- **20 New Workflows**: `/review`, `/refactor`, `/scaffold`, `/api`, `/component`, `/feature`, `/security`, `/performance`, `/accessibility`, `/lint`, `/release`, `/migrate`, `/monitor`, `/backup`, `/docs`, `/changelog`, `/readme`, `/ai`, `/data`, `/prompt`
- `/design` workflow as a cleaner alias for `/ui-ux-pro-max`

### Changed

- Merged `penetration-tester` into `security-auditor` (offensive + defensive in one agent)
- Merged `product-owner` into `product-manager` (unified product strategy)
- Renamed `explorer-agent` to `codebase-explorer` for clarity
- Updated `ARCHITECTURE.md` with comprehensive agent/workflow reference
- **Final counts**: 38 Agents · 80 Skills · 31 Workflows


## [2.1.0] - 2026-03-15

### Added

- **43 New Skills** across all domains, bringing total from 37 to **80 skills**:
    - **AI & LLM** (4): `prompt-engineering`, `rag-engineer`, `ai-agents-architect`, `llm-app-patterns`
    - **DevOps & Cloud** (7): `docker-expert`, `aws-serverless`, `kubernetes-architect`, `terraform-specialist`, `ci-cd-pipelines`, `vercel-deployment`, `monorepo-management`
    - **Architecture** (3): `microservices-patterns`, `domain-driven-design`, `event-sourcing-architect`
    - **Languages** (3): `typescript-expert`, `golang-pro`, `fastapi-pro`
    - **Frameworks** (4): `nextjs-app-router`, `vue-nuxt-expert`, `react-native-expert`, `flutter-expert`
    - **Business & Product** (4): `product-manager-toolkit`, `copywriting`, `pricing-strategy`, `analytics-tracking`
    - **Observability** (2): `observability-engineer`, `incident-responder`
    - **Web Experience** (3): `3d-web-experience`, `scroll-experience`, `design-system-builder`
    - **Data & Backend** (4): `graphql-expert`, `redis-caching`, `message-queues`, `data-engineering`
    - **Auth & Real-time** (2): `oauth-authentication`, `websocket-realtime`
    - **Platform** (2): `supabase-firebase`, `email-development`
    - **Desktop & Web3** (2): `electron-tauri`, `web3-blockchain`
    - **Integration** (1): `stripe-integration`
    - **Workflow** (2): `git-workflow`, `create-pr`

### Changed

- **Total Skills**: 37 → 80
- **Coverage**: ~90% → ~99% full-stack development
- **ARCHITECTURE.md**: Expanded with new skill categories and agent-skill mappings
- **Agent skill mappings**: Enhanced for all specialist agents

## [2.0.2] - 2026-02-04
- **New Skills**:
    - `rust-pro` - Master Rust 1.75+ 
- **Agent Workflows**:
    - Updated `orchestrate.md` fix output turkish


## [2.0.1] - 2026-01-26

### Added

- **Agent Flow Documentation**: New comprehensive workflow documentation
    - Added `.agent/AGENT_FLOW.md` - Complete agent flow architecture guide
    - Documented Agent Routing Checklist (mandatory steps before code/design work)
    - Documented Socratic Gate Protocol for requirement clarification
    - Added Cross-Skill References pattern documentation
- **New Skills**:
    - `react-best-practices` - Consolidated Next.js and React expertise
    - `web-design-guidelines` - Professional web design standards and patterns

### Changed

- **Skill Consolidation**: Merged `nextjs-best-practices` and `react-patterns` into unified `react-best-practices` skill
- **Architecture Updates**:
    - Enhanced `.agent/ARCHITECTURE.md` with improved flow diagrams
    - Updated `.agent/rules/GEMINI.md` with Agent Routing Checklist
- **Agent Updates**:
    - Updated `frontend-specialist.md` with new skill references
    - Updated `qa-automation-engineer.md` with enhanced testing workflows
- **Frontend Design Skill**: Enhanced `frontend-design/SKILL.md` with cross-references to `web-design-guidelines`

### Removed

- Deprecated `nextjs-best-practices` skill (consolidated into `react-best-practices`)
- Deprecated `react-patterns` skill (consolidated into `react-best-practices`)

### Fixed

- **Agent Flow Accuracy**: Corrected misleading terminology in AGENT_FLOW.md
    - Changed "Parallel Execution" → "Sequential Multi-Domain Execution"
    - Changed "Integration Layer" → "Code Coherence" with accurate description
    - Added reality notes about AI's sequential processing vs. simulated multi-agent behavior
    - Clarified that scripts require user approval (not auto-executed)

## [2.0.0] - Unreleased

### Initial Release

- Initial release of AI Agent Toolkit
- 20 specialized AI agents
- 37 domain-specific skills
- 11 workflow slash commands
- CLI tool for easy installation and updates
- Comprehensive documentation and architecture guide

[Unreleased]: https://github.com/hoangatg/ai-agent-toolkit/compare/v2.0.0...HEAD
[2.0.0]: https://github.com/hoangatg/ai-agent-toolkit/releases/tag/v2.0.0
