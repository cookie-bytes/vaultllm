## ADDED Requirements

### Requirement: Alternating section backgrounds on services page
Content sections on `services.html` SHALL alternate between `bg-white` and `bg-gray-50`.

#### Scenario: Section backgrounds alternate
- **WHEN** `services.html` is rendered
- **THEN** consecutive content sections SHALL have alternating background colours

---

### Requirement: Heroicons for service feature icons
Feature/benefit icons on the services page SHALL use inline Heroicons SVG, not emoji or Unicode characters.

#### Scenario: Inline SVG icons in features list
- **WHEN** the services feature section is inspected
- **THEN** each feature item SHALL contain an inline `<svg>` Heroicons element
