---
name: react-native-expert
description: React Native development expertise. Navigation, native modules, performance, animations, and cross-platform patterns. Use when building mobile apps with React Native or Expo.
---

# React Native Expert

> One codebase, two platforms — done right.

---

## 1. Architecture Decisions

### Expo vs Bare Workflow

| Factor | Expo | Bare |
|--------|------|------|
| **Setup** | Minutes | Hours |
| **Native modules** | Limited (Expo SDK) | Full access |
| **OTA updates** | Built-in (EAS Update) | Manual (CodePush) |
| **Build** | EAS Build (cloud) | Local Xcode/Android Studio |
| **Best for** | 90% of apps | Custom native code needs |

> **Rule:** Start with Expo. Eject only when you must.

---

## 2. Navigation

### React Navigation Patterns

| Pattern | Use Case |
|---------|----------|
| **Stack** | Linear flows (auth, onboarding) |
| **Tab** | Main app sections |
| **Drawer** | Settings, secondary nav |
| **Modal** | Overlays, forms |
| **Deep linking** | URL-based navigation |

### Principles

| Principle | Application |
|-----------|-------------|
| **Type-safe routes** | Use TypeScript route params |
| **Lazy loading** | Load screens on demand |
| **State persistence** | Save nav state for app restart |
| **Deep links** | Configure linking for all screens |

---

## 3. State Management

| Solution | Best For |
|----------|----------|
| **React Context** | Simple, app-wide state |
| **Zustand** | Lightweight, performant |
| **Redux Toolkit** | Complex state, middleware |
| **React Query/TanStack** | Server state, caching |
| **MMKV** | Persistent local storage |

---

## 4. Performance

### Critical Optimizations

| Technique | Impact |
|-----------|--------|
| **FlatList** over ScrollView | Virtual rendering for lists |
| **React.memo** | Prevent unnecessary re-renders |
| **useCallback/useMemo** | Memoize callbacks and values |
| **Hermes engine** | Faster startup, less memory |
| **Image optimization** | Use expo-image or FastImage |
| **Native driver** | `useNativeDriver: true` for animations |

### Performance Budget

| Metric | Target |
|--------|--------|
| **App startup** | < 2 seconds |
| **Frame rate** | 60 fps |
| **Bundle size** | < 20MB (initial) |
| **RAM usage** | < 200MB |

---

## 5. Animations

| Library | Use Case |
|---------|----------|
| **Reanimated 3** | Complex gesture-driven animations |
| **Moti** | Declarative animations (simple) |
| **Skia** | Custom drawing, shaders |
| **Lottie** | After Effects animations |

---

## 6. Native Integration

| Need | Solution |
|------|---------|
| **Camera** | expo-camera, react-native-vision-camera |
| **Maps** | react-native-maps |
| **Push notifications** | expo-notifications, FCM |
| **Biometrics** | expo-local-authentication |
| **File system** | expo-file-system |
| **Payments** | Stripe React Native SDK |

---

## 7. Testing

| Type | Tool |
|------|------|
| **Unit** | Jest + React Native Testing Library |
| **Component** | @testing-library/react-native |
| **E2E** | Detox or Maestro |
| **Visual** | Storybook for React Native |

---

## 8. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| ScrollView for long lists | FlatList or FlashList |
| Inline styles everywhere | StyleSheet.create() |
| Console.log in production | Remove with babel plugin |
| Sync storage (AsyncStorage for large data) | MMKV for fast storage |
| Ignore platform differences | Platform.select() when needed |

---

> **Remember:** React Native is not "React for mobile." Touch interactions, memory constraints, and platform conventions require mobile-first thinking.
