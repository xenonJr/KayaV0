# 🏠 Kayaa Studio

**A browser-based 3D real estate configurator — explore properties, customize materials in real time, and request quotes directly from the owner.**

🔒 **Status:** Private (Client Deployment)

---

## Overview

Kayaa Studio lets potential property buyers explore real estate in full 3D space, customize finishes (floors, walls, countertops, fixtures), and submit their personalized configuration to the property owner for a quote — all from the browser with zero downloads.

Built with Unity and C#, deployed on the web via WebGL.

---

## Tech Stack

| Layer | Tech |
|-------|------|
| Engine | Unity |
| Language | C# |
| Deployment | WebGL (browser-based) |
| Materials | PBR Textures, Scriptable Objects |
| UI | Unity UI Toolkit |
| API | REST (JSON) for quote submissions |
| Optimization | Texture atlasing, LOD, draw call batching, lightmap baking |

---

## Core Features

### 🏗️ 3D Property Visualization
- Full 3D walkable property models rendered in the browser via WebGL
- **Orbit Mode** — top-down exploration for room layout and overview
- **Walk-Through Mode** — first-person navigation for immersive room-by-room experience
- Smooth camera transitions with configurable input for mouse, touch, and trackpad

### 🎨 Real-Time Material Customization
- Dynamic material swapping on any surface — floors, walls, countertops, ceilings, fixtures
- Built on **Unity Scriptable Objects** — each surface is mapped to a material slot that swaps at runtime
- **PBR textures** (albedo, normal, roughness, metallic) for physically accurate rendering
- Live preview — every material change updates the 3D model instantly with no reload
- Clean side panel UI for browsing material categories and previewing swatches

### 📩 Quote Request System
- Users finalize customization and submit a configuration snapshot to the property owner
- Captures: property ID, room-by-room material selections, optional notes, timestamp
- Serialized to **JSON** and sent via **REST API** to the owner's dashboard
- Eliminates ambiguity — owner sees exactly what the buyer wants

### ⚡ WebGL Performance
- Optimized asset pipeline — models decimated to WebGL-safe polygon counts
- Texture compression with platform-appropriate formats (ETC2/ASTC)
- **LOD (Level of Detail)** groups — distant objects use simpler meshes automatically
- Draw call batching and aggressive lightmap baking to reduce real-time computation
- Loads in **under 8 seconds** on standard broadband, runs at **30+ FPS** on mid-range hardware

---

## Architecture

```
[Browser — WebGL Runtime]
        ↓
[Unity Application (C#)]
   ├── Scene Manager      → Property loading, camera control
   ├── Material System     → Scriptable Objects, PBR swap logic
   ├── UI Toolkit Overlay  → Material picker, category browser
   └── Quote Module        → Config snapshot → JSON → REST API
                                                       ↓
                                              [Owner Dashboard]
```

---

## Problem it solves

Property buying relies on flat photos and static floor plans. Buyers can't visualize how a space feels, compare material choices, or communicate preferences clearly. Property owners lose leads who can't picture themselves in the space. Kayaa Studio turns passive listings into interactive experiences — explore, customize, and request a quote without a site visit or software download.

---

## Getting Started

```bash
git clone https://github.com/xenonJr/kayaa-studio.git

# Open in Unity 2022.3+ LTS
# Build: File → Build Settings → WebGL → Build
# Serve locally or deploy to any static hosting
```

---

## Screenshots

> *Coming soon*

---

## License

MIT
