---
name: 3d-web-experience
description: Three.js, React Three Fiber, and WebGL for immersive 3D web experiences. Use when building 3D visualizations, product configurators, or interactive 3D content.
---

# 3D Web Experience

> Make the web dimensional. Create experiences, not just pages.

---

## 1. Technology Selection

| Technology | Best For |
|-----------|----------|
| **Three.js** | Full control, vanilla JS |
| **React Three Fiber** | React ecosystem, declarative |
| **Babylon.js** | Game-like experiences |
| **A-Frame** | Quick prototypes, VR/AR |
| **Spline** | Design-first, no-code |

---

## 2. React Three Fiber Architecture

### Component Structure

```
<Canvas>
  <Scene>
    <Lighting />
    <Camera />
    <Models />
    <Effects />
  </Scene>
</Canvas>
```

### Key Libraries

| Library | Purpose |
|---------|---------|
| **@react-three/fiber** | React renderer for Three.js |
| **@react-three/drei** | Helpers, controls, abstractions |
| **@react-three/postprocessing** | Visual effects |
| **@react-three/rapier** | Physics engine |
| **leva** | Debug controls/GUI |

---

## 3. Performance Optimization

| Technique | Impact |
|-----------|--------|
| **Instancing** | Render 1000s of same geometry |
| **LOD (Level of Detail)** | Reduce geometry at distance |
| **Texture compression** | KTX2, basis textures |
| **Frustum culling** | Only render visible objects |
| **Object pooling** | Reuse instead of create/destroy |
| **Web Workers** | Offload heavy computation |

### Performance Budget

| Metric | Target |
|--------|--------|
| **Draw calls** | < 100 |
| **Triangles** | < 500K (mobile), < 2M (desktop) |
| **Texture memory** | < 100MB |
| **Frame rate** | 60fps (desktop), 30fps (mobile) |

---

## 4. 3D Asset Pipeline

| Format | Use Case |
|--------|----------|
| **glTF/GLB** | Standard, web-optimized |
| **DRACO** | Compressed geometry |
| **KTX2** | Compressed textures |
| **HDR/EXR** | Environment maps |

---

## 5. Common Use Cases

| Use Case | Key Techniques |
|----------|---------------|
| **Product configurator** | Materials, camera, interaction |
| **Data visualization** | Instancing, animation |
| **Portfolio/landing** | Scroll-driven animation |
| **Game** | Physics, collision, state |
| **AR/VR** | WebXR, spatial interaction |

---

## 6. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Load uncompressed models | Use DRACO/glTF-transform |
| Skip mobile optimization | Test on low-end devices |
| Render when hidden | Pause when offscreen |
| Animation in every frame | Use delta time, RAF |
| Block main thread | Heavy work in Web Workers |

---

> **Remember:** 3D on the web should enhance the experience, not slow it down. Performance is a feature — always profile on real devices.
