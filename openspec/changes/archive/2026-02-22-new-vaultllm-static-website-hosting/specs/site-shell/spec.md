## ADDED Requirements

### Requirement: Base HTML template
Every page SHALL use a consistent HTML5 document structure including `<!DOCTYPE html>`, `lang="en-GB"`, UTF-8 charset, viewport meta tag, and a canonical `<link>` pointing to `https://vaultllm.uk/<page>`.

#### Scenario: Valid document structure
- **WHEN** any page is rendered in a browser
- **THEN** the document SHALL include `<!DOCTYPE html>`, `<html lang="en-GB">`, a `<meta charset="UTF-8">`, and a `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

#### Scenario: Canonical URL present
- **WHEN** any page is loaded
- **THEN** a `<link rel="canonical">` tag SHALL be present pointing to the correct `https://vaultllm.uk/` URL for that page

---

### Requirement: Tailwind CSS configuration
Every page SHALL load Tailwind CSS via the CDN Play script and include an inline `tailwind.config` block that extends the default theme with brand colour tokens and the Inter font family.

#### Scenario: Brand tokens available
- **WHEN** Tailwind renders utility classes
- **THEN** `bg-navy`, `text-navy`, `bg-walnut`, `text-walnut`, `bg-teal`, and `text-teal` SHALL resolve to `#0B1F3A`, `#A0785A`, and `#00C8C8` respectively

#### Scenario: Font family applied
- **WHEN** body text is rendered
- **THEN** the Inter typeface SHALL be used, loaded from `assets/fonts/` with no external DNS requests

---

### Requirement: Self-hosted Inter font
The Inter font SHALL be served from `docs/assets/fonts/` using `@font-face` declarations. No request SHALL be made to Google Fonts or any third-party font CDN.

#### Scenario: Font loads without external requests
- **WHEN** a page is loaded with network access blocked to third-party origins
- **THEN** body text SHALL still render in Inter (not a system fallback)

#### Scenario: Font file present
- **WHEN** the repository is checked out
- **THEN** `docs/assets/fonts/` SHALL contain at minimum the Inter Regular (400) and Semi-Bold (600) woff2 files

---

### Requirement: Company logo asset
The VaultLLM logo PNG SHALL be stored at `docs/assets/images/logo.png` and referenced by a relative path in every page header.

#### Scenario: Logo renders in navigation
- **WHEN** any page is loaded
- **THEN** the `<img>` tag for the logo SHALL have a valid `src` pointing to `assets/images/logo.png`, an `alt` of "VaultLLM", and explicit `width` and `height` attributes to prevent layout shift

---

### Requirement: Shared navigation
Every page SHALL include an identical `<header>` containing the VaultLLM logo and navigation links to all five pages. The current page's nav link SHALL be visually distinguished (e.g. underline or colour change).

#### Scenario: All nav links present
- **WHEN** any page is loaded
- **THEN** the header SHALL contain links to Home (`/`), Services (`/services.html`), ROI (`/roi.html`), FAQ (`/faq.html`), and Contact (`/contact.html`)

#### Scenario: Active link highlighted
- **WHEN** a user is on the Services page
- **THEN** the Services nav link SHALL have a distinct visual state compared to the other links

#### Scenario: Mobile navigation
- **WHEN** viewport width is below 768px
- **THEN** navigation links SHALL collapse into a hamburger menu toggled by Alpine.js

---

### Requirement: Shared footer
Every page SHALL include an identical `<footer>` containing the company name, tagline, copyright notice, and links to the Privacy Policy and any required legal text.

#### Scenario: Footer content present
- **WHEN** any page is loaded
- **THEN** the footer SHALL display "VaultLLM", the tagline "Your Intelligence. Locally Secured.", the current copyright year, and a link to the Privacy Policy page

---

### Requirement: CNAME file for custom domain
A `docs/CNAME` file SHALL exist containing exactly `vaultllm.uk` with no trailing whitespace or newline beyond the filename, to instruct GitHub Pages to serve the site at the custom domain.

#### Scenario: CNAME file content
- **WHEN** the `docs/CNAME` file is read
- **THEN** its sole content SHALL be the string `vaultllm.uk`

---

### Requirement: Responsive layout
All pages SHALL be fully usable on viewports from 320px (mobile) to 1440px (desktop) without horizontal scrolling.

#### Scenario: No horizontal scroll on mobile
- **WHEN** a page is viewed at 320px viewport width
- **THEN** no element SHALL cause horizontal overflow

#### Scenario: Readable at desktop widths
- **WHEN** a page is viewed at 1440px viewport width
- **THEN** content SHALL be constrained to a maximum width container (e.g. `max-w-6xl mx-auto`) and remain centred
