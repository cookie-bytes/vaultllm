## ADDED Requirements

### Requirement: Hero section with Privacy First headline
The landing page (`index.html`) SHALL open with a full-width hero section containing a primary headline emphasising data privacy, a supporting sub-headline, and a primary CTA button linking to the Contact page.

#### Scenario: Hero headline visible above the fold
- **WHEN** the landing page loads on a 1280px desktop viewport
- **THEN** the primary headline, sub-headline, and CTA button SHALL all be visible without scrolling

#### Scenario: CTA button navigates to contact page
- **WHEN** a user clicks the primary CTA button in the hero
- **THEN** the browser SHALL navigate to `/contact.html`

#### Scenario: Hero renders on mobile
- **WHEN** the page is viewed at 375px viewport width
- **THEN** the headline text SHALL not overflow its container and the CTA button SHALL be full-width

---

### Requirement: Privacy First value proposition section
Below the hero, the page SHALL include a section clearly stating that all AI processing occurs on-premises, no data is sent to the cloud, and the service is GDPR-compliant by design.

#### Scenario: Three core privacy pillars displayed
- **WHEN** a user scrolls past the hero
- **THEN** the page SHALL display at minimum three distinct value proposition points covering: on-premises processing, zero cloud data transfer, and GDPR compliance

#### Scenario: No external data collection on page load
- **WHEN** the page is loaded with no user interaction
- **THEN** no tracking scripts, cookies, or third-party network requests (beyond CDN assets) SHALL be initiated

---

### Requirement: Social proof and trust indicators
The landing page SHALL include a trust section displaying indicators relevant to regulated UK SMEs, such as sector callouts (law firms, accountants, financial advisors) and any relevant compliance or security credentials.

#### Scenario: Target sectors named
- **WHEN** a user views the trust section
- **THEN** the page SHALL explicitly reference law firms, accountants, and/or financial advisors as target clients

---

### Requirement: ROI teaser with link to full comparison
The landing page SHALL include a concise ROI teaser — a headline figure or short comparison statement — with a link or CTA directing users to the full ROI comparison page.

#### Scenario: ROI link present
- **WHEN** a user views the ROI teaser section
- **THEN** a clearly labelled link or button SHALL navigate to `/roi.html`

---

### Requirement: Services summary with link to Services page
The landing page SHALL include a brief summary of the managed node service (hardware, maintenance, support) and a CTA linking to the full Services page.

#### Scenario: Services CTA present
- **WHEN** a user views the services summary section
- **THEN** a clearly labelled button or link SHALL navigate to `/services.html`

---

### Requirement: SEO meta tags
The landing page SHALL include a descriptive `<title>` tag, a `<meta name="description">` under 160 characters, and Open Graph tags (`og:title`, `og:description`, `og:url`, `og:image`) suitable for social sharing.

#### Scenario: Meta description present and within length
- **WHEN** the page source is inspected
- **THEN** a `<meta name="description">` tag SHALL be present with content no longer than 160 characters

#### Scenario: Open Graph tags present
- **WHEN** the page source is inspected
- **THEN** `og:title`, `og:description`, `og:url`, and `og:image` meta tags SHALL all be present

---

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
