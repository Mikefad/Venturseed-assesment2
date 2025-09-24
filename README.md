VenturSeed — Frontend Developer Assignment

Live demo: https://venturseed-assesment2.vercel.app/

Rebuild of the provided Figma home page using Nuxt 3 + Vue 3 + TailwindCSS, with mobile + desktop layouts and a Pixelay comparison.


Tech Stack

Nuxt 3 (Vue 3 + Vite)
TailwindCSS
Nuxt Image (@nuxt/image) – optimized images (format/size), lazy-loading
Small scoped CSS where Figma required absolute positioning


## Pixelay Evidence

<details>
  <summary><strong>Desktop Overlays</strong></summary>

  <p>
    <img src="/pixelay_images/desktop/Screenshot%20(1).png" alt="Desktop Overlay 1" width="900"><br/>
    <img src="/pixelay_images/desktop/Screenshot%20(2).png" alt="Desktop Overlay 2" width="900"><br/>
    <img src="/pixelay_images/desktop/Screenshot%20(3).png" alt="Desktop Overlay 3" width="900">
  </p>
</details>

<details>
  <summary><strong>Mobile Overlays</strong></summary>

  <p>
    <img src="/pixelay_images/mobile/Screenshot%20(1).png" alt="Mobile Overlay 1" width="360"><br/>
    <img src="/pixelay_images/mobile/Screenshot%20(2).png" alt="Mobile Overlay 2" width="360"><br/>
    <img src="/pixelay_images/mobile/Screenshot%20(3).png" alt="Mobile Overlay 3" width="360">
  </p>
</details>

📄 See notes: [pixelay_images/notes.md](./pixelay_images/notes.md)


## Getting Started (Local)

> The Nuxt app lives in **homedesign/** (that’s where `package.json` is).

# bash
cd homedesign
npm install
npm run dev       # http://localhost:3000

# build & preview
npm run build
npm run preview   # http://localhost:3000

What’s Included

Responsive desktop + mobile layouts
Interactive element: mobile menu toggle (and other small UI interactions)
Matching typography/spacing as closely as possible to Figma
Pixelay overlays (desktop + mobile) and notes
Nuxt Image: automatic lazy-loading, size/format optimization, placeholders


Pixelay Evidence

/pixelay
  ├─ pixelay-desktop.png
  ├─ pixelay-mobile.png
  └─ notes.md


How I captured them:

Run the site locally (or open the Vercel URL).

In Pixelay, create overlays:

Desktop: 1440×900 (or your team’s standard desktop viewport).

Mobile: 375×812 (iPhone X/12 footprint) or the device size your team specifies.

Export to /pixelay/pixelay-desktop.png and /pixelay/pixelay-mobile.png.

Add short diffs to /pixelay/notes.md.


Sample notes.md:

# Pixelay Notes

## Desktop (1440×900)
- Typography renders within ±2px vs Figma baseline (browser font metrics).
- Some Figma frames are larger than common 1440 canvases; widths clamped to avoid excessive whitespace.
- Gradient and antialiasing may differ slightly from Figma preview.

## Mobile (375×812)
- Hero “Dart-Native” pill positioned per Figma; subcopy line-height adapted to system font rendering.
- Vector/wave elements adjusted to avoid color bleed on small screens.
- CTA buttons match Figma dimensions (345×40) within 1px tolerance.


Notes, Tradeoffs & Assumptions

Figma frame scale: The source frames are larger than typical desktop viewports. I preserved visual proportion without forcing oversized type that would feel off on real devices. Pixelay may highlight tiny (1–3px) spacing/line-height differences caused by font metrics.

Exact pixel matching vs. web reality: Some absolute positions from Figma were translated into responsive utilities + minimal scoped CSS to keep layouts robust across breakpoints.

Assets: Exported/optimized PNG/SVGs can show tiny color/AA differences compared to Figma’s renderer.

Accessibility (a11y)

Semantic headings (single h1), proper h2/h3 hierarchy.

Buttons are real <button>s; links are <a> with descriptive labels.

Keyboard focus states and logical tab order.

Reduced motion respected (prefers-reduced-motion) for any transitions.



Performance

Static assets served from /public and/or optimized images.

Lazy‐loading where appropriate (loading="lazy" or <NuxtImg> when used).

Minimal JS for interactions; Tailwind for styling.



Project Structure (high-level)
/<app-root>
  ├─ app.vue / pages/
  ├─ components/
  │   ├─ Navbar.vue
  │   ├─ HeroWithVideo.vue
  │   ├─ SectionOpenFeature.vue
  │   ├─ PricingSection.vue
  │   └─ ...
  ├─ public/           # exported images/icons from Figma
  ├─ pixelay/          # Pixelay evidence (see above)
  ├─ tailwind.config.cjs
  ├─ package.json
  └─ README.md



What I’d Do With More Time

Expand test coverage on components with edge cases (long text, missing assets).

Add more interactive elements (accordion, tabs) where appropriate.

Swap heavy PNGs for SVG/Next-gen formats and tune color profiles.

Add CI to generate/attach Pixelay overlays automatically on PR.

Deliverables Checklist


