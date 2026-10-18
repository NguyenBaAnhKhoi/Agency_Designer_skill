---
name: ai-image-gen
description: Professional prompt engineering for Midjourney v6, Flux.1, SDXL, and DALL-E 3 for graphic designers. Generates brand imagery, poster art, marketing visuals, and mockups with precise camera, lighting, and composition formulas.
---

# AI Image Generation for Graphic Designers

## Overview
This skill provides production-grade prompt templates and parameter standards for generating commercial-quality visuals using modern AI image models (Midjourney, Flux.1, SDXL, DALL-E 3).

## Prompt Formula
Every image generation prompt must follow this exact 5-part architecture:
`[Subject & Action] + [Art Style / Medium] + [Lighting & Atmosphere] + [Camera / Lens / Composition] + [Render Engine & Technical Flags]`

### 1. Subject & Action
- Clear noun with emotional or physical action. Avoid vague words like "beautiful", "amazing".
- Example: *"A sleek matte-black ceramic perfume bottle on a fractured volcanic basalt pedestal, light water mist dispersing in air"*

### 2. Art Style & Medium
- Commercial photography, editorial fashion shoot, 3D claymation, Bauhaus risograph print, Swiss modernism poster, or brutalist architecture.

### 3. Lighting & Atmosphere
- Studio rim lighting, volumetric god rays, high-key diffuse daylight, bioluminescent rim glows, cinematic warm golden hour 3200K, chiaroscuro contrast.

### 4. Composition & Framing
- 85mm portrait lens, f/1.8 shallow depth of field, macro close-up, rule of thirds, Dutch angle, top-down flat lay, centered isometric view.

### 5. Technical Parameters by Model
- **Midjourney v6.1**: `--ar 16:9` (or `4:5`, `1:1`), `--v 6.1`, `--style raw`, `--stylize 250`, `--chaos 10`
- **Flux.1 Schnell/Dev**: Steps: 28-35, Guidance scale: 3.5, Aspect ratio: 1024x1024 or 1280x768
- **SDXL**: `(masterpiece:1.2), (photorealistic:1.3), 8k resolution, raw photo`
- **Negative Prompts**: `blurry, low quality, distorted text, extra limbs, watermark, oversaturated, deformed proportions, plastic skin, out of frame`

## Designer Workflow
1. **Analyze Concept**: Extract subject, mood, and brand color palette.
2. **Draft 3 Variants**:
   - Variant A: Clean Editorial Studio Photography
   - Variant B: Dynamic 3D / Abstract Concept
   - Variant C: Minimalist Graphic / Vector-inspired Artwork
3. **Upscale & Post-process**: Pass into `venice-image-edit` or Photoshop for background removal and typography layout.
