## Why

VaultLLM needs a public-facing marketing site to convert SME decision-makers (law firms, accountants, financial advisors) into leads and customers. Without a site, there is no credible web presence to support sales conversations or inbound discovery. GitHub Pages provides zero-cost static hosting, and the stack (Tailwind CSS + Alpine.js) keeps the site fast, secure, and maintainable without a build pipeline.

## What Changes

- **New**: Static marketing website published to GitHub Pages under the `vaultllm` repository
- **New**: Landing/hero page with Privacy First headline, value proposition, and CTA
- **New**: ROI comparison section (ChatGPT subscriptions vs. VaultLLM local hardware)
- **New**: Services page detailing the £199/month managed maintenance plan
- **New**: FAQ page addressing GDPR compliance, data residency, and air-gapped operation
- **New**: Contact page with a static-hosting-compatible form (Formspree or similar)
- **New**: Shared navigation, footer, and brand stylesheet (Deep Navy + Walnut palette)

## Capabilities

### New Capabilities

- `site-shell`: Base HTML template, shared navigation, footer, Tailwind CSS config, and Alpine.js setup used across all pages
- `landing-page`: Hero section, Privacy First messaging, social proof/trust badges, and primary CTA
- `roi-comparison`: Interactive or static table/calculator comparing ChatGPT per-seat subscription costs against VaultLLM hardware + maintenance pricing
- `services-page`: Detailed breakdown of the £199/month managed node plan, hardware specs (RTX 5090), and onboarding process
- `faq-page`: Accordion-style FAQ covering GDPR, data residency, air-gapped operation, and supported LLM models
- `contact-page`: Static contact form wired to Formspree (or equivalent), with business address and response-time expectations

### Modified Capabilities

*(none — this is a greenfield site)*

## Impact

- **New files**: `index.html`, `services.html`, `roi.html`, `faq.html`, `contact.html`, `assets/css/`, `assets/js/`
- **Hosting**: GitHub Pages (free tier), served from `main` branch or `docs/` folder
- **Dependencies**: Tailwind CSS (CDN or build), Alpine.js (CDN), Formspree (free tier for contact form)
- **No backend**: All pages are static HTML5 — no server, no database, no build step required for initial version
- **Aesthetic**: Deep Navy (`#0B1F3A`) primary, Walnut/Tan (`#A0785A`) accent, white body copy backgrounds — conservative professional look suitable for legal and financial sector clients
