---
name: creative-agency
description: "Design graphic identities and visual systems for events and campaigns: art direction, expressive typography, Key Visual (KV) & poster series, social, environmental graphics, stage LED, 3D spatial, and motion. Use for complete visual campaigns, event design, and creative revisions."
---

# Creative Agency — Event & Campaign Visual Design System

## 1. Core Mission
Specializes in **graphic design for real-world events, live experiences, and comprehensive brand campaigns**. Responsible for developing a cohesive, distinct, and production-ready visual world.
- Communication strategy serves as a supporting input; do not replace visual craft with lengthy insight decks or abstract marketing funnels.
- Every project is an ongoing cycle of **research, ideation, visual foundation, proofing, production, and refinement**. A single poster is merely a test sample of the system, not the end of a campaign scope.
- **Event-First Scope**: Begin from the live event experience and user journey, not an arbitrary list of file counts. Use the 4-dimensional matrix: **Time × Space × Persona × Show Content**.

---

## 2. Professional Workflow

### Phase 1: Context Research & Creative Material Gathering
- Analyze the brand, event nature, scale, attendee personas, venue architecture, and production constraints before finalizing deliverables.
- Map out touchpoints across campaign phases:
  - **Teaser Phase**: Mysterious mood, visual motifs, save-the-date.
  - **Announcement / Hype Phase**: Key Visual (KV), lineup, ticket tiers, sponsor lockups.
  - **Showday / Live Phase**: Stage LED loops, wayfinding signage, accreditation lanyards, wristbands, photo booths, merchandise.
  - **Recap Phase**: Highlights, thank-you assets, community recap frames.
- Draw creative references from history, music, culture, architecture, and tactile materials.

### Phase 2: Distinct Concept Exploration
- Connect research insights to visual form: moodboards, custom typography sketches, collage, material tests, and lighting explorations.
- Contrast headline-to-image relationships and rhythmic pacing. Changing a single hex color or adding a drop shadow does not constitute a new concept.

### Phase 3: Visual Foundations
Establish the core visual system in `assets/visual-foundations.md`:
- **Art Direction & Philosophy**: Core concept statement and aesthetic rules.
- **Logo Lockup & Identity**: Proportions, clear space, co-branding guidelines.
- **Color Architecture**: Dominant (60%), Secondary (30%), Accent (10%), and dark/light mode tokens.
- **Typography Matrix**: Display/Hero typeface, Subheadings, Body copy, and **Vietnamese diacritics handling**.
- **Graphic Assets**: Custom motifs, 3D primitives, textures, grid patterns.

### Phase 4: System Proofing & Stress-Testing
- Create a master visual and test it across extreme aspect ratios:
  - Ultra-tall vertical (9:16 Instagram Story, 80x200cm Roll-up banner).
  - Ultra-wide horizontal (32:9 Curved Stage LED, 1200x628 Facebook link preview).
  - Micro-scale (favicon, 48px app icon, wristband print).
- Document results in `assets/visual-proof-record.md`. If the visual collapses at extreme ratios, adjust the foundation before rollout.

### Phase 5: Production & Deliverable Rollout
- Populate `assets/deliverables.csv` with exact dimensions, color modes (CMYK / RGB), resolution (300 DPI print / 72 DPI screen), bleeding margins, and target deadlines.
- Differentiate between **Original Artwork**, **Content Variations**, **Format Adaptations**, and **3D/Mockup Proofs**.

### Phase 6: Optical Polish & Technical Quality Gate
- Optical kerning, baseline alignment, contrast ratio validation (WCAG AA >= 4.5:1).
- Separation of concerns between raster layers, vectors, and live editable text.

---

## 3. Specialized Technical Domains

### 3.1 Key Visual (KV) & Poster Design Hierarchy
Design for viewing distance zones:
1. **Distance Zone (30m - 50m)**: Instant recognition via dominant color contrast, silhouette, and bold graphic mass.
2. **Mid Zone (5m - 10m)**: Legibility of primary headline, event name, and date.
3. **Close Zone (1m - 2m)**: Secondary details, artist lineup, sponsor credits, QR codes, ticket information.

### 3.2 Stage LED & 3D Spatial Graphics
- **Technical Packet LED**: Strict adherence to physical LED cabinet geometry and pixel mapping (`assets/led-technical-sheet.md`).
- **Safe Margins**: Minimum 10% safe title buffer on all sides to prevent edge clipping behind stage trussing or speaker arrays.
- **Color Spaces & Output**: Rec.709 / DCI-P3. Delivery codecs: Apple ProRes 422 / 4444 (master), H.264 / H.265 (playback servers like Resolume, Disguise, Watchout).
- **Motion Rhythm**: Ambient stage loops must not strobe or induce audience fatigue; sync energy levels to show cues.

### 3.3 Vietnamese & Bilingual Typography Standards
- Always preserve full Vietnamese tone marks and diacritics accurately.
- Avoid font substitution errors where accented vowels fall back to generic system fonts.
- Manually adjust kerning and vertical leading (`line-height`) when combining uppercase diacritics with international headlines.

### 3.4 Marketing Collateral & POSM Design Standards
- **Standee / Roll-up Banner (80 × 200cm & 60 × 160cm) — The Eye-Level Rule:**
  - **Top Zone (180cm - 200cm):** Primary Brand Logo and Event/Campaign Identity.
  - **Golden Focal Zone (140cm - 170cm):** Standing adult eye-level. Place Key Visual focal point + Main Headline + Core Value Proposition.
  - **Action Zone (100cm - 140cm):** Date, venue, QR code, website, registration link.
  - **Dead Zone (Floor to 80cm):** Strictly background textures, subtle ambient graphics, or brand pattern. **NEVER** place key text or contact details below 80cm (occluded by foot traffic and impossible to read standing up).
- **Brochure & Leaflet (Tri-fold A4 / Bi-fold A4 / Flyer A5):**
  - **Tri-fold 6-Panel Reading Flow:**
    - *Outside Spread:* Panel 5 (Inside Flap) ➔ Panel 6 (Back Cover / Contact) ➔ Panel 1 (Front Cover / Hook).
    - *Inside Spread:* Panels 2, 3, 4 (Full narrative flow across 3 cohesive columns).
- **Event POSM (Backdrop, Wobbler, Tent Card, Badge):**
  - *Photo Backdrop (300 × 250cm / 400 × 300cm):* Repeating logo grid (step-and-repeat) scaled to 15-20cm per logo so logos appear clearly behind attendees in camera shots.
  - *Lanyard & Badge (10 × 15cm):* Category pill (VIP, Speaker, Staff, Press) in high-contrast color code, Attendee Name in bold ≥28pt.

### 3.5 Prepress & Print Production Quality Assurance
- **Color Profiles:** CMYK FOGRA39 (Europe/Asia standard) or US Web Coated SWOP v2. Never deliver RGB files to commercial offset/digital printers.
- **Resolution & Bleed:** Strict 300 DPI at 100% scale. Outer Bleed margin: 3mm (Europe/Asia) or 5mm (large format / POSM). Safe margin: minimum 5mm inside cut line.
- **Black Color Calibration:**
  - *Rich Black (`C:40 M:30 Y:30 K:100`):* For large background areas and bold display headlines (creates deep, luscious black without ink pooling).
  - *Pure Black (`C:0 M:0 Y:0 K:100`):* Strictly for small body text (<14pt) to prevent optical registration misalignments.

### 3.6 Design System Retrieval via `ui-ux-pro-max`
When defining visual foundations and collateral styling, query the built-in design database:
```bash
python3 .agent/skills/Designer/ui-ux-pro-max/scripts/search.py "<event_type> visual" --domain style
python3 .agent/skills/Designer/ui-ux-pro-max/scripts/search.py "<brand_industry> palette" --domain color
python3 .agent/skills/Designer/ui-ux-pro-max/scripts/search.py "<brand_personality> font" --domain typography
```

---

## 4. Operational Asset Templates
- **Creative Brief**: [`assets/creative-brief.md`](assets/creative-brief.md)
- **Scope & Matrix**: [`assets/design-scope.md`](assets/design-scope.md)
- **Visual Foundations**: [`assets/visual-foundations.md`](assets/visual-foundations.md)
- **Proof & QA Record**: [`assets/visual-proof-record.md`](assets/visual-proof-record.md)
- **Deliverables Sheet**: [`assets/deliverables.csv`](assets/deliverables.csv)
- **LED Technical Sheet**: [`assets/led-technical-sheet.md`](assets/led-technical-sheet.md)
- **Show Cue Sheet**: [`assets/shot-cue-sheet.csv`](assets/shot-cue-sheet.csv)
- **Post-Project Case Study**: [`assets/case-study.md`](assets/case-study.md)

