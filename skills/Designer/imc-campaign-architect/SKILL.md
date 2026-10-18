---
name: imc-campaign-architect
description: "Master architecture and Deliverable Bill of Materials (BOM) for 360 IMC Campaigns, Product Launches, and Music Festivals. Decomposes large campaigns across 3 phases (Tease, Launch, Sustain) and coordinates multi-pack creative execution."
last-updated: 2026-10-19
---

# 🏛️ IMC Campaign Architect — 360 Campaign Architecture & Deliverable BOM

## 1. Core Mission & Philosophy
The **IMC Campaign Architect** acts as the Executive Creative Director and Campaign Producer for high-stakes brand activations, music festivals, and product launches.

### Root Problem Solved:
When asked to create a full campaign, AI agents default to a "Lazy Overview" (generating 1 surface-level summary file) or omit crucial physical and digital collateral. This skill enforces:
1. **Mandatory Campaign Deliverable Matrix (Bill of Materials - BOM)**: Pre-populating all required collateral before any asset is generated.
2. **3-Phase Lifecycle Mapping**: Structuring assets chronologically across **Phase 1: Tease/Pre-Hype**, **Phase 2: Launch/Reveal**, and **Phase 3: D-Day & Sustain**.
3. **Multi-Pack Decomposition**: Splitting execution into 5 autonomous production packs to eliminate token bottlenecks and prevent visual degradation.

---

## 2. The 3-Phase Lifecycle Campaign Matrix

```
┌────────────────────────────────────────────────────────────────────────┐
│                        360° CAMPAIGN TIMELINE                          │
├─────────────────────┬───────────────────────┬──────────────────────────┤
│ PHASE 1: TEASING    │ PHASE 2: LAUNCH/REVEAL│ PHASE 3: D-DAY & SUSTAIN │
│ (D-30 to D-14)      │ (D-14 to D-Day)       │ (Showday & D+7)          │
├─────────────────────┼───────────────────────┼──────────────────────────┤
│ • Mysterious Teaser │ • Master Key Visual   │ • Stage LED Visuals      │
│ • Save-The-Date     │ • Full Lineup Reveal  │ • Physical Tickets/Merch │
│ • Motif Snippets    │ • Early-Bird Tickets  │ • Wayfinding & POSM      │
│ • Social Countdown  │ • Experiential Web    │ • Live Show Coverage     │
│ • Mascot Silhouette │ • Mascot Full Reveal  │ • Recap / Aftermovie     │
└─────────────────────┴───────────────────────┴──────────────────────────┘
```

---

## 3. Campaign Bill of Materials (BOM) Template
When any campaign or launch prompt is received, the agent MUST immediately output or initialize the following Deliverable Matrix:

### Pack 01: Brand Core, Identity & Visual DNA
- [ ] **Event Logo & Lockup**: Vector SVG master logo + horizontal / vertical / monochrome variants.
- [ ] **Brand Motif Engine (`brand-motif-engine`)**: Seamless vector pattern system, geometric badges, `<defs>` symbols.
- [ ] **Visual DNA Lock (`visual-dna.json`)**: Exact hex/Pantone colors, typography pairing, mascot seed tokens.
- [ ] **Mascot / IP Character (`mascot-sheet`)**: Turnaround sheet, 6 expressions, action poses holding product/props.

### Pack 02: Digital, Social & Media Lifecycle
- [ ] **Phase 1 (Teasing)**:
  - 1080x1350 (4:5) Cryptic Teaser Poster.
  - 1080x1920 (9:16) Save-The-Date Story with countdown sticker safe zone.
  - Social Avatar Frame & Profile Header (1920x1080).
- [ ] **Phase 2 (Announcement & Ticket Drop)**:
  - Master Key Visual (KV) in 4:5 (IG Feed), 9:16 (Story/TikTok), and 16:9 (Landscape Web/Billboard).
  - Tiered Ticket Announcement (Early Bird, VIP, GA).
  - Artist / Product Lineup Bento Carousel (10-slide high retention).
- [ ] **Phase 3 (D-Day & Recap)**:
  - Daily Countdown Series (D-3, D-2, D-1, Today).
  - Venue Map, Schedule & Guidelines Carousel.
  - Thank You & Recap Template (highlighting attendance, memorable moments).

### Pack 03: Event Merchandise & Physical Artcraft (`event-merch-and-artcraft`)
- [ ] **Physical Ticketing System**: VIP / SVIP / GA tickets with perforation lines, holographic foil, and QR codes.
- [ ] **Interactive Lightstick**: Ergonomic handle, custom acrylic head embedding the Key Motif, packaging box.
- [ ] **Wristbands & Access Lanyards**: Tyvek/Fabric wristband with RFID chip, PVC badge with color-coded tier pills.
- [ ] **Event Merchandise**: T-Shirt graphic placement, tote bag, enamel pins.

### Pack 04: Experiential Stage & Spatial Environment
- [ ] **Stage LED Pixel Map**: Ultra-wide Center LED (32:9), Left/Right Stage Wings (9:16), DJ Booth Fascia (4:1).
- [ ] **Entrance & Venue POSM**: Welcome arch (Cổng chào), Standee Roll-up (80x200cm), Step-and-Repeat Photo Backdrop (400x300cm).
- [ ] **Wayfinding Signage**: Zone directions, F&B booth branding, safety instructions.

### Pack 05: Creative Experiential Web (`experiential-festival-web`)
- [ ] **100vh Immersive Hero**: Display kinetic typography, ambient motif canvas, live ticket drop countdown.
- [ ] **Interactive Lineup Showcase**: Bento grid with SVG displacement hover effects.
- [ ] **3D Ticket Tier Selector**: Realistic ticket cards with tear-off animations and currency calculation.
- [ ] **Merch & Venue Map Section**: Interactive SVG map of stages and merch booths.

---

## 4. Execution Protocol: Anti-Overview & Pack-by-Pack
1. **Never generate the entire campaign in one prompt**:
   - Step 1: Lock the `visual-dna.json` and generate the Campaign BOM table.
   - Step 2: Inquire with the client which Pack to execute first, or execute sequentially (Pack 01 -> Pack 02 -> Pack 03 -> Pack 04 -> Pack 05).
2. **Every Asset Must be Production-Ready**:
   - Provide exact pixel dimensions or millimeter specs.
   - Separate layers for print (Die-line, Bleed, Foil, Artwork).
   - Reference `visual-dna.json` so every pack is 100% aesthetically unified.
