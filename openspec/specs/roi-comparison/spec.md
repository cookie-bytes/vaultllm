## ADDED Requirements

### Requirement: Static ROI comparison table
The ROI page (`roi.html`) SHALL display a pre-calculated comparison table showing the cumulative cost of ChatGPT Team subscriptions versus VaultLLM hardware plus the monthly maintenance plan at seat counts of 5, 10, 20, and 50 users, projected over 12 and 36 months.

#### Scenario: Table rows cover required seat counts
- **WHEN** a user views the ROI table
- **THEN** rows for 5, 10, 20, and 50 seats SHALL be present for both the ChatGPT and VaultLLM columns

#### Scenario: Table is readable without JavaScript
- **WHEN** a user loads the page with JavaScript disabled
- **THEN** the full static comparison table SHALL still be visible and legible

#### Scenario: VaultLLM cost basis stated
- **WHEN** a user reads the table
- **THEN** the VaultLLM column SHALL be based on a one-time hardware cost plus "from £199/month" maintenance, with the pricing basis clearly labelled beneath the table

---

### Requirement: ChatGPT pricing basis disclosed
The page SHALL clearly state the ChatGPT per-seat price used in the comparison and the date it was accurate, so visitors can verify the figures.

#### Scenario: Pricing source note present
- **WHEN** a user views the comparison table
- **THEN** a note SHALL indicate the ChatGPT per-seat price used and state that prices are subject to change

---

### Requirement: Alpine.js seat-count enhancer (progressive enhancement)
The page MAY include an Alpine.js-powered numeric input that recalculates and displays estimated costs for a custom seat count entered by the user. This enhancement SHALL be additive — the static table MUST remain present regardless of JavaScript availability.

#### Scenario: Custom seat count updates displayed cost
- **WHEN** a user with JavaScript enabled enters a seat count in the input field
- **THEN** the estimated 12-month and 36-month costs for both ChatGPT and VaultLLM SHALL update without a page reload

#### Scenario: Static table unaffected when JS disabled
- **WHEN** JavaScript is disabled
- **THEN** the static comparison table SHALL display normally and no broken input element SHALL be visible

---

### Requirement: Breakeven callout
The page SHALL prominently display the approximate number of months at which VaultLLM becomes cheaper than an equivalent ChatGPT subscription for a representative seat count (e.g. 10 users).

#### Scenario: Breakeven figure visible
- **WHEN** a user views the ROI page
- **THEN** a callout or highlight box SHALL state the approximate breakeven point in months for at least one representative seat count

---

### Requirement: CTA to contact page
The ROI page SHALL include a CTA at the bottom of the page inviting the user to get in touch to discuss their specific requirements.

#### Scenario: CTA links to contact page
- **WHEN** a user reaches the bottom of the ROI page
- **THEN** a button or link SHALL navigate to `/contact.html`
