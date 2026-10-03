# Neon Drift — Generative Art

> A seed-based generative system for drifting-line compositions.  
> A reproducible catalogue of computational drift studies.

---

## What is this?

**Neon Drift** is a generative design system built on accumulation and drift. A single line travels through the field, bouncing off its edges, changing its trajectory with each pass. The line is redrawn between one and three hundred times — each stroke slightly shifted, slightly recoloured — until the accumulated strokes form a luminous cloud of neon.

Every artwork in this catalogue is defined by a single numeric seed. The same seed always produces the identical composition — making each piece **traceable, reproducible, and licensable** across textile, print, and apparel applications.

Named for the drift of a line that never stops moving, **Neon Drift** reframes accumulation as a textile.

---

## Live

🌐 **[View the catalogue →](https://reyrove.github.io/Neon-Drift/)**

---

## The System

The generator is a single-layer system — a drifting shape whose positions, sizes, colours, and strokes are all seeded:

| Layer | Description |
|-------|-------------|
| **Ground** | A seeded dark RGB background, computed to contrast with the neon strokes. |
| **Drift** | One shape (line, ellipse, or rectangle) redrawn 100–300 times, its position updated between each pass. |

Both layers are driven by the same seed, ensuring deterministic output.

### Parameters

- **Line count** — 100 to 300 strokes
- **Shape mode** — 0 = lines, 1 = ellipses, 2 = rectangles
- **Initial colour** — `r: 190–255`, `g: 190–255`, `b: 180–255` (neon range)
- **Colour drift** — ±10 per stroke, constrained to `[150, 255]`
- **Position drift** — seeded deltas, up to 20% of the canvas width
- **Bounds behaviour** — reflects off all four edges
- **Stroke weight** — `w / 1000` to `w / 500`, seeded
- **Background** — a seeded RGB triplet

---

## Structure

```
Neon-Drift/
├── index.html              ← Full catalogue (single-file)
├── images/
│   ├── fav.svg
│   ├── neondrift-tote.png
│   ├── neondrift-cushion.png
│   └── ...
├── Neon-Drift.jpg          ← Apparel mockup
└── README.md
```

The entire project is contained in a single `index.html` — no build step, no dependencies, no framework. Open it in any modern browser.

---

## Features

- **Seed-based generation** — every composition is deterministic and reproducible
- **Live catalogue** — cover, statement, plate, surfaces, process, archive, commission sections
- **Multiple surfaces** — print, scarf, textile, wallpaper — all rendered from the same seed
- **Archive of 8 seeds** — click any plate to load it into the main view
- **PNG export** — download any composition directly from the browser
- **Keyboard shortcuts** — `R` for new seed, `S` to save
- **Legal modal** — licensing, terms, and credits built in
- **Responsive** — works on desktop, tablet, and mobile
- **Mobile-first navbar** — horizontally scrollable with fade hint

---

## Usage

### Generate a new composition

Click **New Seed** or press `R`.

### Download the current composition

Click **Download** or press `S`.

### Load a seed from the archive

Click any plate in the **Archive** section.

---

## Color System

Every composition is drawn from two seeded sources:

- **Background** — a fully random RGB triplet, computed once per seed. Because the neon strokes are always bright, the background can be anything from deep shadow to mid-tone.
- **Strokes** — a neon RGB value that starts in the range `[190, 255]` for red and green, `[180, 255]` for blue, then drifts by up to ±10 per stroke while remaining constrained to `[150, 255]`. This keeps the composition luminous but never washed out.

Because both the background and the drift are seeded, no two compositions share the same rhythm of line and hue.

---

## Technical Notes

- Pure vanilla JavaScript — no libraries
- Canvas 2D rendering
- Custom xorshift random generator for deterministic seeds
- Device-pixel-ratio aware rendering
- Fully static rendering — one seed produces one composition, no animation loops
- Single `renderStatic()` function drives the cover, plate, framed print, all four surfaces, and all eight archive thumbnails
- p5.js `ellipse(x, y, w, h)` and `rect(x, y, w, h)` semantics preserved exactly in the Canvas 2D implementation
- `prefers-reduced-motion` respected

---

## About

**Neon Drift** is a project by [Reyhaneh Daneshdoost](https://reyrove.github.io/) — an Iranian-born artist working at the intersection of classical textile logic and generative systems.

The work begins with a simple observation: the woven surface — repetitive, mathematically structured, infinitely variable — has always been a form of computation, long before computers.

**Neon Drift** is an attempt to render that logic visible.

> *A line that never stops moving leaves a trace of everywhere it has been.*

---

## Licensing

All compositions are seed-documented and available for licensing across textile, surface, and apparel applications.

For commercial use, custom editions, or exclusive rights:

📧 **reyhanehdaneshdoost@gmail.com**

See the **Licensing** section in the live catalogue for details.

---

## Links

- 🌐 [Website](https://reyrove.github.io/)
- 📷 [Instagram](https://www.instagram.com/rey._.rove/)
- 💼 [LinkedIn](https://www.linkedin.com/in/reyhaneh-daneshdoost-730481160/)
- 🐦 [X](https://x.com/reyrove)

---

## Credits

**Design & Generative System**  
Reyhaneh Daneshdoost

**Typefaces**  
Cormorant Garamond · DM Mono

**Edition**  
Neon Drift — Autumn 2026

---

<p align="center">
  <em>Generative Drifting Line</em><br />
  <sub>© Reyrove Studio · All compositions reproducible by seed</sub>
</p>