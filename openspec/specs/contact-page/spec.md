## ADDED Requirements

### Requirement: Static contact form via Formspree
The Contact page (`contact.html`) SHALL include a contact form that submits to Formspree via a `fetch` POST. The form SHALL NOT require a page reload on submission. Submissions SHALL be routed to `enquiries@vaultllm.uk`.

#### Scenario: Form submits without page reload
- **WHEN** a user completes and submits the form
- **THEN** the page SHALL remain loaded and display a success message in place of the form, without navigating to a new URL

#### Scenario: Success state shown after submission
- **WHEN** Formspree returns a successful response
- **THEN** the form SHALL be hidden and a confirmation message SHALL be displayed thanking the user and stating an expected response time

#### Scenario: Error state shown on failure
- **WHEN** Formspree returns an error response
- **THEN** an error message SHALL be displayed below the form advising the user to try again or email directly

---

### Requirement: Required form fields
The contact form SHALL collect the following fields: Full Name (required), Company Name (required), Email Address (required), Phone Number (optional), and Message (required).

#### Scenario: Required fields validated before submission
- **WHEN** a user attempts to submit the form with one or more required fields empty
- **THEN** the browser's native validation SHALL prevent submission and highlight the empty required field(s)

#### Scenario: Email field validated as email format
- **WHEN** a user enters a non-email string in the Email Address field
- **THEN** the browser's native validation SHALL prevent submission

---

### Requirement: Business contact information displayed
In addition to the form, the Contact page SHALL display the company's business email address (`enquiries@vaultllm.uk`) and state the expected response time for enquiries.

#### Scenario: Email address visible on page
- **WHEN** a user views the Contact page
- **THEN** `enquiries@vaultllm.uk` SHALL be visible as a `mailto:` hyperlink

#### Scenario: Response time stated
- **WHEN** a user views the Contact page
- **THEN** an expected response time SHALL be stated (e.g. "We typically respond within one business day")

---

### Requirement: No CAPTCHA or third-party verification widget
The contact form SHALL NOT include reCAPTCHA or any other third-party verification widget that would set cookies or make external network requests.

#### Scenario: No third-party verification widget present
- **WHEN** the contact page source is inspected
- **THEN** no reCAPTCHA, hCaptcha, or equivalent script tag SHALL be present

---

### Requirement: GDPR-compliant data notice
The Contact page SHALL include a brief, plain-English notice informing users how their submitted data will be used, in compliance with UK GDPR.

#### Scenario: Data use notice present
- **WHEN** a user views the contact form
- **THEN** a short notice SHALL be visible near the submit button stating that submitted information will be used only to respond to the enquiry and will not be shared with third parties

---

### Requirement: Alternating section backgrounds on contact page
Content sections on `contact.html` SHALL alternate between `bg-white` and `bg-gray-50`.

#### Scenario: Section backgrounds alternate
- **WHEN** `contact.html` is rendered
- **THEN** consecutive content sections SHALL have alternating background colours
