---
name: event-merch-and-artcraft
description: "Design physical event merchandise and stage environmental collateral: VIP/GA tickets with perforation & security foils, custom lightsticks, RFID wristbands, stage LED multi-screen pixel-mapping, and entrance POSM."
last-updated: 2026-10-19
---

# 🎟️ Event Merchandise & Artcraft Production System

## 1. Core Mission & Philosophy
Live experiences and music festivals are defined by physical touchpoints. Attendees touch tickets, wave lightsticks, wear wristbands, and gaze at massive LED stages. 

Generic 2D poster skills (`canvas-design`) fail here because physical artcraft requires **orthographic construction, industrial manufacturing tolerances, die-lines, perforation geometry, and multi-display pixel mappings**.

---

## 2. Production Domain 1: Physical Ticketing Architecture

```
┌───────────────────────────────────────────────────────────────┬───────────────┐
│ MAIN TICKET BODY (140mm × 70mm)                               │ STUB (60mm)   │
├───────────────────────────────────────────────────────────────┼───────────────┤
│ [EVENT LOGO & LOCKUP]                [TIER BADGE: SVIP/VIP/GA]│ [QR / BARCODE]│
│ CONCERT / PRODUCT LAUNCH TITLE                                │ ADMIT ONE     │
│ DATE: 2026-10-25 | VENUE: SAIGON EXHIBITION CENTER            │ SEAT: A-12    │
│                                                               │ SERIAL: #0842 │
│ [HOLOGRAPHIC FOIL STAMP]             [EMBEDDED KEY MOTIF]     │               │
└───────────────────────────────────────────────────────────────┴───────────────┘
                                ▲ Perforation Line (Cấn răng cưa đứt quãng)
```

### Ticketing Technical Specs:
- **Dimensions**: Standard 200mm × 70mm or 180mm × 65mm.
- **Perforation Line (Đường cấn xé)**: Placed 50mm–60mm from the right edge. Rendered in Illustrator/SVG with `stroke-dasharray="2 3"` on a dedicated `DIE_CUT` layer.
- **Tier Color Coding (Phân cấp hạng vé)**:
  - **SVIP / VVIP**: Rich Black (`C:40 M:30 Y:30 K:100`) + Metallic Gold Foil / Hologram Stamp.
  - **VIP**: Primary Campaign Gradient / Electric Neon accent.
  - **Fanzone / GA (General Admission)**: Clean high-contrast inverted monochrome / Secondary brand color.
- **Security & Data Zones**:
  - High-density 2D QR Code (minimum 20mm × 20mm, quiet zone 4mm).
  - Variable Data Serial Number font (OCR-B or monospace DIN).
  - Anti-counterfeit micro-text & security guilloche patterns.

---

## 3. Production Domain 2: Custom Lightstick & Packaging Engineering

```
              ┌──────────────┐
              │              │  ◄── 1. GLOWING HEAD (Clear Acrylic / Injection PC)
              │  [KEY MOTIF] │      - 3D Laser-engraved Motif inside
              │   EMBEDDED   │      - Ultra-bright addressable RGB LED
              │              │      - Dimensions: 90mm × 100mm × 35mm
              └──────┬───────┘
                     │
              ┌──────┴───────┐
              │ [POWER / BT] │  ◄── 2. CONTROL RING / BUTTON
              ├──────────────┤
              │              │
              │  ERGONOMIC   │  ◄── 3. HANDLE CYLINDER (Matte ABS Plastic)
              │    HANDLE    │      - UV-printed event typography
              │  (140mm H)   │      - Silicone grip ribs
              │              │
              ├──────────────┤
              │ [BATTERY CAP]│  ◄── 4. BASE & LANYARD LOOP (AAA × 3)
              └──────────────┘
```

### Lightstick Manufacturing Specs:
- **Total Height**: 220mm – 250mm; Handle diameter: 32mm – 36mm.
- **Optical Chamber**: Frosted or laser-etched acrylic featuring the vector Key Motif from `visual-dna.json`.
- **Packaging Box**: Rigid magnetic box or window-cut paperboard (260mm × 120mm × 60mm) with custom EVA foam insert, complete with unfolding die-cut templates.

---

## 4. Production Domain 3: Stage LED Multi-Screen Pixel Mapping

Modern concerts and product launches never use a single 16:9 projector screen. The visual canvas is an orchestrated multi-display environment:

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                            STAGE TRUSS RIG                                   │
├───────────────┬──────────────────────────────────────────────┬───────────────┤
│ LEFT WING     │            CENTER ULTRA-WIDE LED             │ RIGHT WING    │
│ PORTRAIT      │               (Ratio: 32:9)                  │ PORTRAIT      │
│ (Ratio: 9:16) │          Resolution: 3840 × 1080 px          │ (Ratio: 9:16) │
│ 1080 × 1920 px│                                              │ 1080 × 1920 px│
│               ├──────────────────────────────────────────────┤               │
│ [Live Artist  │ [Key Visual Cinematic Loops & Ambient Motif] │ [Live Artist  │
│  IMAG Feed]   ├──────────────────────────────────────────────┤  IMAG Feed]   │
│               │            DJ BOOTH / STAGE FASCIA (4:1)     │               │
│               │             Resolution: 1920 × 480 px        │               │
└───────────────┴──────────────────────────────────────────────┴───────────────┘
```

### Stage Visual Guidelines:
1. **Resolution & Synchronized Canvas**:
   - Master Stage Canvas: 7680 × 2160 or 3840 × 1080 (32:9).
   - Side IMAG Wings: 1080 × 1920 (9:16) with 15% safe area buffer from speaker arrays.
   - DJ Booth / Riser LED: 1920 × 480 (4:1) for looping kinetic typography and brand motifs.
2. **Visual Hierarchy & Pacing**:
   - High-energy moments: Synchronized pulse of Key Motif across all screens.
   - Keynote / Reveal moments: Wings fade to subtle dark ambiance, Center screen spotlights product / artist.

---

## 5. Production Domain 4: Event Wearables & Entrance POSM
- **Fabric Wristbands**: 350mm × 15mm woven polyester with smart slider lock and 40mm × 25mm PVC RFID tag.
- **Accreditation Lanyard**: 900mm × 20mm heat-transfer printed strap with die-cut acrylic badge (100mm × 150mm).
- **Entrance Step-and-Repeat Backdrop**: 4000mm × 3000mm matte canvas banner; alternating logo pattern spaced 250mm apart to fit shoulder height in guest photography.
