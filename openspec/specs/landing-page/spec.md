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
