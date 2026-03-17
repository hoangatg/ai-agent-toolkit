---
name: flutter-expert
description: Flutter and Dart development expertise. Widget architecture, state management, platform channels, and cross-platform patterns. Use when building mobile apps with Flutter.
---

# Flutter Expert

> Beautiful apps, natively compiled, from a single codebase.

---

## 1. Architecture Patterns

### App Architecture

| Pattern | Best For |
|---------|----------|
| **Clean Architecture** | Large apps, testability |
| **BLoC** | Event-driven, reactive |
| **MVVM** | Simple separation of concerns |
| **Riverpod** | Modern, compile-safe DI |

### Project Structure

```
lib/
├── main.dart
├── app/              # App config, themes, routes
├── core/             # Shared utilities, constants
├── features/         # Feature-first organization
│   ├── auth/
│   │   ├── data/     # Repositories, data sources
│   │   ├── domain/   # Entities, use cases
│   │   └── presentation/ # Screens, widgets, state
│   └── home/
└── shared/           # Shared widgets, services
```

---

## 2. State Management

| Solution | Complexity | Best For |
|----------|-----------|----------|
| **setState** | Low | Simple local state |
| **Provider** | Low-Med | Basic DI + state |
| **Riverpod** | Medium | Type-safe, testable, modern |
| **BLoC/Cubit** | Medium | Event-driven, enterprise |
| **GetX** | Low | Rapid prototyping (not for prod) |

---

## 3. Widget Design

### Principles

| Principle | Application |
|-----------|-------------|
| **Composition** | Small widgets composed together |
| **Const constructors** | Mark widgets `const` when possible |
| **Keys** | Use keys for list items, AnimatedSwitcher |
| **Builder pattern** | Lazy building for performance |
| **Separation** | UI widgets vs logic widgets |

### Custom Widget Checklist

- Does it have a const constructor?
- Is it stateless (if possible)?
- Does it expose enough customization?
- Is it reusable across features?

---

## 4. Navigation

| Solution | Features |
|----------|----------|
| **GoRouter** | Declarative, deep linking, type-safe |
| **Navigator 2.0** | Full control, complex flows |
| **Auto Route** | Code generation, type-safe |

---

## 5. Performance

| Technique | Impact |
|-----------|--------|
| **const widgets** | Skip rebuild entirely |
| **RepaintBoundary** | Isolate repaint regions |
| **ListView.builder** | Lazy rendering for lists |
| **Image caching** | cached_network_image |
| **Compute isolates** | Heavy computation off main thread |
| **DevTools profiler** | Find jank and memory leaks |

---

## 6. Platform Integration

| Need | Solution |
|------|---------|
| **Native code** | Platform channels (MethodChannel) |
| **Background work** | WorkManager, background_fetch |
| **Notifications** | firebase_messaging + flutter_local_notifications |
| **Storage** | shared_preferences, Hive, Isar |
| **HTTP** | Dio with interceptors |

---

## 7. Testing

| Type | Tool |
|------|------|
| **Unit** | flutter_test, mockito |
| **Widget** | WidgetTester, pumpWidget |
| **Integration** | integration_test package |
| **Golden** | Visual regression testing |

---

## 8. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| God widget (1000+ lines) | Extract to smaller widgets |
| setState for global state | Riverpod or BLoC |
| Ignore const constructors | Mark everything const possible |
| Network calls in widgets | Use repositories + use cases |
| Skip null safety | Full null-safe code |

---

> **Remember:** Flutter's power is in composition. Build small, testable widgets and compose them into features. The widget tree is your architecture.
