# AGENTS.md — AI AGENT INSTRUCTIONS FOR NIDHI TEA

This file provides system instructions and architecture constraints for any AI coding assistant (Antigravity, Cursor, Windsurf, Copilot, Claude, etc.) operating on this repository.

> **Full Documentation**: See [GEMINI.md](file:///c:/Users/USER/Downloads/Nidhi%20Tea/Nidhi%20Tea/GEMINI.md) for the complete design system and animation catalog.

---

## Quick Reference Summary

* **Project**: Nidhi Tea — Single-Page Handcrafted Tea Web Experience.
* **Main File**: [index.html](file:///c:/Users/USER/Downloads/Nidhi%20Tea/Nidhi%20Tea/index.html) (Markup + Tailwind config + Custom CSS + GSAP JS in one file).
* **Styling**: Tailwind CDN + Custom CSS custom properties (`--background`, `--cream`, `--gold`, `--flame`, `--cherry`).
* **Motion Engine**: GSAP 3.12.5 + ScrollTrigger CDN.

---

## WHAT IS CHANGED (Current State)

1. **Brand Conversion**: Entire template has been completely transformed into **Nidhi Tea** (mountain handcrafted artisan teas).
2. **Assets**: All old hot sauce assets have been replaced with ultra-clean transparent tea elements in `element-img/` (teapots, loose leaves, spices, strainers, honey dippers) and products in `img/`.
3. **Hero Carousel**: Multi-blend carousel (`Classic Masala Chai`, `Honey Lemon Green Tea`, `Rose Cardamom Black Tea`) with dynamic companion botanical shrink-and-bloom transitions.
4. **Cinematic 4K Video**: Added `#cinemaSection` with GSAP scroll expansion, custom video control bar, autoplay on viewport enter, mute/unmute, and fullscreen.
5. **Why Section**: Split into arched SVG headline (`#whyIntroSection`) + 300vh pinned horizontal scroll scrubbing (`#whySection`).
6. **Preloader**: 4-quadrant clip-path circle reveals with floating ingredients, exit explosion, and elastic heading character pop.

---

## WHAT YOU CAN CHANGE (Safe Zones)

- **Copy & Typography**: Headlines, product descriptions, pricing (`₹299`), quotes in `REVIEWS` array.
- **Product Data**: Add or modify objects in the `PRODUCTS` and `SLIDES` arrays in JavaScript.
- **Visual Media**: Swap images in `img/` or `element-img/` with transparent PNG/WebP files of equivalent dimensions.
- **Links**: Navigation anchors, social media links in footer, newsletter submit handling.

---

## WHAT YOU MUST NOT CHANGE (Danger Zones - DO NOT TOUCH)

1. **NO Selector Renaming**: Do NOT rename or remove any element IDs or classes referenced by JavaScript (`#loader`, `#heroTitle`, `.char`, `#heroTintWrap`, `#whySection`, `#whyStickyContainer`, `.slide`, `.why-line`, `#cinemaVideo`, `#cinemaArena`, etc.).
2. **NO Library Removal**: Do NOT remove GSAP, ScrollTrigger, or Tailwind CDN scripts. Do NOT delete the `SplitTextPlugin` fallback class.
3. **NO Math / Scroll Layout Alteration**:
   - `#whySection` MUST remain `h-[300vh]`.
   - `#whyStickyContainer` MUST remain `sticky top-0 h-screen overflow-hidden`.
4. **NO Disabling Video Attributes**: `#cinemaVideo` MUST keep `playsinline`, `loop`, and `muted` for browser autoplay compliance.
5. **NO Removing Transforms / Hardware Acceleration**: Retain all `will-change-transform` and inline transform styles.

---
*Refer to [GEMINI.md](file:///c:/Users/USER/Downloads/Nidhi%20Tea/Nidhi%20Tea/GEMINI.md) for detailed property tables and keyframes.*
