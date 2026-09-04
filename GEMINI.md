# NIDHI TEA — AI CONTEXT & DESIGN/ANIMATION GUIDELINES
> **Permanent Reference File (`GEMINI.md`) for AI Assistants & Developers**
> **Current Version**: 1.0 (Finalized Design & Animation System)
> **Brand**: Nidhi Tea — Premium Handcrafted Teas ("Sip Wellness, Taste Purity")

---

## 1. Project Overview & Architecture

Nidhi Tea is an ultra-premium, high-performance single-page e-commerce landing experience for an artisanal organic Indian tea brand. The frontend is engineered as a standalone, zero-build static web application contained inside [index.html](file:///c:/Users/USER/Downloads/Nidhi%20Tea/Nidhi%20Tea/index.html).

### Tech Stack & Libraries
* **Markup**: Semantic HTML5 with custom data-attributes (`data-hero`, `data-listing-card`, `data-bottle`, etc.).
* **Styling**: Tailwind CSS via CDN (`https://cdn.tailwindcss.com`) with tailored theme extensions and vanilla CSS custom properties.
* **Typography**: Google Fonts — **Anton** (Display / Headlines) and **Inter Tight** (Body / Sans / UI).
* **Animation Engine**: **GSAP 3.12.5** + **ScrollTrigger** (`https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js` & `ScrollTrigger.min.js`).
* **Text Splitting**: Built-in native `SplitTextPlugin` class polyfill (zero dependency, no paid GSAP Club token required).
* **Video Media**: HTML5 4K cinematic video (`nidhi-tea-cinematics-.mp4`) with custom custom glassmorphic UI controls.

---

## 2. Final Design System & Aesthetics

### Color Palette (Hex & CSS Variables)
```css
:root {
  --background: #100B06; /* Rich earthy deep obsidian dark background */
  --cream:      #F6E9D7; /* Warm natural organic milk-cream typography & accents */
  --gold:       #BE8D3F; /* Warm heritage artisanal gold (Masala Chai blend tint) */
  --flame:      #F15726; /* Vibrant citrus amber (Honey Lemon Green Tea tint) */
  --cherry:     #C4321C; /* Royal floral ruby (Rose Cardamom Black Tea tint) */
  --smoke:      #2A231C; /* Deep brown-smoke neutral panel tone */
}
```

### Typography Hierarchy
* **Display / Headlines**: Google Font **Fraunces** (`font-family: 'Fraunces', serif; font-optical-sizing: auto;`)
  * Applied to `h1, h2, h3, h4, h5, h6`, Tailwind classes `font-display` / `font-heading`, and `.display-tight` with `text-transform: uppercase`, `line-height: .88`, `letter-spacing: -.005em`, `font-weight: 700`.
* **Subtitles & Outlined Text**:
  * `.text-outline`: `color: transparent; -webkit-text-stroke: 1.5px var(--cream);`
  * `.number`: `color: transparent; -webkit-text-stroke: 3px var(--cream); letter-spacing: 0.02em;`
* **Body / Interface**: Google Fonts **Inter Tight** & **Poppins** (`font-family: "Inter Tight", "Poppins", system-ui, sans-serif;`) with crisp `-webkit-font-smoothing: antialiased`.

### Visual Treatments & Textures
* **Noise Panels (`.noise-panel`)**: Subtle dark textured cards (`#1A130C` with radial dotted matrix).
* **Dotted Dividers (`.dotted-rule`)**: `repeating-linear-gradient` horizontal rules between sections.
* **Animated Scroller Line (`.why-line`)**: 300% width repeating linear dotted track driven across the screen by GSAP ScrollTrigger.

### Shape & Component Architecture
* **Radius System**: Restrained 10px corner language (`rounded-lg: 10px`, `rounded-xl: 12px`, `rounded-md: 8px`, `rounded-sm: 4px`).
* **Elevation & Framing**: Flat, framed surfaces with delicate 1px/2px borders rather than heavy drop shadows on card containers.
* **Buttons**:
  * Primary (`bg-cream text-background`): `rounded-lg` (10px), 56px height, sturdy padding (`px-3.5 py-3.5`), 2px border.
  * Secondary (`bg-transparent text-cream border-2 border-cream`): `rounded-lg` (10px), 56px height, outlined counterpart.
* **Cards & Inputs**: `rounded-lg` (10px), surface fill, clean framed border, generous vertical breathing room.

---

## 3. Master Animation Directory

All animations in this project are finalized and calibrated for 60fps hardware-accelerated performance:

| Animation Feature | Mechanism | Key Elements / Selectors | Description |
| :--- | :--- | :--- | :--- |
| **1. Preloader Reveal** | GSAP Timeline | `#loader`, `.pl-revealer`, `.pl-item`, `.pl-logo` | 4 staggered circular SVG clip-path reveals, botanical items flying to 4 corners with floating idle, exploding outward on exit, and logo shooting upwards. |
| **2. Hero Title Elastic Pop** | GSAP + SplitText | `#heroTitle .char` | Individual characters split and animated into place with `elastic.out(0.75, 0.25)` entrance. |
| **3. Hero Floating Pack** | CSS Keyframe | `.hero-floating-pack` (`@keyframes hero-pack-float`) | Subtle 5s idle levitation (`rotate(5deg) translateY(-16px)`). |
| **4. Hero Disc Pulse** | CSS Keyframe | `.animate-hero-bg` (`@keyframes hero-bg-pulse`) | Breathing 6s scale cycle (`0.96` to `1.04`) behind active product pack. |
| **5. Hero Companion Accents** | CSS Keyframe + JS Shrink/Bloom | `#heroTopWrap`, `#heroBottomWrap`, `.animate-float-companion-*` | Botanical accents levitate diagonally; upon slide transition, they scale down to 0, swap ingredient images, and bloom back with spring easing. |
| **6. Hero Carousel Slide** | Vanilla JS + Cubic-Bezier | `#heroSlides`, `data-hero-slide` | 3D depth transitions: Active slide is scale 1; outgoing slides shrink to 0.35 and translate ±120% with rotation. |
| **7. Hero Mouse Parallax** | GSAP `mousemove` | `#top`, `#heroTintWrap`, `#heroSlides` | Smooth interactive mouse movement parallax tracking cursor position. |
| **8. Header Morph on Scroll** | Vanilla JS scroll listener | `#logoBox`, `#navLinks`, `#navPill`, `#navBurger` | Above 80px scroll, large header logo shrinks, desktop links tuck away, and compact "Shop Tea" CTA pill docks in top right. |
| **9. Intro Text Word Scrub** | GSAP ScrollTrigger | `#introText .intro-word` | Text words smoothly brighten from `opacity: 0.15` to `opacity: 1` as user scrolls down. |
| **10. Benefits Floating Spices** | GSAP ScrollTrigger + CSS Float | `.floating-food-item` | 8 organic tea elements pop into view with spring elastic scale on scroll, then continuously float. |
| **11. Benefits Sticky Stack** | Vanilla JS scroll/dim | `#benefits .bene-wrap`, `.bene-dim` | Cards stack with custom top offsets (`BASE + i * HEADER`) and previous cards darken via `.bene-dim` opacity transition. |
| **12. Product Cards 3D Lift** | GSAP ScrollTrigger + CSS 3D | `#productGrid .prod`, `[data-bottle]`, `[data-shadow]` | On hover, bottle pack floats upwards (`translateY(-24px)`), shadow contracts, ingredient badges fan out, and action buttons reveal. |
| **13. Why Standalone SVG Arc** | GSAP ScrollTrigger | `#whyIntroSection`, `#whyArcPath`, `svg` | Huge curved headline follows SVG path, reveals with smooth scaling and ambient pulsing background glow. |
| **14. Why Horizontal Scrub** | GSAP ScrollTrigger Pinned Timeline | `#whySection`, `#whyStickyContainer`, `.slide-1`, `.slide-2`, `.slide-3` | Pinned `300vh` section where 3 giant numbered slides glide horizontally across screen as user scrolls, synchronized with the moving dotted line. |
| **15. Cinema 4K Video Section** | GSAP ScrollTrigger + HTML5 Video API | `#cinemaSection`, `#cinemaFrame`, `#cinemaVideo` | Video container scales up from 0.88 to 1.0 on scroll, auto-plays when entering viewport, with glassmorphic play/pause, scrubbable progress bar, mute, and fullscreen. |
| **16. Reels Video Slider ("Loved By All")** | GSAP Ticker + Infinite Wrap | `#reviewTrack`, `.reel-video`, `.reel-sound-btn` | Hardware-synchronized continuous infinite auto-glide across 6 creator video review cards with hover-pause, mouse drag/touch swipe, and sound toggle. |

---

## 4. What Was Changed (Transformation History)

> [!NOTE]
> This codebase was adapted from an experimental sauce layout into an authentic, production-grade Artisanal Tea platform:

1. **Brand Identity Shift**:
   * Changed from "Bucks Sauce" hot sauce theme to **"Nidhi Tea — Sip Wellness, Taste Purity"**.
   * Replaced pepper imagery with authentic high-resolution transparent tea elements (Assam loose leaves, blooming jasmine teapot, Yixing clay pot, raw ginger, fresh mint, star anise, cinnamon, dripping honey dipper).
2. **Hero Slide Architecture Overhaul**:
   * Upgraded to 3 flagship tea blends:
     1. `Blend N0.01`: **Classic Masala Chai** (`var(--gold)`)
     2. `Blend N0.02`: **Honey Lemon Green Tea** (`var(--flame)`)
     3. `Blend N0.03`: **Rose Cardamom Black Tea** (`var(--cherry)`)
   * Introduced dual floating companion botanical accents that dynamically swap and bloom per blend.
3. **Dedicated 4K Cinematic Tea Story Added (`#cinemaSection`)**:
   * Integrated `nidhi-tea-cinematics-.mp4` with a custom-engineered, fully responsive HTML5 video player.
   * Features GSAP ScrollTrigger scroll expansion, scroll autoplay/pause, seekable progress bar, time counters, mute/unmute, and fullscreen mode.
4. **Why Nidhi Tea Section Redesign**:
   * Separated into an **Intro Arched Heading Section** (`#whyIntroSection`) using dynamic SVG `<textPath>` and a **3-Phase Scroll-Pinned Scrub** (`#whySection`).
   * Pinned horizontal scrub with 3 slides featuring huge outlined numbers (`01`, `02`, `03`), badge pills, and floating mascot teapots.
5. **Enhanced Preloader & Elastic Heading Reveal**:
   * Circular reveals reveal botanical ingredients floating to 4 quadrants, followed by an explosion exit and elastic typography character pop for `#heroTitle`.

---

## 5. What CAN Be Changed (Safe Modifications)

When making modifications or updates, **ONLY** edit within the following safe zones:

### A. Text & Copy Content
* **Headings, Taglines, Body Paragraphs**:
  * Hero title text in `#heroTitle`.
  * Hero intro text in the `TEXT` variable in JS:
    ```javascript
    const TEXT = "Premium handcrafted teas sourced from the finest estates. ★ No artificial additives...";
    ```
  * Why Nidhi Tea paragraph copy inside `.slide-1 .text`, `.slide-2 .text`, `.slide-3 .text`.
  * Cinema header text in `.cinema-header`.
  * Footer about text, copyright notices, and company details.

### B. Product Offerings & Slide Data
* **Hero Slides (`SLIDES` array)**:
  * You can update names, image paths, tints, and companion ingredients in:
    ```javascript
    const SLIDES = [
      { name: "...", img: "img/...", tint: "var(--gold)", topIngredient: "...", bottomIngredient: "..." },
      ...
    ];
    ```
* **Product Catalog (`PRODUCTS` array)**:
  * You can add, edit, or adjust items, prices, and descriptions in:
    ```javascript
    const PRODUCTS = [
      { name: ["Classic", "Masala", "Chai"], tagline: "...", front: "img/...", fruit: "...", bg: "#BE8D3F", price: "₹299" },
      ...
    ];
    ```

### C. Testimonials & Reels
* **Reel Cards (`REELS` array)**:
  * Safe to add, remove, or modify creator reel video entries:
    ```javascript
    const REELS = [
      { handle: "@...", displayName: "@...", link: "https://...", video: "video/reels/...", cdn: "https://...", poster: "img/reels/..." },
      ...
    ];
    ```

### D. Media Assets (Images & Video)
* **Image Replacements**:
  * Safe to replace images in `img/` or `element-img/` as long as the new assets are transparent PNG or WebP files with comparable aspect ratios.
* **Video Source**:
  * Can update `<source src="nidhi-tea-cinematics-.mp4" type="video/mp4" />` with another MP4 path.

### E. Links & Form Handlers
* Social links (`In`, `Fa`) in the footer.
* Newsletter form submission handler (currently `onsubmit="return false"`).
* Navigation anchor links (`href="#products"`).

---

## 6. What MUST NOT Be Changed (Strict Rules / Danger Zone)

> [!CAUTION]
> The following components, selectors, math formulas, and layout structures MUST NOT be altered without breaking the core layout and animations:

### 1. DO NOT Alter JavaScript Hook IDs and Classes
The following IDs and classes are strictly bound to GSAP timelines and scroll listeners:
* Preloader: `#loader`, `.pl-bg`, `.pl-revealer`, `.pl-item`, `.pl-logo`, `.pl-last`
* Hero: `#heroTitle`, `.char`, `.word`, `#heroSlides`, `.hero-slide-item`, `#heroTintWrap`, `#heroTint`, `#heroTopWrap`, `#heroBottomWrap`, `#heroTopImg`, `#heroBottomImg`, `[data-hero]`, `#heroNo`, `#heroName`
* Navigation: `#logoBox`, `#logoImg`, `#navLinks`, `#navPill`, `#navBurger`, `#mobileMenu`
* Floating Food & Intro: `#intro`, `#introText`, `.intro-word`, `.floating-food`, `.floating-food-item`
* Benefits: `#benefits`, `.bene-wrap`, `.bene-dim`
* Products: `#products`, `#productGrid`, `.prod`, `[data-bottle]`, `[data-shadow]`, `.fruitTL`, `.fruitBR`, `.fruitTR`, `.fruitBL`, `.tagline`, `.actions`
* Why Pinned Section: `#whySection`, `#whyStickyContainer`, `.slide`, `.slide-1`, `.slide-2`, `.slide-3`, `.why-line`, `.num-wrapper`, `.number`
* Cinema Video: `#cinemaSection`, `#cinemaArena`, `#cinemaFrame`, `#cinemaVideo`, `#cinemaPlayBtn`, `#cinemaMiniPlayBtn`, `#cinemaMuteBtn`, `#cinemaFullscreenBtn`, `#cinemaProgressBar`, `#cinemaProgressFill`, `#cinemaTime`, `#cinemaOverlay`
* Reviews: `#reviewsSection`, `#reviewTrack`, `.reviews-title`
* Footer: `#footerSection`, `.footer-grid`

### 2. DO NOT Remove or Alter External CDN Scripts
* **Tailwind CDN**: `<script src="https://cdn.tailwindcss.com"></script>`
* **GSAP 3.12.5**: `<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>`
* **ScrollTrigger**: `<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>`
* **SplitText Emulation**: Do not delete the `SplitTextPlugin` class definition at line 857.

### 3. DO NOT Touch the Scroll Height Formula on `#whySection`
* `#whySection` MUST retain `class="relative w-full h-[300vh] bg-background"`.
* `#whyStickyContainer` MUST retain `sticky top-0 h-screen w-full overflow-hidden`.
* Modifying this height or sticky configuration will break the GSAP horizontal scrub pinned timeline completely.

### 4. DO NOT Remove CSS Transforms & Performance Optimizations
* Any element with `will-change-transform` has been placed there to force GPU layer compositing and prevent frame drops during GSAP scrubbing.
* Do not remove inline styles such as `transform: translate3d(...)` or `clip-path: circle(...)`.

### 5. DO NOT Remove `muted` and `playsinline` on the Video
* Modern web browsers strictly forbid autoplay for videos with audio. The `muted` and `playsinline` attributes on `#cinemaVideo` are mandatory for the ScrollTrigger intersection autoplay to function.

---

## 7. Development & Testing Commands

To serve and preview the website locally:
```bash
# Python 3 built-in HTTP server
python -m http.server 8000

# Or using Node http-server / npx serve
npx -y serve .
```
Visit: `http://localhost:8000` (or the port specified).

---
*Created for Dipak Halder / Nidhi Tea repository. Maintained by AI Engineering.*
