# Three-Axis Vulnerability Diagnostic

## Product
AI-Native Order Processing Automation for OneForce & TRI2

**Product:** AI-Native Order Processing Automation for OneForce & TRI2
**Your Role:** Product Owner responsible for defining the vision, strategy, and delivery of an AI-native platform that automatically classifies customer requests, extracts order data from emails and attachments, creates orders in TRI2, and reduces Customer Service operational workload while maintaining human oversight during early deployment phases.

---

## Scores

### Contextual Moat — 4/5
*Workflow depth × switching cost. Would users leave in a weekend if a competitor showed up?*

**Score rationale:** The solution is deeply embedded into Edenred's operational workflow, integrating OneForce (Salesforce), TRI2, customer service processes, customer-specific business rules, internal APIs, and human review mechanisms. The AI must understand unstructured emails, attachments (Excel/PDF), order types, client permissions, and fulfillment rules before executing actions.

**Named attacker (from partner challenge):** Customer Service Operations Outsourcing Providers and Manual Back-Office Processing Teams

---

### Data Advantage — 4/5
*Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?*

**Score rationale:** The product benefits from a proprietary operational dataset that external AI providers do not have access to. Over time, the system learns from:

Historical customer order emails and attachments (free text, Excel, PDF).
OneForce case classifications and outcomes.
TRI2 order creation history.
Customer-specific ordering patterns and validation rules.
Human review decisions, corrections, and exceptions.
Confidence scores and audit logs generated during processing.

**Named attacker (from partner challenge):** Generic horizontal AI assistants (e.g., ChatGPT, Claude, Gemini) without access to Edenred operational systems and proprietary order-processing data.

---

### Platform Exposure — 2/5
*Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?*

**Score rationale:** Even if OpenAI, Microsoft Copilot, Google, or Salesforce release native email-to-order automation capabilities, they would still lack direct access to Edenred's proprietary workflows, business rules, customer-specific validations, OneForce case structure, and TRI2 order execution logic.

**Named attacker (from partner challenge):** Microsoft Copilot Studio / Salesforce Agentforce

---

## Top Vulnerability
<!-- One line: what's the single biggest strategic risk? --> The product's success depends on reliably interpreting highly variable customer emails and attachments. Low extraction accuracy or incorrect autonomous actions could reduce trust and slow adoption before automation reaches meaningful scale.

## Confidence Level
<!-- H / M / L — how confident are you in this bet after the diagnostic? --> MIDDLE · The business case is strong (3,000 requests/month, 70% order-related, repetitive workflows, clear cost-reduction opportunity), and the phased rollout with human oversight significantly reduces execution risk. However, confidence is not yet High because success depends on handling unstructured customer communications, customer-specific rules, attachment variability (Excel/PDF), and achieving sufficiently high accuracy before moving from copilot-assisted workflows to full automation.
