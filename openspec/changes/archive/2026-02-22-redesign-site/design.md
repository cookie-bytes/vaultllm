## Context

The site is a 6-page static HTML site using Tailwind CSS (CDN) and Alpine.js. It is hosted on GitHub Pages at vaultllm.uk. No build step exists — all changes are made directly in HTML files. The current logo is a hand-crafted SVG that doesn't match the original brand image. Content sections are all plain white, making the layout feel flat. No photography is available.

## Goals / Non-Goals

**Goals:**
- Produce a new `logo.svg` and `logo-icon.svg` that closely match the original Gemini brand image
- Improve visual depth across all pages without adding external dependencies
- Keep all changes to CSS classes and inline SVG — no build step, no new files beyond the logos

**Non-Goals:**
- Changing page content, copy, or structure
- Adding photography or illustration assets beyond SVG
- Changing the Tailwind CDN or Alpine.js setup
- Responsive layout changes

## Decisions

**D1: Logo — stacked SVG with separate horizontal variant**
The original is a stacked mark (icon above wordmark above tagline). The header needs a horizontal variant (icon + wordmark, no tagline) to fit the `h-16` fixed header. Two files: `logo.svg` (stacked, used in footer hero contexts) and `logo-icon.svg` (icon only, used in footer). Header `<img>` uses an inline SVG or a new `logo-horizontal.svg`.

Alternative considered: single SVG with both variants via CSS — too complex for a no-build setup.

**D2: Hero texture — CSS-only dot grid via background-image**
A subtle dot grid on the navy hero using `background-image: radial-gradient(...)` applied inline or via a `<style>` block. No image files needed. Tailwind CDN's arbitrary value support handles this.

Alternative considered: SVG pattern element — works but adds markup noise to every hero section.

**D3: Section alternation — `bg-gray-50` on even sections**
Apply `bg-gray-50` to every other content section (not hero/CTA) across all pages. This is a Tailwind class already available via CDN — no config change needed.

**D4: Icons — inline SVG from Heroicons**
Replace any emoji or basic SVG icons in the pillars and feature lists with Heroicons inline SVG (MIT licensed, no package needed — copy paths directly). Keeps file sizes minimal and renders crisp at all sizes.

**D5: Typography — Tailwind class adjustments only**
Increase hero `h1` from `text-4xl` to `text-5xl md:text-6xl`. Add `leading-tight` and `tracking-tight` where missing. No font changes — Inter is already loaded.

## Risks / Trade-offs

- **Logo SVG complexity** → SVG hand-coding a detailed circuit-lock may not perfectly match the raster original. Mitigation: prioritise overall shape, colour, and feel over pixel accuracy.
- **Inline SVG verbosity** → Heroicons inline SVG adds ~200 chars per icon. Acceptable for a 6-page static site with no build optimisation.
- **`bg-gray-50` on CDN Tailwind** → CDN Play script scans HTML for classes; `bg-gray-50` is a standard class and will be included automatically.

## Migration Plan

1. Create `logo.svg` (stacked), `logo-horizontal.svg` (header), `logo-icon.svg` (footer icon)
2. Update header `<img>` across all 6 pages to `logo-horizontal.svg`
3. Update footer icon `<img>` to `logo-icon.svg`
4. Apply hero dot-grid texture to `index.html` hero
5. Apply `bg-gray-50` alternation to all content sections across all pages
6. Replace pillar/feature icons with Heroicons inline SVG on `index.html` and `services.html`
7. Apply typography class updates across all pages

Rollback: revert `docs/assets/images/logo.svg` and HTML class changes via git.
