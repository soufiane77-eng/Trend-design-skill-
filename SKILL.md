---
name: moroccan-premium-brand-design
description: Use when designing premium Moroccan, North African, or Middle Eastern brand experiences — coffee houses, restaurants, riads, spas, art galleries, or luxury boutiques. Triggers on "Moroccan coffee", "café marocain", "riad design", "Moroccan luxury", "North African brand", "oriental premium", "Marrakech style", "zellige", "Moroccan typography".
---

# Moroccan Premium Brand Design

## Overview

A comprehensive design system and aesthetic framework for creating **ultra-premium Moroccan / North African brand experiences**. This skill produces production-ready HTML/CSS/JS that rivals luxury architecture and hospitality brands. The reference implementation is **EL QAHWA** — a Moroccan coffee house brand.

The core insight: **Moroccan luxury is about warmth, not cold minimalism. It's about texture, pattern, light, and ritual.** The palette draws from terracotta, gold, espresso, and cream — never sterile whites or cold grays.

## When To Use

| Use Case | Example |
|----------|---------|
| **Moroccan coffee brand** | Café, coffee shop, roastery website |
| **North African restaurant** | Premium dining, riad, rooftop lounge |
| **Luxury hospitality** | Riad hotel, spa, hammam, boutique |
| **Artisan brand** | Pottery, textiles, zellige, leather |
| **Oriental luxury e-commerce** | Home decor, fragrance, spices |
| **Cultural institution** | Museum, gallery, cultural center |

## Design System

### Color Palette

```css
:root {
  /* Core — Warm & Rich */
  --espresso:       #1C0F0A;  /* Deepest brown — texte sur fond clair */
  --espresso-light: #2D1810;  /* Brown légèrement adouci */
  --cream:          #F5EDE0;  /* Warm cream — fond principal */
  --ivory:          #FDF8F3;  /* Ivoire chaud — fond secondaire */
  --sand:           #E8DDD0;  /* Sable — transitions, bordures */

  /* Accents — Gold & Terracotta */
  --gold:           #C9A84C;  /* Or — accent principal, CTA */
  --gold-light:     #E8D5A3;  /* Or doux — hover, lueurs */
  --terracotta:     #C8765A;  /* Tomette — accent secondaire */
  --terracotta-dark:#A85D42;  /* Tomette foncée */
  --sage:           #7BA89A;  /* Sauge — accent ponctuel (optionnel) */

  /* Text */
  --ink:            #1C0F0A;  /* Texte principal */
  --muted:          #6B5A4E;  /* Texte secondaire, notes */
}
```

**Rules:**
- The background should **never** be pure white (`#FFFFFF`). Use `#FDF8F3` (ivory) or `#F5EDE0` (cream).
- The darkest tone should **never** be pure black (`#000000`). Use `#1C0F0A` (espresso).
- Gold is the **primary accent** — use it sparingly on CTAs, dividers, decorative elements.
- Terracotta is the **secondary accent** — use for italic words, highlights, stats.

### Typography

```css
--display: 'Playfair Display', serif;  /* Titres — élégance classique */
--body:    'Outfit', sans-serif;       /* Corps de texte — modernité épurée */
```

| Usage | Font | Style | Size range |
|-------|------|-------|------------|
| Brand name (hero) | Playfair Display | 700, uppercase, italic | `clamp(4rem, 12vw, 12rem)` |
| Section headings | Playfair Display | 400-600, mixed case | `clamp(2.5rem, 5vw, 4.5rem)` |
| Italic emphasis | Playfair Display | 400 italic | same as parent |
| Body text | Outfit | 300-400 | `0.875rem - 1rem` |
| Labels / metadata | Outfit | 500-600, uppercase, `tracking: 0.2-0.4em` | `0.625rem - 0.75rem` |
| Navigation | Outfit | 500, uppercase, `tracking: 0.25em` | `0.625rem` |

**Pairing rule:** Headlines in serif (Playfair Display) evoke heritage, craftsmanship, time. Body in sans-serif (Outfit) keeps the page modern and readable. Never use a generic sans like Inter or Roboto — Outfit has warmer geometric character.

### Spacing & Rhythm

```
Section padding:  py-24 (6rem) mobile, py-36 (9rem) desktop
Gap grid:         gap-10 to gap-16 between columns
Card padding:     p-6 to p-8
Border radius:    2rem (32px) for large containers, 1rem (16px) for cards
```

- Use generous whitespace — Moroccan luxury breathes
- Asymmetrical grids (12 columns, 5+7 or 6+6 splits)
- Overlapping elements for depth (floating badges, offset images)

## Layout Patterns

### Hero — Full-Screen Immersion

```
┌──────────────────────────────────────┐
│          ░░ GRAIN OVERLAY ░░         │
│  ┌────────────────────────────────┐  │
│  │  HEADER (transparent → blur)   │  │
│  ├────────────────────────────────┤  │
│  │                                │  │
│  │  BRAND NAME (massive serif)    │  │
│  │  Tagline (elegant, small)      │  │
│  │  CTA buttons (premium)         │  │
│  │                     ┌─────────┐│  │
│  │                     │Glass    ││  │
│  │                     │Card     ││  │
│  │                     │(product)││  │
│  │                     └─────────┘│  │
│  │  ──── gradient divider ────    │  │
│  │                                │  │
│  │  Material Card | Stats | Text  │  │
│  └────────────────────────────────┘  │
└──────────────────────────────────────┘
```

**Key technique:** The hero image has a dark gradient overlay (`rgba(28,15,10, 0.6→0.85)`) — NOT a simple black overlay. This keeps warmth.

### Section — Alternating Rhythm

Sections alternate backgrounds:
```
Section 1: --cream  (Notre Histoire)
Section 2: --ivory  (Nos Crus)
Section 3: --cream  (Le Rituel)
Section 4: --ivory  (Notre Espace / Contact)
```

### Product Grid — 3 Cards

Three cards with:
- Image on top (4:3 ratio)
- Product name in serif
- Origin/blend type label
- Tasting notes as tags
- Price in serif
- Add to cart button

On hover: 3D tilt transform (CSS `perspective(1000px) rotateX/Y`), image zoom, elevation change.

### Experience Timeline — Vertical Steps

Numbered steps (01–04) with:
- Circle number on left
- Connector line between steps
- Title + description on right
- Last step in gold (destination)

## Moroccan Decorative Elements

### 1. Geometric Pattern (subtle background)

```css
.geometric-pattern {
  background-image:
    linear-gradient(45deg, var(--ink) 25%, transparent 25%),
    linear-gradient(-45deg, var(--ink) 25%, transparent 25%),
    linear-gradient(45deg, transparent 75%, var(--ink) 75%),
    linear-gradient(-45deg, transparent 75%, var(--ink) 75%);
  background-size: 40px 40px;
  opacity: 0.04;
}
```

Use as subtle background texture — never prominent. It should be barely perceptible.

### 2. Arch Divider

```css
.arch-divider {
  width: 120px; height: 60px;
  border: 1px solid var(--border-medium);
  border-top: none;
  border-radius: 0 0 60px 60px;
}
/* Gold dot in center */
.arch-divider::after {
  content: ''; width: 6px; height: 6px;
  background: var(--gold); border-radius: 50%;
  position: absolute; top: -1px; left: 50%; transform: translateX(-50%);
}
```

### 3. Arch Decor (CSS border-radius trick)

Use `border-radius: 2rem` on containers and cards — the rounded corners evoke Moroccan arches without being literal.

### 4. Grain Texture Overlay

```css
.grain-overlay {
  position: fixed; inset: 0; z-index: 9999; pointer-events: none; opacity: 0.025;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 400 400' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E");
  background-size: 200px 200px;
}
```

### 5. Footer Pattern (dot grid)

```css
.footer-pattern {
  background-image: radial-gradient(circle at 1px 1px, rgba(201, 168, 76, 0.08) 1px, transparent 0);
  background-size: 32px 32px;
}
```

## Animation System

| Animation | When | Easing | Duration | CSS |
|-----------|------|--------|----------|-----|
| **Reveal up** | Sections entering viewport | `cubic-bezier(0.19, 1, 0.22, 1)` — ease-out expo | 1.2s | `translateY(50px) → translateY(0)` + `opacity 0→1` |
| **Reveal left/right** | Side content entering | `cubic-bezier(0.165, 0.84, 0.44, 1)` — ease-out quart | 1.0s | `translateX(±40px) → 0` + `opacity 0→1` |
| **Fade in** | Background, persistent elements | `ease-out` | 1.5s | `opacity 0→1` |
| **Scale in** | Cards, gallery | `cubic-bezier(0.19, 1, 0.22, 1)` | 1.2s | `scale(0.92) → 1` + `opacity 0→1` |
| **Pulse dot** | Interactive hotspots, status | `cubic-bezier(0.4, 0, 0.6, 1)` | 3s infinite | `scale(1→1.15→1)` + opacity |
| **Steam** | Coffee imagery | `ease-out` | 3s infinite | Height + opacity + translateX |
| **Record spin** | Music button playing | `linear` | 8s infinite | `rotate(0→360deg)` |
| **Hover lift** | Cards, buttons | `cubic-bezier(0.165, 0.84, 0.44, 1)` | 0.6s | `translateY(-4px)` + shadow |
| **3D tilt** | Product cards | Custom per mouse | 0.6s | `rotateX/Y` via JS |

### Scroll Trigger Implementation

Use Intersection Observer with `threshold: 0.12` and `rootMargin: 0px 0px -40px 0px`. Elements start with `opacity: 0` and `animation-play-state: paused`, then are set to `running` when they enter the viewport.

### Staggered Delays

```css
/* Hero elements stagger in */
.reveal-up { animation-delay: 0.8s; }  /* h1 */
.reveal-up { animation-delay: 1.1s; }  /* tagline */
.reveal-up { animation-delay: 1.4s; }  /* buttons */
.reveal-right { animation-delay: 1.2s; } /* glass card */

/* Section reveals */
.reveal-left { animation-delay: 0s; }
.reveal-up { animation-delay: 0.2s; }
.reveal-up { animation-delay: 0.4s; }
```

## Glass Card Component

```css
.glass-card {
  background: rgba(253, 248, 243, 0.72);           /* --ivory at 72% */
  backdrop-filter: blur(24px) saturate(200%) brightness(1.05);
  border: 1px solid rgba(255, 255, 255, 0.5);
  box-shadow:
    0 4px 6px -1px rgba(28, 15, 10, 0.04),
    0 10px 15px -3px rgba(28, 15, 10, 0.06),
    0 20px 40px -8px rgba(28, 15, 10, 0.1);
}
```

## Premium Button Component

```css
.btn-premium {
  background: linear-gradient(135deg, var(--espresso) 0%, var(--espresso-light) 100%);
  box-shadow: 0 4px 6px -1px rgba(28,15,10,0.12), 0 2px 4px -2px rgba(28,15,10,0.08);
  position: relative;
  overflow: hidden;
}
.btn-premium::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(201,168,76,0.15) 0%, transparent 100%);
  opacity: 0;
  transition: opacity 0.5s ease;
}
.btn-premium:hover {
  transform: translateY(-3px) scale(1.02);
  box-shadow: 0 20px 25px -5px rgba(28,15,10,0.2), 0 10px 10px -5px rgba(28,15,10,0.12);
}
.btn-premium:hover::before { opacity: 1; }
```

## Music Player Component

### Design
- Fixed position, bottom-left (32px from edges)
- Circle button (56px), espresso with gold border
- "Record spin" animation when playing (dashed border rotates)
- Tooltip appears on hover with track status

### Behavior
- Click to toggle play/pause
- Press `M` key as shortcut
- Volume fades in/out smoothly (over ~0.5s)
- Volume at 25% max for background ambiance
- `audio.load()` called on page load (pre-buffer without playing)
- Error state shown gracefully if file not found
- No autoplay — requires user gesture

### HTML Structure
```html
<audio id="bg-music" preload="auto" loop>
  <source src="votre-musique.mp3" type="audio/mpeg">
</audio>
<div id="music-player" role="button" tabindex="0">
  <div id="music-btn" class="music-btn">
    <iconify-icon icon="lucide:music" class="icon-music"></iconify-icon>
  </div>
  <div class="music-tooltip">
    <span class="status-dot"></span>
    <span><em id="track-status">Cliquez pour jouer</em> Café Marocain</span>
  </div>
</div>
```

## Quality Checklist

Before considering a design complete, verify:

- [ ] **Colors**: No pure white or pure black anywhere? Background is warm (cream/ivory)?
- [ ] **Typography**: Headlines in serif (Playfair Display or equivalent)? Body has character (not Inter/Roboto)?
- [ ] **Texture**: Grain overlay present? Geometric pattern as subtle background?
- [ ] **Glass card**: At least one glassmorphic element with blur + transparency?
- [ ] **Buttons**: Premium buttons with gradient, hover lift, and inner glow?
- [ ] **Animations**: Staggered reveals on page load? Scroll-triggered section entries?
- [ ] **Images**: All have hover zoom effect? Lazy loading with shimmer placeholder?
- [ ] **Moroccan touch**: At least one decorative element (arch, geometric pattern, zellige)?
- [ ] **Responsive**: Works on mobile? Grid collapses to single column?
- [ ] **Accessibility**: Reduced motion supported? Focus visible? Keyboard navigable?
- [ ] **Music** (optional): Floating music button? Smooth fade in/out? M key shortcut?
- [ ] **Brand story**: Is there a heritage section? Counter animation for years/products?
- [ ] **CTA**: Premium button that invites action? Reservation form for hospitality?

## Reference Implementation

See `examples/EL-QAHWA.html` for the complete reference implementation (2100+ lines of production HTML/CSS/JS).

### Sections in Reference
1. **Hero** — Full-screen, massive typography, glass product card with steam animation
2. **Notre Histoire** — Two-column with heritage story, counter stats, 3D tilt image, floating badge
3. **Nos Crus** — 3 product cards with 3D hover, tasting notes, pricing
4. **Le Rituel** — 4-step timeline with connector lines, Arabic proverb quote
5. **Notre Espace** — Masonry gallery grid with hover overlays
6. **Contact** — Reservation form in glass card, contact details
7. **Footer** — Dark with gold accents, newsletter, social links, hours

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Using pure white background | Replace `#FFFFFF` with `#FDF8F3` (ivory) |
| Using pure black text | Replace `#000000` with `#1C0F0A` (espresso) |
| Minimalist/sterile layout | Add grain texture, geometric pattern, warm tones |
| Generic fonts | Use Playfair Display + Outfit (or equivalent character) |
| No scroll animations | Add Intersection Observer with staggered reveals |
| Flat buttons | Add gradient, shadow, hover lift, inner glow |
| Centered/symmetric layout | Use 12-column grid with asymmetric splits |
| No brand narrative | Add counter stats, heritage section, story paragraph |
| Autoplaying music | Never autoplay — require user gesture, use fade in |

## Evolving Beyond

This skill captures the **EL QAHWA** baseline. To exceed it:

- **More ambitious layouts**: Full-bleed sections, diagonal splits, overlapping hero text
- **WebGL / Three.js**: Particle systems, 3D coffee bean models, fluid simulations
- **Scroll-driven animations**: CSS `scroll-timeline`, parallax layers, reveal-on-scroll progress
- **Custom illustrations**: Moroccan patterns in SVG, animated zellige tiles
- **Micro-interactions**: Magnetic buttons, custom cursor trails, ripple effects
- **Page transitions**: View Transitions API for smooth navigation between sections
- **Variable fonts**: Playfair Display or equivalents with optical size axis for responsive typography
- **Dark mode**: A warm dark variant (deep espresso background, gold text, cream accents)
