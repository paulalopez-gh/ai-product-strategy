# AI-Native Order Processing Automation for OneForce & TRI2

> Edenred can reduce operational costs and order processing times by using AI agents to automate up to 85% of customer order requests received by email, starting with low-complexity, low-risk orders and progressively expanding toward full end-to-end automation.

---

## Strategy at a Glance

| Component | Module | Status | Key Artifact |
|-----------|--------|--------|-------------|
| **The Bet** | M1 | [x] | `01-the-bet/` |
| **The Moat** | M2 | [x] | `02-the-moat/` |
| **The Margin** | M3 | [x] | `03-the-margin/` |
| **The Contract** | M4 | [x] | `04-the-contract/` |
| **The Guardrails** | M5 | [x] | `05-the-guardrails/` |
| **The Pitch** | M6 | [x] | `06-the-pitch/` |

---

## The Bet (M1)

**What we're building, for whom, why now.**

- **Product:** AI-Native Order Processing Automation for OneForce & TRI2
- **AI Value Archetype:** Orchestrator
- **Vulnerability Scores:** _(add: Moat _/5 · Data _/5 · Platform _/5)_
- **Top Risk:** The product's success depends on reliably interpreting highly variable customer emails and attachments. Low extraction accuracy or incorrect autonomous actions could reduce trust and slow adoption before automation reaches meaningful scale.
- **Confidence:** _(add: H / M / L)_
- **Prototype:** https://lovable.dev/projects/49bc8fc3-21c0-40e6-bd91-8a35048758ab?magic_link=mc_a1e0530a-3a0d-4f28-a5f6-99634bba5c21
- **Kill Criteria:** The strongest kill signal would be evidence that the workflow complexity and exception rate are too high to achieve meaningful automation beyond a limited subset of orders.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:**
- **Weakest Loop:** Data & Trust Loop – The system's ability to learn and improve depends on accurately classifying unstructured emails, extracting order information from multiple formats (text, Excel, PDF), and building enough user confidence to progressively increase automation levels.
- **Top Encroachment Threat:** Microsoft Copilot Studio / Salesforce Agentforce
- **Encroachment Defense:** Start with high-volume, low-complexity reload orders (70% of total volume) and implement a human-in-the-loop approval process.…
- **Vendor Portability:** Partial

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?**

- **Gross Margin (current):** 100%
- **Gross Margin (AI-adjusted):** 85%
- **Pricing Model:** outcome-based
- **Pricing Today → Tomorrow:** Internal operational process. No direct customer pricing. Value is measured through cost reduction, faster order processing, and scalability of Customer Service operations. → Internal chargeback based on automated orders processed and operational savings generated.
- **Total AI COGS / unit:**
- **Cascading Strategy:** Triage: GPT-4o Mini (Azure OpenAI) or equivalent low-cost model; frontier: GPT-4o (Azure OpenAI) with Document Intelligence for complex emails and attachments; ratio 75% triage model / 25% frontier model
- **Net Margin Shift:** Significant positive margin expansion driven by operational cost reduction.
- **Break-even at:**

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** 92%
- **Golden Dataset:** 13 rows, 3 adversarial
- **Confidence UX:** The AI shows confidence, extracted data, validation results, and reasons behind its decision. Automation level depends on confidence, order value, customer risk profile, and completeness of required information.
- **HITL Architecture:** **Trigger:** Human review is automatically triggered when: Confidence score <90% · Missing mandatory order information High-value order · Large strategic account · Business-rule conflict detected · Unauthorized sender detected · Validation …
- **Failure Mode Coverage:**

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales, and what compounds.**

- **Compounding System:** | Loop | Input | Output | Compounds? | Status | |------|-------|--------|-----------|--------| | Recursive Learning | Customer Service Manager corrections, order approvals, extraction fixes, classification changes, excep…
- **Governance Posture:** This policy governs the AI-powered customer order automation workflow used to process customer requests received through OneForce and execute or prepare orders in TRI2.
- **Autonomy Boundaries:** Classify email as Order / Inquiry / Incident / Spam, auto. Generate customer clarification email draft, auto. Generate order summary and TRI2 recommendation, auto.…
- **Escalation Triggers:** 1. Confidence score <90%. 2. Missing mandatory order information. 3. Unauthorized sender detected. 4. High-value transaction exceeds threshold. 5. Strategic account customer. 6. Business-rule validation failure. 7.…
- **Audit Cadence:** Daily, Escalated cases, failed validations, low-confidence orders (<90%), unauthorized sender attempts, processing incidents. (DAC Large Accounts Manager).…
- **Shadow AI Audit (user-side):**
- **Agent Boundaries:** Email Triage Agent Can classify requests as Order, Inquiry, Incident, or Spam. Cannot create orders. Approval owner: DAC Manager.
- **Regulatory Exposure:** - GDPR (General Data Protection Regulation)

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):**
- **Horizon 2 (Next):**
- **Horizon 3 (Bet):**
- **Board Narrative:** **The case:**
- **Ask:** ## M1 Baseline vs. Now
- **Key Strategic Change:**

→ Details: [`06-the-pitch/`](06-the-pitch/)
