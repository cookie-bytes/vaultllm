## ADDED Requirements

### Requirement: Accordion-style FAQ list
The FAQ page (`faq.html`) SHALL display questions and answers in an accordion pattern, where each question is clickable and toggles the visibility of its answer. The accordion SHALL be implemented with Alpine.js and SHALL degrade gracefully (answers visible) when JavaScript is disabled.

#### Scenario: Answer toggles on question click
- **WHEN** a user clicks a collapsed question
- **THEN** the answer SHALL expand and be visible

#### Scenario: Other answers collapse when one opens
- **WHEN** a user opens a second question while one is already open
- **THEN** the previously open answer SHALL collapse (single-open accordion behaviour)

#### Scenario: All answers visible with JS disabled
- **WHEN** JavaScript is disabled and the FAQ page is loaded
- **THEN** all answers SHALL be visible in a plain expanded list, with no hidden content

---

### Requirement: GDPR and data residency questions
The FAQ page SHALL include at minimum one question covering GDPR compliance and at minimum one question covering data residency, explaining that all data remains on the client's premises.

#### Scenario: GDPR question present
- **WHEN** a user reads the FAQ
- **THEN** at least one question SHALL explicitly address GDPR compliance and how VaultLLM's architecture supports it

#### Scenario: Data residency question present
- **WHEN** a user reads the FAQ
- **THEN** at least one question SHALL explicitly state that all data processing occurs on the client's own hardware and no data is transmitted externally

---

### Requirement: Air-gapped operation question
The FAQ page SHALL include a question explaining whether and how the VaultLLM node can operate in an air-gapped (no internet) environment.

#### Scenario: Air-gapped FAQ entry present
- **WHEN** a user views the FAQ
- **THEN** one question SHALL address air-gapped or offline operation capability

---

### Requirement: Supported LLM models question
The FAQ page SHALL include a question listing the LLM models supported and directing users to the Services page for full details.

#### Scenario: Models FAQ entry present
- **WHEN** a user views the FAQ
- **THEN** one question SHALL address which AI models are supported, with a link to `/services.html` for full details

---

### Requirement: Maintenance and support questions
The FAQ page SHALL include at minimum one question covering what happens if the hardware fails and one covering the support process.

#### Scenario: Hardware failure FAQ entry present
- **WHEN** a user views the FAQ
- **THEN** one question SHALL address the process if the node hardware fails or requires replacement

#### Scenario: Support process FAQ entry present
- **WHEN** a user views the FAQ
- **THEN** one question SHALL describe how to contact support and expected response times

---

### Requirement: Minimum FAQ count
The FAQ page SHALL contain at minimum eight questions covering the topics above plus general questions about VaultLLM and the onboarding process.

#### Scenario: At least eight questions present
- **WHEN** a user views the FAQ page
- **THEN** the accordion SHALL contain at least eight question-answer pairs
