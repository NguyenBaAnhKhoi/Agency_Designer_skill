---
name: brand-motif-engine
description: "Generate modular vector graphic systems, Key Motifs, seamless SVG patterns, geometric brand devices, and exported <defs>/<symbol> libraries to guarantee 100% visual consistency across all campaign collateral."
last-updated: 2026-10-19
---

# 🧬 Brand Motif Engine — Vector DNA & Seamless Graphic System

## 1. Core Mission & Philosophy
A successful creative campaign is anchored by its **Key Motif** (Bộ Gen Họa Tiết). Whether it is the concentric soundwaves of Spotify Wrapped, the geometric ribbons of Apple Event, or the cybernetic wireframes of a music festival, the Motif is the invisible thread linking a 20-meter billboard to a 3-centimeter wristband.

### Root Problem Solved:
When asked to create collateral separately, AI agents invent new decorative elements on every prompt, destroying brand cohesion. The **Brand Motif Engine** defines the primary graphic devices upfront as modular, production-ready SVG `<defs>` and `<symbol>` components, ensuring **zero visual drift**.

---

## 2. Motif Architecture: The 4 Core Graphic Layers

```
┌────────────────────────────────────────────────────────────────────────┐
│                        MOTIF SYSTEM ARCHITECTURE                       │
├─────────────────────┬───────────────────────┬──────────────────────────┤
│ 1. KEY MOTIF (HERO) │ 2. MODULAR BADGES     │ 3. SEAMLESS PATTERNS     │
├─────────────────────┼───────────────────────┼──────────────────────────┤
│ The core symbolic   │ Geometric framing,    │ Seamless background      │
│ mark derived from   │ die-cut container     │ textures, dot matrices,  │
│ event theme/sound   │ shapes & lockup tags  │ distortion lines         │
├─────────────────────┴───────────────────────┴──────────────────────────┤
│ 4. SVG <defs> & <symbol> LIBRARY (Injected into visual-dna.json)       │
└────────────────────────────────────────────────────────────────────────┘
```

1. **Key Motif (The Core Graphic Particle)**:
   - Must be mathematically constructed (concentric arcs, hyperbolic curves, isometric starbursts, modular glyphs).
   - Designed to work in single-color silhouette (for foil stamps & engraving) as well as vibrant multi-stop gradients.
2. **Modular Badges & Framing Devices**:
   - Ticket stamps, VIP ribbons, corner notches, technical framing lines.
3. **Seamless Repeating Patterns**:
   - Wallpaper patterns for merch packaging, lanyard straps, web backgrounds, and photobooths.
4. **Distortion & Kinetic Variants**:
   - Motion-ready vector frames for GSAP animations or stage LED pulse loops.

---

## 3. SVG Specification & Code Standard
All motifs must be exported as semantic, reusable SVG definitions suitable for injection into `visual-dna.json` and direct `<use>` referencing across HTML, SVG, and Illustrator.

### Example Reusable SVG Library Structure:
```xml
<svg xmlns="http://www.w3.org/2000/svg" style="display: none;">
  <defs>
    <!-- 1. Color Gradients -->
    <linearGradient id="dna-grad-primary" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#FF2E93" />
      <stop offset="50%" stop-color="#FF8A00" />
      <stop offset="100%" stop-color="#00F0FF" />
    </linearGradient>

    <!-- 2. Hero Key Motif: Geometric Sound Starburst -->
    <symbol id="key-motif-starburst" viewBox="-100 -100 200 200">
      <path d="M0 -85 L18 -25 L85 0 L18 25 L0 85 L-18 25 L-85 0 L-18 -25 Z" 
            fill="url(#dna-grad-primary)" />
      <circle cx="0" cy="0" r="14" fill="#0A0A0C" stroke="url(#dna-grad-primary)" stroke-width="4" />
      <line x1="-95" y1="0" x2="95" y2="0" stroke="#00F0FF" stroke-width="1.5" stroke-dasharray="4 4" />
      <line x1="0" y1="-95" x2="0" y2="95" stroke="#00F0FF" stroke-width="1.5" stroke-dasharray="4 4" />
    </symbol>

    <!-- 3. Seamless Brand Pattern -->
    <pattern id="brand-seamless-pattern" width="60" height="60" patternUnits="userSpaceOnUse">
      <use href="#key-motif-starburst" x="30" y="30" width="30" height="30" opacity="0.15" />
      <path d="M0 30 H60 M30 0 V60" stroke="#FFFFFF" stroke-width="0.5" opacity="0.08" />
    </pattern>

    <!-- 4. Die-cut Ticket Notch / Perforation Stamp -->
    <symbol id="motif-ticket-stamp" viewBox="0 0 120 40">
      <rect x="0" y="0" width="120" height="40" rx="6" fill="none" stroke="#FF2E93" stroke-width="1.5" />
      <circle cx="0" cy="20" r="8" fill="#0A0A0C" />
      <circle cx="120" cy="20" r="8" fill="#0A0A0C" />
      <line x1="12" y1="20" x2="108" y2="20" stroke="#FF2E93" stroke-dasharray="3 3" stroke-width="1" />
    </symbol>
  </defs>
</svg>
```

---

## 4. Cross-Asset Inheritance Rules
When executing individual campaign deliverables:
1. **Lightstick Head**: Extrude or engrave the `<symbol id="key-motif-starburst">` onto the clear acrylic surface.
2. **Concert Ticket**: Place the `<use href="#motif-ticket-stamp">` at the tear-off stub and use the seamless pattern on the reverse side.
3. **Social Media Feed & Story**: Anchor corners or focal points with the Key Motif to establish brand recall in <0.5 seconds.
4. **Festival Web Landing**: Embed the pattern inside an animated canvas background, rotating or scaling via GSAP ScrollTrigger.
5. **Stage LED**: Expand the motif into a high-res vector array pulsating to music BPM.
