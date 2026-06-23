# Trend design skill  🏺

> A premium design system and AI skill for creating ultra-luxury website design .

## Overview

This repository contains a **reusable design skill** and **reference implementation** for crafting  websites. It was born from the [EL QAHWA](examples/EL-QAHWA.html) project — a luxury Moroccan coffee house brand.

The skill captures everything needed to consistently produce designs that rival luxury hospitality brands: the color system, typography, animation patterns, decorative elements, and quality standards.

## What's Inside

```
moroccan-premium-brand-design/
├── SKILL.md                    # The design skill — reusable by AI agents
├── README.md                   # This file
├── examples/
│   └── EL-QAHWA.html           # Complete reference implementation (2100+ lines)
└── assets/
    └── (placeholder for images, icons, etc.)
```

### For AI Agents

The `SKILL.md` file is structured as an AI skill — it can be loaded by Claude, Gemini, Copilot, or any agent that supports skill frameworks. It tells the agent:

- What aesthetic direction to follow
- Which colors, fonts, and patterns to use
- How to structure the layout
- What animations and interactions to implement
- What quality checks to pass before finishing

### For Designers & Developers

The `examples/EL-QAHWA.html` file is a **production-ready reference implementation**. Open it in a browser to see the full experience:

- 🎨 Moroccan-inspired color palette (espresso, gold, terracotta, cream)
- 📐 Playfair Display + Outfit typography pairing
- ✨ Scroll-triggered reveal animations
- 🔄 3D tilt on product cards
- 🎵 Floating music player with Moroccan ambiance
- 📱 Fully responsive
- ♿ Accessible (reduced motion, keyboard nav, focus indicators)

## The Design Philosophy

```
Moroccan luxury is about warmth, not cold minimalism.
It's about texture, pattern, light, and ritual.
```

**Core principles:**
- No pure white or pure black — warm ivory and deep espresso instead
- Gold as the primary accent — used sparingly for maximum impact
- Terracotta as the secondary accent — for highlights and emphasis
- Serif headlines (heritage) + sans-serif body (modernity)
- Generous whitespace, asymmetric grids, overlapping elements
- Grain texture and geometric patterns as subtle background atmosphere

## Quick Start

1. Open `examples/EL-QAHWA.html` in a browser to see the reference design
2. Read `SKILL.md` to understand the full design system
3. Use the skill with your AI agent to generate new brand designs
4. Adapt the patterns to your own project

### Publishing to GitHub

```bash
# Create a new repository on GitHub, then:
git init
git add .
git commit -m "Initial commit: Moroccan Premium Brand Design skill"
git remote add origin https://github.com/your-username/moroccan-premium-brand-design.git
git push -u origin main
```

## Customization

To adapt the design to a different brand:

1. **Recolor**: Update the CSS variables in the `:root` block
2. **Rename**: Replace "EL QAHWA" with your brand name
3. **Reimage**: Swap Unsplash URLs for your own imagery
4. **Remusic**: Replace the audio source with your own track

## License

MIT — use freely, adapt, remix. Attribution appreciated but not required.
