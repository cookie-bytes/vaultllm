## Requirements

### Requirement: Stacked SVG logo
A stacked SVG logo SHALL be created at `docs/assets/images/logo.svg` with a transparent background. It SHALL contain a flat-top hexagon mark with a circuit-lock icon, the "VaultLLM" wordmark ("Vault" in white, "LLM" in teal `#00C8C8`), and the tagline "Your Intelligence. Locally Secured." below. It SHALL render correctly on a navy `#0B1F3A` background.

#### Scenario: Logo renders on dark background
- **WHEN** `logo.svg` is displayed on a `#0B1F3A` background
- **THEN** the hexagon mark, wordmark, and tagline SHALL all be clearly visible with no white background artefacts

#### Scenario: Correct brand colours used
- **WHEN** the SVG source is inspected
- **THEN** the hexagon fill SHALL be `#0B1F3A`, the stroke and circuit elements SHALL be `#00C8C8`, "Vault" text SHALL be white, and "LLM" text SHALL be `#00C8C8`

---

### Requirement: Horizontal header logo variant
A horizontal SVG logo SHALL be created at `docs/assets/images/logo-horizontal.svg` containing only the hexagon mark and "VaultLLM" wordmark inline (no tagline). It SHALL fit comfortably in a 40px tall header at `h-10 w-auto` sizing.

#### Scenario: Logo fits in fixed header
- **WHEN** `logo-horizontal.svg` is rendered at 40px height
- **THEN** the full mark and wordmark SHALL be legible without clipping

#### Scenario: No tagline present
- **WHEN** the SVG source is inspected
- **THEN** no tagline text SHALL be present

---

### Requirement: Icon-only logo variant
An icon-only SVG SHALL be created at `docs/assets/images/logo-icon.svg` containing only the flat-top hexagon with circuit-lock mark, no wordmark or tagline. It SHALL be square-ish and usable at 28–32px sizes in the footer.

#### Scenario: Icon legible at small size
- **WHEN** `logo-icon.svg` is rendered at 28px × 28px
- **THEN** the hexagon outline and lock mark SHALL be clearly distinguishable
