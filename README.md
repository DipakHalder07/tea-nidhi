# Nidhi Tea — Premium Handcrafted Teas

> **Sip Wellness. Taste Purity. Love Every Cup.**
> An artisanal, high-performance web experience crafted with Tailwind CSS and GSAP.

---

## 🍵 Project Overview

Nidhi Tea is an interactive single-page e-commerce landing experience built for a premium organic tea brand. Featuring smooth 60fps micro-animations, scroll-scrubbed storytelling, 3D interactive product showcases, and a cinematic 4K video experience.

### ✨ Key Features & Animations

- **Dynamic Preloader**: Staggered circular reveal sequence with floating botanical elements and elastic typography character entrance.
- **Interactive Hero Carousel**: Multi-blend switcher with dynamic background tint morphing, 3D pack depth scaling, and companion botanical shrink-and-bloom effects.
- **GSAP Scroll-Triggered Text Scrub**: Smooth opacity reveals on brand storytelling typography as the user scrolls.
- **Stacked Sticky Benefits**: Layered feature cards that stack and dim sequentially on scroll.
- **3D Floating Product Cards**: Cards with interactive hover physics, pack lift, shadow scaling, and botanical fan-outs.
- **Curved Arched SVG Headline**: Standalone arched typography (`WHY NIDHI TEA`) aligned with ambient pulsing lighting.
- **Scroll-Pinned Horizontal Showcase**: 3-phase horizontal slide scrub locked over a `300vh` scroll track with continuous moving dotted guidelines.
- **4K Cinematic Tea Story**: Custom HTML5 video arena featuring viewport autoplay, scroll-expansion, glassmorphic controls, seeking progress bar, and fullscreen mode.
- **Infinite Reviews Marquee**: Continuous customer testimonial track.

---

## 🚀 How to Run Locally

Serve the project using any local web server:

```bash
# Using Python 3
python -m http.server 8000

# Or using Node.js
npx -y serve .
```

Open `http://localhost:8000` in your web browser.

---

## 🤖 AI Guidelines & Architecture Rules

For AI coding assistants (Gemini, Antigravity, Cursor, Claude, Windsurf, Copilot) working on this project:

- Read [GEMINI.md](file:///c:/Users/USER/Downloads/Nidhi%20Tea/Nidhi%20Tea/GEMINI.md) for full design system tokens, animation specs, safe modification zones, and strict **DO NOT TOUCH** rules.
- Read [AGENTS.md](file:///c:/Users/USER/Downloads/Nidhi%20Tea/Nidhi%20Tea/AGENTS.md) for quick-reference rules.

---

## 📁 Project Structure

```
├── index.html                  # Core single-page application (HTML, CSS, JS)
├── GEMINI.md                   # Permanent AI Context, Design & Animation Rulebook
├── AGENTS.md                   # Universal AI Agent guidelines
├── README.md                   # Project overview & documentation
├── nidhi-tea-cinematics-.mp4   # 4K Cinematic promotional tea video
├── element-img/                # Transparent high-res botanical elements & teapots
│   ├── isolated_ceramic_bowl_of_dark_loose_leaf_oolong_tea...png
│   ├── isolated_cinnamon_sticks_star_anise_and_dried_orange...png
│   ├── isolated_fresh_green_tea_leaves_with_water_droplets...png
│   ├── isolated_glass_teapot_filled_with_blooming_jasmine...png
│   ├── isolated_honey_dipper_with_dripping_golden_honey...png
│   ├── isolated_rustic_clay_tea_pot_yixing_style_side_view...png
│   ├── isolated_steaming_cup_of_green_tea_in_a_porcelain...png
│   └── isolated_vintage_silver_tea_strainer_with_loose...png
├── img/                        # Product pack renders, logo & icons
│   ├── hero.png                # Classic Masala Chai pack
│   ├── product-2.png           # Honey Lemon Green Tea pack
│   ├── product-3.png           # Rose Cardamom Black Tea pack
│   └── logo.webp               # Nidhi Tea brand logo
└── assets/                     # Legacy SVG icons & supporting assets
```

---
© 2026 Nidhi Tea. All rights reserved.
