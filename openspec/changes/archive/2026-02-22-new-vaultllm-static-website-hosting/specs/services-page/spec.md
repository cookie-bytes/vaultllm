## ADDED Requirements

### Requirement: Managed maintenance plan details
The Services page (`services.html`) SHALL clearly describe the managed maintenance plan, including the "from £199/month" pricing, what is covered (hardware monitoring, model updates, remote support), and what is not covered.

#### Scenario: Pricing displayed with "from" qualifier
- **WHEN** a user views the Services page
- **THEN** the maintenance plan price SHALL be shown as "from £199/month" and SHALL NOT display a fixed price without the qualifier

#### Scenario: Plan inclusions listed
- **WHEN** a user reads the plan description
- **THEN** the page SHALL list at minimum three specific inclusions (e.g. remote monitoring, firmware/model updates, telephone/email support)

---

### Requirement: Hardware specification section
The Services page SHALL include a section detailing the hardware provided, specifically the RTX 5090-based node, including key specifications relevant to AI inference (VRAM, supported model sizes, typical inference speed).

#### Scenario: RTX 5090 named
- **WHEN** a user views the hardware section
- **THEN** the GPU model (NVIDIA RTX 5090 or equivalent) SHALL be explicitly named

#### Scenario: Capability context provided
- **WHEN** a user reads the hardware specs
- **THEN** the page SHALL translate the hardware specs into business-relevant terms (e.g. "runs 70B parameter models locally" or "processes documents without internet access")

---

### Requirement: Onboarding process section
The Services page SHALL describe the onboarding steps from initial enquiry to a live node, giving prospects a clear picture of what to expect.

#### Scenario: Onboarding steps present
- **WHEN** a user reads the onboarding section
- **THEN** at least three sequential steps SHALL be described (e.g. Discovery call → Hardware dispatch → Installation & configuration → Handover)

---

### Requirement: Supported LLM models section
The Services page SHALL list the LLM models supported or recommended on the VaultLLM node, with a brief description of each model's strengths relevant to the target audience (e.g. document summarisation, contract review, data extraction).

#### Scenario: At least two models listed
- **WHEN** a user views the supported models section
- **THEN** at least two LLM models SHALL be listed with a one-line use-case description each

---

### Requirement: CTA to contact page
The Services page SHALL include a prominent CTA inviting the user to book a discovery call or request a quote, linking to `/contact.html`.

#### Scenario: CTA present and linked
- **WHEN** a user views the Services page
- **THEN** at least one CTA button or link SHALL be present linking to `/contact.html`
