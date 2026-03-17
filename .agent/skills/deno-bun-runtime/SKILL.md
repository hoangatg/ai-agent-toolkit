---
name: deno-bun-runtime
description: Modern JavaScript/TypeScript runtimes — Deno 2 and Bun. Native TypeScript support, built-in tooling, and performance optimizations. Use when building with Deno, Bun, or evaluating runtime alternatives to Node.js.
---

# Deno & Bun Runtimes

> Next-generation JS/TS runtimes with built-in tooling and superior performance.

## Comparison

| Feature | Node.js | Deno 2 | Bun |
|---------|---------|--------|-----|
| **TypeScript** | Needs build | Native | Native |
| **Package Manager** | npm/pnpm | npm compatible | bun install (fastest) |
| **Test Runner** | Jest/Vitest | Built-in | Built-in |
| **Bundler** | Webpack/Vite | Built-in | Built-in (fastest) |
| **Security** | Unrestricted | Permissions model | Unrestricted |
| **HTTP Server** | Express/Fastify | Deno.serve | Bun.serve |
| **Speed** | Baseline | 1.5-2x faster | 3-4x faster |

---

## Deno 2 Key Features

- **npm compatibility**: Import npm packages directly
- **Permissions**: `--allow-net`, `--allow-read`, `--allow-env`
- **LSP**: Built-in language server
- **Deploy**: Deno Deploy for edge computing

## Bun Key Features

- **Speed**: Fastest JS runtime, built on JavaScriptCore
- **All-in-one**: Runtime + bundler + test runner + package manager
- **Node.js compatible**: Drop-in replacement for most Node.js code
- **SQLite**: Built-in SQLite support
