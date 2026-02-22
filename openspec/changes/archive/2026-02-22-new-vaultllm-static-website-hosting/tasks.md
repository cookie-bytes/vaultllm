## 1. Repository & Hosting Setup

- [x] 1.1 Create `docs/` directory at repository root to serve as the GitHub Pages source
- [x] 1.2 Create `docs/CNAME` containing exactly `vaultllm.uk`
- [ ] 1.3 Configure GitHub Pages in repository settings to serve from `docs/` on the `main` branch
- [ ] 1.4 Verify GitHub Pages picks up the CNAME and shows the custom domain as pending in settings

## 2. Assets — Fonts & Logo

- [x] 2.1 Download Inter Regular (400) and Semi-Bold (600) woff2 files from the official Inter repository
- [x] 2.2 Place font files at `docs/assets/fonts/inter-regular.woff2` and `docs/assets/fonts/inter-semibold.woff2`
- [x] 2.3 Copy `Gemini_Generated_Image_pa0ov5pa0ov5pa0o.png` from the project root to `docs/assets/images/logo.png`
- [x] 2.4 Create `docs/assets/css/fonts.css` with `@font-face` declarations for Inter 400 and 600 pointing to `../fonts/`

## 3. Site Shell — Shared HTML Structure

- [x] 3.1 Draft the shared `<header>` HTML with the VaultLLM logo (`<img src="assets/images/logo.png" alt="VaultLLM">`), nav links to all five pages, and a hamburger toggle `x-data` block for mobile
- [x] 3.2 Draft the shared `<footer>` HTML with company name, tagline "Your Intelligence. Locally Secured.", copyright year, and a Privacy Policy placeholder link
- [x] 3.3 Create the inline Tailwind config `<script>` block with brand tokens (`navy: #0B1F3A`, `walnut: #A0785A`, `teal: #00C8C8`) and Inter as the default sans font
- [x] 3.4 Confirm the Tailwind CDN Play script tag and Alpine.js CDN script tag load order is correct (config block → Tailwind CDN → Alpine.js CDN)

## 4. Landing Page (`index.html`)

- [x] 4.1 Create `docs/index.html` with full HTML5 boilerplate, canonical URL `https://vaultllm.uk/`, SEO `<title>`, and `<meta name="description">` under 160 chars
- [x] 4.2 Add Open Graph meta tags (`og:title`, `og:description`, `og:url`, `og:image`) to `index.html`
- [x] 4.3 Build the hero section with a Privacy First primary headline, supporting sub-headline, and a CTA button linking to `contact.html`
- [x] 4.4 Build the Privacy First value proposition section with three pillars: on-premises processing, zero cloud transfer, GDPR by design
- [x] 4.5 Build the trust/social proof section naming law firms, accountants, and financial advisors as target clients
- [x] 4.6 Build the ROI teaser section with a headline cost-saving figure and a "See the full comparison →" link to `roi.html`
- [x] 4.7 Build the services summary section with a one-paragraph description of the managed node offering and a CTA to `services.html`
- [x] 4.8 Add shared header and footer (duplicated HTML) with active state applied to the Home nav link
- [x] 4.9 Add `<!-- SHARED HEADER — update all pages when changing -->` comment above the header block

## 5. Services Page (`services.html`)

- [x] 5.1 Create `docs/services.html` with full boilerplate, canonical URL, and SEO meta tags
- [x] 5.2 Build the managed maintenance plan section showing "from £199/month" with a bulleted list of at least three inclusions (remote monitoring, model updates, support)
- [x] 5.3 Build the hardware specification section naming the RTX 5090, key VRAM/performance specs, and translate specs into business terms (e.g. "runs 70B parameter models locally")
- [x] 5.4 Build the onboarding process section as a numbered or visual step sequence (min. 4 steps: Discovery → Hardware dispatch → Installation → Handover)
- [x] 5.5 Build the supported LLM models section listing at least two models with one-line use-case descriptions each
- [x] 5.6 Add a prominent CTA button at the bottom linking to `contact.html`
- [x] 5.7 Add shared header and footer with active state on the Services nav link

## 6. ROI Comparison Page (`roi.html`)

- [x] 6.1 Create `docs/roi.html` with full boilerplate, canonical URL, and SEO meta tags
- [x] 6.2 Pre-calculate ChatGPT Team per-seat costs vs. VaultLLM (hardware one-off + from £199/month) for 5, 10, 20, and 50 seats at 12 and 36 months
- [x] 6.3 Build the static comparison table with seat-count rows and 12-month / 36-month columns for both options
- [x] 6.4 Add a pricing source note beneath the table stating the ChatGPT price used and noting prices are subject to change
- [x] 6.5 Add a breakeven callout box/highlight showing approximate breakeven month for 10 seats
- [x] 6.6 Add the Alpine.js seat-count enhancer input that recalculates estimated costs dynamically (progressive enhancement — static table must remain visible with JS off)
- [x] 6.7 Add a CTA at page bottom linking to `contact.html`
- [x] 6.8 Add shared header and footer with active state on the ROI nav link

## 7. FAQ Page (`faq.html`)

- [x] 7.1 Create `docs/faq.html` with full boilerplate, canonical URL, and SEO meta tags
- [x] 7.2 Write at least 8 question-answer pairs covering: GDPR compliance, data residency, air-gapped operation, supported models, hardware failure process, support contact & response times, onboarding timeline, and pricing
- [x] 7.3 Build the Alpine.js accordion component (`x-data`, `x-show`, `x-transition`) for single-open behaviour
- [x] 7.4 Ensure all answers are visible in plain HTML when JavaScript is disabled (no `hidden` attribute on answer elements — use Alpine's `x-show` only)
- [x] 7.5 Add a link to `services.html` within the supported models FAQ answer
- [x] 7.6 Add shared header and footer with active state on the FAQ nav link

## 8. Contact Page (`contact.html`)

- [x] 8.1 Create `docs/contact.html` with full boilerplate, canonical URL, and SEO meta tags
- [x] 8.2 Build the contact form with fields: Full Name (required), Company Name (required), Email Address (required, type="email"), Phone Number (optional), Message (required textarea)
- [x] 8.3 Wire up the Formspree endpoint (`action="https://formspree.io/f/<form-id>"`) with `method="POST"` and add the hidden `_replyto` field
- [x] 8.4 Implement Alpine.js `fetch`-based submission handler that prevents default form submission, POSTs to Formspree as JSON, and updates UI state
- [x] 8.5 Implement success state: hide form, show confirmation message with expected response time
- [x] 8.6 Implement error state: show inline error message advising retry or direct email
- [x] 8.7 Add `enquiries@vaultllm.uk` as a visible `mailto:` hyperlink on the page
- [x] 8.8 Add response time statement (e.g. "We typically respond within one business day")
- [x] 8.9 Add GDPR data use notice near the submit button (plain English, no sharing with third parties)
- [x] 8.10 Confirm no reCAPTCHA or third-party verification widget is present
- [x] 8.11 Add shared header and footer with active state on the Contact nav link

## 9. 404 Page

- [x] 9.1 Create `docs/404.html` with a friendly error message, the VaultLLM nav, and a "Return to homepage" link to `index.html`

## 10. Cross-Page QA & Polish

- [ ] 10.1 Verify all five pages render correctly at 320px, 768px, and 1280px viewport widths (no horizontal overflow)
- [ ] 10.2 Verify all nav links are correct and the active state highlights the correct page on each page
- [ ] 10.3 Verify the logo loads from `assets/images/logo.png` on all pages with correct `alt`, `width`, and `height` attributes
- [ ] 10.4 Verify Inter font loads from `assets/fonts/` with no external network requests (check DevTools Network tab)
- [ ] 10.5 Verify all canonical URLs match the page's `https://vaultllm.uk/` URL
- [ ] 10.6 Run the contact form end-to-end: submit a test enquiry and confirm it arrives at `enquiries@vaultllm.uk`
- [ ] 10.7 Test FAQ page with JavaScript disabled: confirm all answers are visible
- [ ] 10.8 Test ROI page with JavaScript disabled: confirm static table is visible and no broken input element is shown
- [ ] 10.9 Run Lighthouse on `index.html` — Performance score should be ≥ 80; flag if CDN Tailwind is the bottleneck
- [x] 10.10 Confirm `docs/CNAME` contains exactly `vaultllm.uk` with no extra whitespace
