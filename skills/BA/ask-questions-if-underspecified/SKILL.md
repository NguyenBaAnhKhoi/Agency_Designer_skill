---
name: ask-questions-if-underspecified
description: Guides an AI agent to pause and ask clarifying questions when a design request has ambiguous objectives, unclear target audiences, or missing brand constraints.
---

# Ask Questions If Underspecified

## Overview
When creative requests arrive with vague instructions (e.g., "design a poster for an event", "make a cool logo", "give me a hero banner"), proceeding without clarification wastes effort and leads to rework.

This skill instructs the agent to ask 1 to 4 focused, multiple-choice questions before executing design tasks.

## Clarification Checklist for Designers
1. **Target Audience & Tone**: Who is this for? What emotional response or impression should it trigger? (Minimalist, playful, corporate, luxury, cyberpunk)
2. **Brand Guidelines**: Are there existing brand colors (Hex/HSL), typography families, or logo assets to follow?
3. **Format & Dimensions**: What are the output dimensions? (e.g., 1080x1080 Instagram, 1920x1080 slide/hero, A4/A3 print at 300 DPI)
4. **Key Information & Copy**: What mandatory text, logos, or call-to-actions must be included?

## Question Guidelines
- Ask all clarifying questions in a single structured list.
- Provide recommended defaults or 2-3 common multiple-choice options.
- Once answered, proceed directly to `BA/spec-driven-development` to document the brief.
