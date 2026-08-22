---
name: pinterest-gestalt
description: Official Pinterest Gestalt Design System guidelines, React component patterns, masonry grids, pin cards, color tokens, and design-md specifications. Use when designing and building Pinterest-inspired React and Next.js interfaces.
---

# Pinterest Gestalt Design System & React UI Patterns

Gestalt is Pinterest’s official design system. It provides a photography-first discovery interface where the chrome recedes and imagery takes center stage.

## 1. Core Visual Philosophy
- **Imagery is Load-Bearing**: The masonry pin grid is the primary visual hero.
- **Chrome Recedes**: Warm cream/charcoal neutral palette (`#e5e5e0`, `#fbfbf9`, `#121316`, `#262622`) with quiet borders and zero decorative gradients.
- **Single Saturated Accent**: Pinterest Red (`#e60023` / pressed `#cc001f`) anchors the primary call-to-action buttons.
- **Rounded Fluidity**:
  - Pin Cards: `rounded-2xl` (16px border-radius)
  - Pill Buttons & Search Bars: `rounded-full` (9999px)
  - Gutters: Tight 8px to 16px columns.
- **Zero-CLS Masonry**: Calculate `aspectRatio: width / height` on cards before images load to prevent layout shifts.

## 2. Color Tokens (Light & Dark)

```css
/* Pinterest Gestalt Tokens */
:root {
  --gestalt-red: #e60023;
  --gestalt-red-hover: #cc001f;
  --gestalt-red-active: #a30018;

  /* Surfaces */
  --gestalt-canvas-light: #ffffff;
  --gestalt-surface-light: #fbfbf9;
  --gestalt-card-light: #f6f6f3;
  --gestalt-border-light: #dadad3;

  --gestalt-canvas-dark: #0a0a0c;
  --gestalt-surface-dark: #121316;
  --gestalt-card-dark: #1a1c22;
  --gestalt-border-dark: #242730;

  /* Text */
  --gestalt-text-primary: #111111;
  --gestalt-text-secondary: #62625b;
  --gestalt-text-dark-primary: #f4f4f6;
  --gestalt-text-dark-secondary: #9ea3b0;
}
```

## 3. Gestalt Component Patterns

### A. The Search Bar
- Fully rounded (`rounded-full`), height 48px.
- Subtle background (`#f6f6f3` in light, `#1a1c22` in dark) with magnifying glass icon.
- Expands/focuses smoothly with clear search tag suggestions and color picker swatches.

### B. Pin Card
- 16px rounded corners (`rounded-2xl`).
- Hover overlay with:
  - Top Right: Save / Favorite pill button in Pinterest Red (`#e60023`).
  - Top Left: Quality Score badge (e.g. `★ 8.0`).
  - Bottom: Catchy Instagram caption and category tag chips (`#soles`, `#barefoot`).
  - Bottom Right: Share / Link button.

### C. Masonry Grid
- Responsive column layout:
  - Mobile (< 640px): 2 columns
  - Tablet (640px – 1024px): 3 columns
  - Desktop (1024px – 1440px): 4 columns
  - Wide Screen (> 1440px): 5–6 columns
- Seamless virtualization or infinite scroll using `IntersectionObserver`.

### D. Modal / Lightbox (Sheet / Dialog)
- Soft darkened scrim backdrop (`backdrop-blur-md bg-black/80`).
- Split layout:
  - Left: Fullscreen responsive image with zoom.
  - Right: Metadata panel with human caption, AI visual breakdown, clickable tag cloud, and related image recommendations.

## 4. References & Documentation
- **Official Gestalt Repo**: https://github.com/pinterest/gestalt
- **Gestalt Design MD Tokens**: https://getdesign.md/pinterest/design-md
- **Local Comprehensive Design Specs**: [DESIGN.md](../../DESIGN.md)
