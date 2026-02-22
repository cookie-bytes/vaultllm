## ADDED Requirements

### Requirement: Hero background texture
The hero section on `index.html` SHALL have a subtle dot-grid or radial-gradient texture applied via CSS on top of the navy background, adding visual depth without image assets.

#### Scenario: Texture visible on hero
- **WHEN** the landing page hero is rendered
- **THEN** a subtle pattern or gradient SHALL be visible on the navy background that is distinct from a flat colour fill

#### Scenario: Texture is CSS-only
- **WHEN** the page source is inspected
- **THEN** no `<img>` or external background-image URL SHALL be used for the hero texture

---

### Requirement: Heroicons for pillar icons
The three Privacy First pillar icons SHALL be inline Heroicons SVG elements (MIT licensed), not emoji or basic geometric shapes. Each icon SHALL be `w-8 h-8` in teal `#00C8C8` or using `text-teal`.

#### Scenario: Inline SVG icons present
- **WHEN** the pillar section is inspected
- **THEN** each pillar SHALL contain an `<svg>` element with a Heroicons path, not a Unicode character or emoji

---

### Requirement: Hero typography scale
The hero `<h1>` on `index.html` SHALL use `text-5xl md:text-6xl` with `leading-tight` and `font-semibold`. The sub-headline SHALL use `text-xl` or larger.

#### Scenario: Hero heading size at desktop
- **WHEN** the page is viewed at 1280px viewport width
- **THEN** the `<h1>` SHALL render at a minimum of 48px computed font size
