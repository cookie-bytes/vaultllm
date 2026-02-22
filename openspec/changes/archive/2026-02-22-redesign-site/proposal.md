## Why

The current site is functional but visually underdeveloped. The logo doesn't faithfully reproduce the brand identity from the original image, and the all-white content sections feel flat and generic for a premium security product. No photography is available, so improvements must come from design: better logo, richer section backgrounds, inline SVG icons, and tighter typography.

## What Changes

- Replace `docs/assets/images/logo.svg` with a new SVG faithful to the original: flat-top hexagon, detailed circuit-lock mark, stacked layout (icon + wordmark + tagline) plus a horizontal header variant
- Alternate section backgrounds (`bg-gray-50` / `bg-white`) across all pages to break up the flat white
- Add a subtle radial gradient or dot-grid texture to the navy hero section on `index.html`
- Replace any placeholder icon elements with proper inline SVG icons from Lucide/Heroicons for the three-pillar section and service features
- Tighten typography: larger hero headings, improved line-height and letter-spacing on body copy
- No changes to page content, copy, or structure

## Capabilities

### New Capabilities
- `logo-redesign`: New SVG logo faithful to the original brand image — flat-top hexagon, circuit-lock mark, stacked and horizontal header variants

### Modified Capabilities
- `site-shell`: Header uses new horizontal logo variant; footer uses icon-only variant; alternating section backgrounds applied as a global pattern
- `landing-page`: Hero gets subtle background texture; pillar icons replaced with proper SVGs; typography hierarchy tightened
- `services-page`: Section backgrounds alternated; feature icons improved
- `roi-comparison`: Section backgrounds alternated
- `faq-page`: Section backgrounds alternated
- `contact-page`: Section backgrounds alternated

## Impact

- `docs/assets/images/logo.svg` — replaced
- `docs/assets/images/logo-icon.svg` — new icon-only file for footer
- All 6 HTML pages — section background and typography classes updated
- No new dependencies — Heroicons/Lucide used as inline SVG, not as a package
