## Context

VaultLLM is a UK-based MSP selling private, self-hosted LLM nodes (RTX 5090-based hardware) to regulated SMEs — primarily law firms, accountants, and financial advisors. The primary concern of this audience is data privacy and GDPR compliance, which positions VaultLLM's "zero data leaves the premises" offering as a direct alternative to cloud-based AI tools like ChatGPT Enterprise.

The site must be trusted on first impression by cautious, risk-averse buyers. It is greenfield: no existing codebase, no CMS, no backend. The repo already exists at `github.com/vaultllm/vaultllm` and GitHub Pages will serve the site from the `main` branch root or `docs/` folder.

## Goals / Non-Goals

**Goals:**
- Deliver a fast, credible marketing site that converts SME decision-makers into enquiries
- Communicate the "Privacy First / data never leaves your premises" value proposition clearly
- Make the £199/month maintenance plan and hardware offering legible and trustworthy
- Pass GDPR credibility checks (no third-party tracking by default, no cookies banner required unless analytics are added later)
- Work without any build step — deployable by committing HTML files directly to GitHub

**Non-Goals:**
- CMS or content editing by non-developers (out of scope for v1)
- Blog, case studies, or resource hub (future work)
- User accounts, authentication, or any server-side logic
- Custom domain SSL setup (GitHub Pages handles this automatically)
- Analytics (deferred — adding GA/Plausible later avoids needing a cookie consent banner now)

## Decisions

### D1: No build step — CDN-loaded Tailwind and Alpine.js

**Decision**: Use Tailwind CSS via the CDN Play script (`cdn.tailwindcss.com`) and Alpine.js via CDN (`cdn.jsdelivr.net/npm/alpinejs`). No npm, no PostCSS, no bundler.

**Rationale**: The target maintainer is a small team or solo operator. A build pipeline adds friction (Node version, lock files, CI config) that outweighs the benefits for a 5-page static site. CDN approach ships on day one with `git push`.

**Alternative considered**: Tailwind CLI build with purging. Better for production file size, but introduces a `package.json` dependency and a build step before every deploy. Revisit if Lighthouse scores degrade noticeably.

**Caveat**: CDN Tailwind does not purge unused classes — total CSS size will be ~350KB. Acceptable for marketing pages; monitor with Lighthouse.

---

### D2: GitHub Pages served from `docs/` subdirectory

**Decision**: Store all site files under `docs/` in the repository root. GitHub Pages is configured to serve from `docs/` on `main`.

**Rationale**: Keeps site source separate from any future tooling, scripts, or OpenSpec artifacts that live in the repo root. Easier to review PRs when site changes are isolated to one directory.

**Alternative considered**: Serving from root (`/`). Simpler, but conflates site files with project metadata files, making the repo harder to navigate.

---

### D3: Formspree for contact form

**Decision**: Use [Formspree](https://formspree.io) free tier for the contact form. Form submits via a `fetch` POST to `https://formspree.io/f/<id>` and Alpine.js handles the success/error state.

**Rationale**: No backend required. Formspree's free tier allows 50 submissions/month — sufficient for a low-volume B2B enquiry form. Submissions are emailed directly to the VaultLLM address.

**Alternative considered**: Netlify Forms — requires hosting on Netlify, not GitHub Pages. Getform.io — similar to Formspree but less established. Static `mailto:` link — poor UX, exposes email address to scrapers.

**GDPR note**: Formspree is GDPR-compliant and processes data under standard contractual clauses. No cookie is set by Formspree during form submission.

---

### D4: Inline Tailwind config block for custom brand tokens

**Decision**: Each HTML page includes a `<script>` block that extends the Tailwind config with brand colours and fonts before the CDN script runs.

**Rationale**: Avoids a separate CSS file while keeping the Deep Navy / Walnut palette as named tokens (`navy`, `walnut`) usable in utility classes like `bg-navy` and `text-walnut`.

```html
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          navy:  '#0B1F3A',
          walnut: '#A0785A',
        },
        fontFamily: {
          sans: ['Inter', 'system-ui', 'sans-serif'],
        },
      }
    }
  }
</script>
```

---

### D5: Page structure — shared header/footer via Alpine.js `x-data` + `fetch`, or duplicated HTML

**Decision**: Duplicate the `<header>` and `<footer>` HTML across all five pages rather than dynamically loading a shared partial.

**Rationale**: Fetching partials with Alpine.js introduces async render flicker (header appearing after page load). With only 5 pages, duplication is a trivial maintenance burden and eliminates complexity. If the site grows beyond ~10 pages, introduce a lightweight SSG (Eleventy or Astro) at that point.

**Alternative considered**: Alpine.js `x-html` with `fetch` to load `_header.html`. Works but causes layout shift on slow connections. Web Components for header/footer — overkill for this project.

---

### D6: Company logo — self-hosted PNG, renamed for clarity

**Decision**: Use the PNG file from the project root as the company logo. Rename it to `logo.png` and place it at `docs/assets/images/logo.png`. Reference it with a relative path in all pages.

**Source file**: `Gemini_Generated_Image_pa0ov5pa0ov5pa0o.png` (project root)

**Logo details**:
- Hexagonal circuit-lock mark in teal/cyan on deep navy
- Wordmark: "VaultLLM"
- Tagline: "Your Intelligence. Locally Secured."

**Brand palette note**: The logo introduces a teal accent (`~#00C8C8`) alongside Deep Navy and Walnut. Update the Tailwind config to include this as a named token (`teal`) for use in CTAs, icon highlights, and hover states where the logo's colour needs to be echoed in the UI.

```html
colors: {
  navy:   '#0B1F3A',
  walnut: '#A0785A',
  teal:   '#00C8C8',
}
```

**Alternative considered**: SVG format for infinite scaling. The provided asset is PNG — acceptable for a logo at fixed nav/header sizes. Convert to SVG in a future polish pass if needed.

---

### D7: ROI comparison — static table, not a live calculator

**Decision**: The ROI section on the landing page uses a static pre-calculated table comparing ChatGPT Team pricing against VaultLLM hardware + maintenance costs at 5, 10, 20, and 50 seats. An Alpine.js seat-count input can optionally enhance this with live interpolation.

**Rationale**: A static table is immediately legible and works without JavaScript. The Alpine enhancement is additive — users who disable JS still see the comparison. Keeps the page fully crawlable.

---

## Risks / Trade-offs

| Risk | Mitigation |
|---|---|
| CDN Tailwind causes slow initial load on poor connections | The CDN script is ~350KB but cached after first visit. Add `<link rel="preconnect">` and `loading="lazy"` on images. Revisit with build step if Lighthouse performance < 80. |
| Formspree free tier limit (50 submissions/month) | Monitor via Formspree dashboard. Upgrade to paid tier (£8/mo) if volume increases. |
| Duplicate header/footer becomes stale across pages | Acceptable for v1. Document the duplication explicitly in a `<!-- SHARED HEADER — update all pages when changing -->` comment. |
| GitHub Pages has no server-side redirects | Use a `404.html` page that redirects to `index.html` for single-page navigation resilience. Not needed for a multi-page static site, but useful if canonical URLs change. |
| No analytics means no conversion data | Acceptable for launch. Add Plausible (privacy-first, no cookie banner needed) in a follow-up change. |

## Open Questions

- **Custom domain**: Resolved — site will be served at `vaultllm.uk`. Set canonical URLs to `https://vaultllm.uk`, add `docs/CNAME` containing `vaultllm.uk`, and point the domain's DNS A records to GitHub Pages IPs.
- **Pricing certainty**: Resolved — price is not yet fixed. Use "from £199/month" throughout the site to avoid edits when the price is finalised.
- **Formspree account**: Resolved — account is owned by VaultLLM. Form submissions route to `enquiries@vaultllm.uk`.
- **Inter font**: Resolved — Inter will be self-hosted under `docs/assets/fonts/`. No Google Fonts DNS lookup, no third-party data transfer.
