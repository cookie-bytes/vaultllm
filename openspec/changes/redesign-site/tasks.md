## 1. Logo SVG Assets

- [x] 1.1 Create `docs/assets/images/logo-icon.svg` — flat-top hexagon with circuit-lock mark, no wordmark or tagline, transparent background, renders at 28–32px
- [x] 1.2 Create `docs/assets/images/logo-horizontal.svg` — hexagon mark + "VaultLLM" wordmark inline (Vault white, LLM teal), no tagline, fits at h-10 in header
- [x] 1.3 Replace `docs/assets/images/logo.svg` with stacked variant — hexagon mark above "VaultLLM" wordmark above tagline "Your Intelligence. Locally Secured.", transparent background

## 2. Header & Footer Logo Swap (all 6 pages)

- [x] 2.1 Update header `<img src>` from `logo.svg` to `logo-horizontal.svg` in `index.html`
- [x] 2.2 Update header `<img src>` from `logo.svg` to `logo-horizontal.svg` in `services.html`
- [x] 2.3 Update header `<img src>` from `logo.svg` to `logo-horizontal.svg` in `roi.html`
- [x] 2.4 Update header `<img src>` from `logo.svg` to `logo-horizontal.svg` in `faq.html`
- [x] 2.5 Update header `<img src>` from `logo.svg` to `logo-horizontal.svg` in `contact.html`
- [x] 2.6 Update header `<img src>` from `logo.svg` to `logo-horizontal.svg` in `404.html`
- [x] 2.7 Update footer `<img>` to use `logo-icon.svg` at width/height 28 in all 6 pages

## 3. Hero Section — index.html

- [x] 3.1 Add CSS dot-grid texture to hero section via inline `background-image: radial-gradient(...)` style or Tailwind arbitrary value
- [x] 3.2 Update hero `<h1>` classes to `text-5xl md:text-6xl font-semibold leading-tight`
- [x] 3.3 Update hero sub-headline to `text-xl` or larger

## 4. Pillar & Feature Icons

- [x] 4.1 Replace the three Privacy First pillar icons in `index.html` with inline Heroicons SVG (`w-8 h-8 text-teal`)
- [x] 4.2 Replace feature/benefit icons in `services.html` with inline Heroicons SVG

## 5. Section Background Alternation

- [x] 5.1 Apply alternating `bg-white` / `bg-gray-50` to content sections in `index.html`
- [x] 5.2 Apply alternating `bg-white` / `bg-gray-50` to content sections in `services.html`
- [x] 5.3 Apply alternating `bg-white` / `bg-gray-50` to content sections in `roi.html`
- [x] 5.4 Apply alternating `bg-white` / `bg-gray-50` to content sections in `faq.html`
- [x] 5.5 Apply alternating `bg-white` / `bg-gray-50` to content sections in `contact.html`

## 6. QA

- [ ] 6.1 Verify all three logo SVGs render correctly on navy background with no white box artefact
- [ ] 6.2 Verify header logo fits cleanly in `h-16` header at all viewport widths
- [ ] 6.3 Verify section backgrounds alternate correctly on each page
- [ ] 6.4 Verify hero texture is visible on `index.html`
- [ ] 6.5 Verify Heroicons render at correct size and colour on `index.html` and `services.html`
