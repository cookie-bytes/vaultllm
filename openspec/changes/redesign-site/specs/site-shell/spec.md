## MODIFIED Requirements

### Requirement: Company logo asset
The VaultLLM logo SHALL be provided as three SVG variants: `logo-horizontal.svg` (header use), `logo.svg` (stacked, hero/footer contexts), and `logo-icon.svg` (icon only, footer). The PNG file `logo.png` is superseded. Every page header SHALL reference `logo-horizontal.svg`.

#### Scenario: Header logo uses horizontal SVG
- **WHEN** any page is loaded
- **THEN** the `<img>` tag in the header SHALL have `src` pointing to `assets/images/logo-horizontal.svg`, an `alt` of "VaultLLM", and class `h-10 w-auto block`

#### Scenario: Footer uses icon-only SVG
- **WHEN** any page is loaded
- **THEN** the `<img>` tag in the footer SHALL reference `assets/images/logo-icon.svg` at 28–32px

#### Scenario: No white background artefact
- **WHEN** any page header is rendered on the navy background
- **THEN** the logo SHALL display without a white box or background colour around it

## ADDED Requirements

### Requirement: Alternating section backgrounds
Content sections (not hero, not CTA) across all pages SHALL alternate between `bg-white` and `bg-gray-50` to provide visual separation without imagery.

#### Scenario: Adjacent sections have different backgrounds
- **WHEN** two consecutive content sections are rendered on any page
- **THEN** they SHALL NOT both have the same background colour class
