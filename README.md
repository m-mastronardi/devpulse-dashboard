**Maria Mastronardi**\
Web and mobile Systems\
September 20 2026

## Section 1: The less than equal 4 click user journey

- **Starting State:** user lands on the DevPluse homepage. On the top
  above the fold they see the sticky header with the navigation, the
  core value proposition, and the "Deploy Free Cluster CTA (Story 1).
  While scrolling, they scan the Infrastructure Feature Grid (Story
  2).
- **Action 1:** User clicks the `#pricing` landmark navigation link in
  the sticky `<nav>` to jump to the Compute Tier Comparison section
  (Story 3).
- **Action 2:** User inspects the three tier cards and clicks the CTA
  inside the "Pro Cluster" card, which anchors down the combined
  Workload Estimator / Registration form.
- **Action 3:** User enters their node count and log throughout into
  the numerical constrained inputs, and fills in the required email
  and company fields of the same form (story 4 + story 5 combined
  similar to ApexPay reference)
- **Action: 4** User clicks the primary dispatch CTA ("Generate API
  Keys") to submit the form.
- **Terminal State:** Native/visual feedback confirms receipt, and
  invalid fields are blocked and highlighted by the browsers built in
  validation UI (`:invalid` state) before submission is possible, and
  on success an inline confirmation message (ex: "Message

**Total interaction count: 4 actions**, mapping to stories 1, 3, 4, and
5, with story 2 consumed passively during the scroll from Starting State
to Action 1.

## Section 2: Don Norman Usability and Constraint Audit

---

Norman Principle UI Component / Feature Specific HTML Element Used
Concept

---

Signifier Primary Action Button `<a href="#register" class="btn-primary">` "Deploy Free Cluster" element.
(above the fold) Signifies it is clickable and where it will take the user.

Signifier Recommended Tier `<article>` carries `aria-current="true"` and contains `<span class="badge">`
Indicator "Most Popular" element inside its heading area. Help to highlight a passage
as relevant.

Physical/System Workload Estimator: `<input type="number" id="node-count" min="1" max="500" step="1" required>`
Constraint Node Count Min, max, and step help to enforce valid numeric range and increment
natively.

Physical/System Operator Contact Field `<input type="email" id="email" required>` The required attribute prevents
Constraint (Email) the browser from allowing the form to be submitted with an empty field.

Feedback Loop Form Submission / Live Two native mechanisms: 1) the browser's built-in `:invalid`/`:valid`
Anchors pseudo-class styling and validation bubble appears immediately if constrained
fields are violated on submit attempt; 2) once successfully dispatched, an
`<output>` or `<p role="status" aria-live="polite">` element updates in place
to visually confirm the system accepted the action, without requiring a full
page reload.

---

## Section 3: Layout Tree

- **Body**
  - **Header**
    - **Div**
      - A href = "/" logo
    - **Nav**
      - A href = "#features"
      - A href = "#pricing"
      - A href = "#register"
      - A href = "\# register" class = "btn-primary" "Deploy
        Free Cluster"
  - **Main**
    - **Section (id = "hero")**
      - H1 (primary value Proposition
      - P (support lead text)
      - Div (CTA)
        - A "Deploy Free Cluster"
        - A "Read Documentation"
    - **Section (id = "features")**
      - H2 "Engineered for Platform Reliability"
      - Div (features grid, for containerization)
        - Article (latency tracking)
          - H3
          - P
        - Article (logo aggregation)
          - H3
          - P
        - Article (auto remediation)
          - H3
          - P
    - **Section (id = "pricing")**
      - H2 ("Compute tiers)
      - Div (micro-grouping: pricing grid)
        - Article (Developer Tier)
          - H3 "Developer"
          - Ul (feature list)
            - Li
            - Li
          - A href = "#register" "section Pro Cluster"
        - Article (Pro-Cluster Tier, aria-current = "true",
          elevated)
          - Span (Most Popular)
          - H3 (Pro Cluster)
          - Ul
            - Li
            - Li
          - A href = "#register", "Contact Sales"
    - **Section (id = "register", combined Workload Estimator and
      API provisioning Lead Capture)**
      - H2 (Estimate your Workload and Request Sandbox Access)
      - Form
        - Fieldset (Work load Estimation)
          - Legend (Workload Estimator)
          - Label (for = "node-count") (type = "number", min
            = "1", max = "500", step = "1", required)
          - Label (for = "log-throughout") + input (type =
            "number", min = "100", max = "100000", step =
            "100", required)
        - Fieldset (API Provisioning Details)
          - Legend (Request Sandbox Details)
          - Label (for = "email") + input (type = "email",
            required)
          - Label (for = "companyl") + input (type = "text",
            required)
          - Label (for = "use-case") + textarea
        - Button (type = "submit", "Generate APIn Keys"
  - **Footer**
    - P (Copyright 2026 DevPulse inc. all rights reserved)
    - Nav (landmark: footer links)
      - Ul
        - Li
        - Li
        - Li
