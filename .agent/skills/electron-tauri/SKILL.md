---
name: electron-tauri
description: Desktop application development with Electron and Tauri. Cross-platform builds, native integration, and security. Use when building desktop apps for Windows, macOS, and Linux.
---

# Electron & Tauri

> Web technologies, native desktop. Best of both worlds.

---

## 1. Framework Selection

| Factor | Electron | Tauri |
|--------|----------|-------|
| **Runtime** | Chromium + Node.js | System WebView + Rust |
| **Bundle size** | 100-200MB+ | 5-30MB |
| **RAM usage** | High (150MB+) | Low (30-50MB) |
| **Language** | JavaScript/TypeScript | Rust (backend) + JS (frontend) |
| **Maturity** | Very mature | Growing rapidly |
| **Best for** | Feature-rich, quick dev | Performance, small bundles |

### Decision

```
Need small bundle + performance? → Tauri
Need mature ecosystem + quick dev? → Electron
Need heavy Node.js integration? → Electron
Building with Rust knowledge? → Tauri
```

---

## 2. Electron Architecture

### Process Model

| Process | Responsibility |
|---------|---------------|
| **Main** | Window management, system APIs, lifecycle |
| **Renderer** | UI (React, Vue, etc.), web content |
| **Preload** | Secure bridge between main and renderer |

### Security Model

| Principle | Implementation |
|-----------|---------------|
| **Context isolation** | ON (default since v12) |
| **Node integration** | OFF in renderer |
| **Preload scripts** | Expose only needed APIs |
| **CSP headers** | Strict Content Security Policy |
| **Remote module** | Disabled |

---

## 3. Tauri Architecture

### Process Model

| Layer | Technology |
|-------|-----------|
| **Frontend** | Any web framework (React, Vue, Svelte) |
| **Backend** | Rust (commands, system access) |
| **Bridge** | `invoke()` for frontend → Rust calls |

### Key Features

| Feature | Purpose |
|---------|---------|
| **Commands** | Typed Rust functions callable from JS |
| **Events** | Bidirectional event system |
| **Plugins** | Extend with file system, HTTP, shell |
| **Updater** | Built-in auto-update |

---

## 4. Common Features

| Feature | Electron | Tauri |
|---------|----------|-------|
| **Auto-update** | electron-updater | Built-in updater |
| **Tray** | Tray API | SystemTray |
| **Notifications** | Notification API | Plugin |
| **File system** | Node.js fs | Tauri fs plugin |
| **Menu** | Menu API | Menu builder |
| **Shortcuts** | globalShortcut | GlobalShortcut |

---

## 5. Build & Distribution

### Electron

| Tool | Purpose |
|------|---------|
| **electron-builder** | Package for all platforms |
| **electron-forge** | Official tooling, plugins |
| **Code signing** | macOS notarization, Windows cert |

### Tauri

| Tool | Purpose |
|------|---------|
| **tauri build** | Built-in bundler |
| **GitHub Actions** | CI/CD cross-platform builds |
| **Updater** | JSON-based update manifest |

---

## 6. Performance

| Technique | Platform |
|-----------|----------|
| Lazy load windows | Electron |
| Use system WebView (not bundled Chromium) | Tauri |
| Minimize IPC calls | Both |
| Use native modules for heavy work | Both |
| Preload critical resources | Both |

---

## 7. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Node integration in renderer | Context isolation + preload |
| Bundle entire node_modules | Tree-shake, optimize |
| Skip code signing | Sign for all platforms |
| Trust renderer input | Validate in main/Rust backend |
| Ignore bundle size | Monitor and optimize |

---

> **Remember:** Desktop apps are a distribution mechanism for your web app with superpowers. Keep the web part fast, use native APIs only when web APIs aren't enough.
