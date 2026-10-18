---
name: social-media-content
description: Design high-converting 2D social media graphic assets, Instagram carousels, Facebook feed posts, Story/Reels covers with UI safe zones, and ad banners. Includes social copywriting and optional multi-platform scheduling via Typefully.
last-updated: 2026-10-18
---

# Social Media 2D Visual Design & Creative Content System

## 1. Overview & Core Philosophy
This skill provides an agency-standard visual production system for **Social Media 2D Graphics, Advertising Creatives, and Carousel Series**.

In modern social media marketing, **visual design drives the stop-rate (hook rate)** while **structured copy drives the conversion**. This skill enforces strict dimensional standards, mobile safe zones, seamless carousel continuity, and typographic hierarchy.

---

## 2. Master Format & Aspect Ratio Matrix

| Asset Type | Pixel Dimensions | Aspect Ratio | Safe Zones / Margins | Optimal Platform | Primary Objective |
|:---|:---:|:---:|:---|:---|:---|
| **Feed Portrait (Golden Ratio)** | **1080 × 1350 px** | **4:5** | Inset 60px all sides | Instagram / Facebook Feed | **Maximum screen real estate (+25% vs 1:1), highest thumb-stop rate** |
| **Feed Square** | **1080 × 1080 px** | **1:1** | Inset 48px all sides | LinkedIn, Twitter/X, IG Grid | Versatile multi-platform standard |
| **Story / Reels / TikTok Cover** | **1080 × 1920 px** | **9:16** | **Top 150px & Bottom 250px NO TEXT** | Instagram Stories, Reels, TikTok | Fullscreen immersive experience |
| **Landscape Banner / Link Ad** | **1200 × 628 px** | **1.91:1** | Inset 40px all sides | Facebook Link Ads, LinkedIn, Twitter | Click-through to external web link |
| **Profile / Event Header** | **1920 × 1080 px** | **16:9** | Center 1200x600px focal | YouTube, Facebook Event, Webinar | Brand recognition & event announcement |

---

## 3. UI Safe Zone Rules for 9:16 (Story / Reels / TikTok)
AI agents frequently fail by placing critical text under native platform UI buttons. Follow this exact spatial geometry:

```
┌────────────────────────────────────────────────────────┐ 0px
│ [DANGER ZONE: Top 150px - Header / Avatar / Close UI]   │
├────────────────────────────────────────────────────────┤ 150px
│                                                        │
│                  SAFE VISUAL AREA                      │
│             (1080 × 1520px Active Canvas)              │
│                                                        │
│  - Main Headline (Y: 250px - 500px)                    │
│  - Hero Visual / 3D Asset / Photo Focal (Center)        │
│  - Callout Badges / Key Value Propositions             │
│  - Primary CTA Button / Swipe Up Indicator             │
│                                                        │
├────────────────────────────────────────────────────────┤ 1670px
│ [DANGER ZONE: Bottom 250px - Caption / Comment / Like] │
└────────────────────────────────────────────────────────┘ 1920px
```

---

## 4. The 10-Slide High-Retention Carousel Blueprint
Multi-slide carousels generate 3x higher engagement than static posts when designed with **Panoramic Seamless Flow**:

```
Slide 1 ──▶ Slide 2..8 ──▶ Slide 9 ──▶ Slide 10
(Hook)      (Value Flow)   (Summary)   (Hard CTA)
```

1. **Slide 1 (The 3-Second Hook):**
   - Headline: Massive, bold font (≥72pt), high-contrast background.
   - Subtitle: 1 punchy sentence setting expectations ("Dưới đây là 5 bước...").
   - Badge Pill: "Swipe ➔" or "Vuốt để xem bí quyết".
   - Hero Element: A 3D asset or visual motif clipped at the right edge to visually pull the user to slide 2.
2. **Slides 2 to 8 (The Value Body):**
   - **One single idea per slide**: Never crowd multiple complex concepts into one card.
   - **Seamless Panoramic Element**: An accent curve, gradient ribbon, or product graphic that spans across the right edge of Slide N and continues on the left edge of Slide N+1.
   - Card container: Floating translucent card (`rgba(255,255,255,0.08)` or clean solid container with 24px rounded corners).
   - Micro-indicator: Top-right slide counter (`02 / 10`).
3. **Slide 9 (The Cheat-Sheet Summary):**
   - 3 to 4 bullet points summarizing the key takeaways for quick screenshotting.
4. **Slide 10 (Action & Conversion):**
   - Distinct Action Card: Prominent Save & Share icons.
   - Clear CTA: "Lưu bài viết này để áp dụng ngay" / "Comment [KEYWORD] để nhận tài liệu".
   - Brand profile avatar + Handle lockup (`@agency_design`).

---

## 5. Graphic Design Principles (PPTX & Agency Rules)

1. **Color Architecture (60-30-10 Rule):**
   - 60% Canvas base (Clean dark mode `#0B0F19` or editorial white `#FAFAFA`).
   - 30% Structural cards, badges, and secondary typography.
   - 10% High-intensity accent (`#FF5722`, `#00E5FF`, `#FFE600`) reserved exclusively for the Hook keywords and CTA button.
2. **Typography Hierarchy:**
   - **Hook Headline:** Display Sans / Punchy Serif, 72–96pt, line-height 1.15x, tracking -0.02em.
   - **Card Title / Subhead:** SemiBold Sans, 32–40pt.
   - **Body Copy:** Neutral Sans (Inter, Be Vietnam Pro, Montserrat), 18–22pt, line-height 1.4x.
   - **Caption / Metadata:** 12–14pt muted (`#64748B`).
3. **Anti-Patterns (Prohibited):**
   - **NO decorative underline bars beneath titles.**
   - **NO single-side accent borders or arbitrary color stripes.**
   - **NO centered body paragraphs.** Always left-align copy for maximum readability on mobile screens.
   - **NO text touching canvas margins.** Maintain minimum 60px internal padding.

---

## 6. Deterministic Output Blueprint (GPT-6.1 Sol Execution Schema)

When designing a social media graphic or carousel, the Agent **MUST** emit the following structured blueprint before creating any visual artifacts:

```markdown
### 📱 SOCIAL GRAPHIC DESIGN SPECIFICATION

**Campaign Name:** [Campaign / Post Name]  
**Asset Format:** [Feed Portrait 4:5 (1080x1350) / Story 9:16 (1080x1920) / Carousel]  
**Slide Count:** [1 or N slides]  

#### 🎨 Color System & Tokens
- **Background (60%):** `#HEX`
- **Surface / Cards (30%):** `#HEX`
- **Accent Hook (10%):** `#HEX`

#### 📝 Copy & Visual Assets Mapping
| Slide # | Slide Type | Hook / Title Copy | Body / Detail Points | Visual Asset / Seamless Graphic | CTA / Badge |
|:---:|:---|:---|:---|:---|:---:|
| 1 | Cover / Hook | [GIẬT TITLE CHÍNH] | [Subtitle 1 câu ngắn] | [3D Asset cắt nửa mép phải] | "Vuốt sang ➔" |
| 2 | Value Step 1 | [Tên Bước 1] | [2 câu giải thích xúc tích] | [Nối liền graphic từ Slide 1] | Step 01/05 |
| ... | ... | ... | ... | ... | ... |
| 10 | Action / CTA | [BẠN THẤY THẾ NÀO?] | [Tóm tắt 1 câu] | [Icon Lưu & Chia sẻ] | "Lưu bài viết" |

#### 🖼️ AI Background Generation Prompt (Clean Base)
`[Visual Theme/3D Asset] + [Studio Lighting / Dark Mode Background] + [Generous Negative Space in Upper-Half for Typography Overlay] + [--ar 4:5 or 9:16] + [--no text, letters, watermarks]`
```

---

## 7. Delivery & Multi-Platform Scheduling (Optional Tool Integration)

Once graphics and social copy are finalized, they can be scheduled directly to X, LinkedIn, Threads, and Bluesky via the integrated Typefully runner:

```bash
# Relative path to script:
./scripts/typefully.js drafts:create --platform linkedin,x --text "Post copy here..." --media "./path/to/slide-1.png"
```

For advanced publishing options (threads, comments, social accounts), refer to `references/setup.md` and `references/platforms/`.
