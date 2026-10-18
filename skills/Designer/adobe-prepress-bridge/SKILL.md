---
name: adobe-prepress-bridge
description: "Generate Adobe Illustrator and InDesign ExtendScript (.jsx) automation scripts, structured SVG files with standardized Illustrator layer hierarchies, CMYK prepress calibration, spot color die-lines, and industrial print specifications."
last-updated: 2026-10-19
---

# 🖨️ Adobe ExtendScript & Prepress Production Bridge

## 1. Core Mission & Philosophy
Professional graphic design agencies do not deliver flattened JPEGs to industrial print houses. Production requires native **Adobe Illustrator (`.ai`)**, **InDesign (`.indd`)**, and **ExtendScript (`.jsx`)** files containing exact layer separations, Pantone spot colors, die-cut vectors, and prepress bleeding.

### Root Problem Solved:
AI agents typically produce unlayered SVGs or web-only RGB designs. This skill acts as an automated prepress technician, writing **Adobe ExtendScript (`.jsx`)** scripts that can be run directly inside Adobe Illustrator (`File > Scripts > Other Script...`) to build production artboards with exact layers, die-lines, and CMYK swatches.

---

## 2. Standardized Adobe Illustrator Layer Architecture

Every print asset created by this skill MUST conform to this strict top-to-bottom layer stack:

```
┌────────────────────────────────────────────────────────────────────────┐
│ LAYER ORDER │ LAYER NAME           │ CONTENT & ATTRIBUTES              │
├─────────────┼──────────────────────┼───────────────────────────────────┤
│ Layer 7     │ DIE_CUT              │ Cut & Crease lines (Spot Magenta) │
│ Layer 6     │ FOIL_STAMP           │ Hot stamping & Holographic areas  │
│ Layer 5     │ SPOT_UV              │ Spot gloss varnish masks          │
│ Layer 4     │ TYPOGRAPHY_LIVE      │ Live editable fonts & legal copy  │
│ Layer 3     │ ARTWORK_VECTOR       │ Key motifs, logos, vector icons   │
│ Layer 2     │ BACKGROUND           │ Solid fills, gradients, textures  │
│ Layer 1     │ BLEED_GUIDE          │ 3mm-5mm bleed boundaries & marks  │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 3. Industrial Prepress Color Calibration
- **CMYK Profile**: ISO Coated v2 (ECI) / FOGRA39 for Europe/Asia; GRACoL 2006 for Americas.
- **Spot Colors & Special Inks**:
  - `DieCut`: 100% Magenta (`C:0 M:100 Y:0 K:0`), Non-printing attribute, 0.5pt stroke.
  - `CreaseLine`: 100% Cyan (`C:100 M:0 Y:0 K:0`), dashed 2pt/2pt stroke.
  - `FoilGold`: Pantone 871 C or Spot Gold representation.
  - `FoilHologram`: Custom Spot channel named `Hologram_Silver`.
- **Black Inks**:
  - **Rich Black** (`C:40 M:30 Y:30 K:100`): Mandatory for large solid backgrounds and headlines ≥36pt.
  - **Pure Black** (`C:0 M:0 Y:0 K:100`): Strictly enforced for body text <14pt with **Overprint Black** enabled.

---

## 4. Production ExtendScript (.jsx) Generator for Illustrator

When requested to create print-ready tickets, standees, or packaging, generate an executable `.jsx` script that can be executed in Adobe Illustrator:

### Example ExtendScript: Automated Event Ticket Generator (`generate_ticket.jsx`):
```javascript
// Adobe Illustrator ExtendScript: Event Ticket with Die-Cut & Layers
#target illustrator

function createEventTicket() {
    // 1. Document Setup (200mm x 70mm + 3mm Bleed)
    var docWidth = 200 * 2.834645; // mm to points
    var docHeight = 70 * 2.834645;
    var bleed = 3 * 2.834645;

    var docPreset = new DocumentPreset();
    docPreset.width = docWidth;
    docPreset.height = docHeight;
    docPreset.colorMode = DocumentColorMode.CMYK;
    docPreset.units = RulerUnits.Millimeters;

    var doc = app.documents.addDocument(DocumentPresetType.Print, docPreset);

    // 2. Setup Swatches: Rich Black & Die-Cut Spot Magenta
    var richBlack = new CMYKColor();
    richBlack.cyan = 40; richBlack.magenta = 30; richBlack.yellow = 30; richBlack.black = 100;

    var spotMagenta = new CMYKColor();
    spotMagenta.cyan = 0; spotMagenta.magenta = 100; spotMagenta.yellow = 0; spotMagenta.black = 0;

    var spotColor = doc.spots.add();
    spotColor.name = "DIE_CUT_CONTOUR";
    spotColor.color = spotMagenta;
    spotColor.colorType = ColorModel.SPOT;

    // 3. Create Layer Hierarchy
    var layerDieCut = doc.layers.add(); layerDieCut.name = "DIE_CUT";
    var layerFoil = doc.layers.add(); layerFoil.name = "FOIL_STAMP";
    var layerType = doc.layers.add(); layerType.name = "TYPOGRAPHY_LIVE";
    var layerArt = doc.layers.add(); layerArt.name = "ARTWORK_VECTOR";
    var layerBg = doc.layers.add(); layerBg.name = "BACKGROUND";

    // 4. Draw Background with Bleed on layerBg
    var bgRect = layerBg.pathItems.rectangle(docHeight + bleed, -bleed, docWidth + (bleed * 2), docHeight + (bleed * 2));
    bgRect.fillColor = richBlack;
    bgRect.stroked = false;

    // 5. Draw Perforation Line on layerDieCut (at X = 140mm)
    var perfX = 140 * 2.834645;
    var perfLine = layerDieCut.pathItems.add();
    perfLine.setEntirePath([[perfX, 0], [perfX, docHeight]]);
    var perfStroke = new SpotColor();
    perfStroke.spot = spotColor;
    perfLine.strokeColor = perfStroke;
    perfLine.strokeWidth = 1;
    perfLine.strokeDashes = [4, 4]; // Dashed perforation
    perfLine.filled = false;

    // 6. Draw Outer Die-Cut Boundary on layerDieCut
    var dieBorder = layerDieCut.pathItems.rectangle(docHeight, 0, docWidth, docHeight);
    dieBorder.strokeColor = perfStroke;
    dieBorder.strokeWidth = 1;
    dieBorder.filled = false;

    alert("✅ Production Ticket Artboard & Prepress Layers generated successfully!");
}

createEventTicket();
```

---

## 5. Prepress Quality Checklist Before Sign-off
1. [ ] All images linked or embedded at **≥300 DPI**.
2. [ ] Outer Bleed of **3mm** (small print) or **5mm** (large POSM) present on all four sides.
3. [ ] No critical text within **5mm** of trim line (Safe Zone buffer).
4. [ ] All text converted to outlines (`Type > Create Outlines`) for external plate makers, while preserving a master file with live typography.
5. [ ] Spot channels configured to `Overprint` where applicable to avoid optical trapping halos.
