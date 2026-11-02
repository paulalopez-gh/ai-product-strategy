# Data Flywheel Map

> Score each loop 1-5. Your weakest loop is where competitors attack first.
> The four loops below are the M2 starting point - adapt if your product has 2 or 6 loops instead of 4.

## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated retraining | 5/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | 3/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | 5/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | 2/5 |

### Correction Loop - 5/5
**What you capture today:** Customer Service Manager feedback, order approval decisions, field corrections, case reclassification, exception handling, validation errors, and human overrides during the review process.
**How it compounds:** Every correction becomes training data that improves future order classification, information extraction, validation accuracy, and automation rates. As more orders are processed, the AI requires less human intervention and handles more complex scenarios.

### Preference Loop - 3/5
**What you capture today:** Customer-specific ordering patterns, preferred attachment formats, recurring order types, account-level business rules, approval requirements, and communication preferences.
**How it compounds:** The system learns how each customer typically places orders and adapts validations and recommendations accordingly. Over time, it reduces friction, anticipates missing information, and increases straight-through processing rates for recurring customers.

### Domain Context Loop - 5/5
**What you capture today:** Historical OneForce cases, TRI2 order history, Edenred business rules, operational procedures, document templates, validation logic, approval workflows, customer account structures, and order execution outcomes.
**How it compounds:** Each processed order enriches Edenred's proprietary operational knowledge base. The AI continuously improves its understanding of order workflows, exception patterns, and business logic, creating a domain-specific advantage that external competitors cannot easily replicate.

### Network Loop - 2/5
**What you capture today:** Aggregated operational intelligence across customers, agents, order types, validation scenarios, and exception cases.
**How it compounds:** Insights generated from one customer's orders can improve models, validations, and automation strategies for others. While there is no direct user-to-user network effect, the shared learning across the ecosystem increases overall system performance and automation coverage over time.

**Total Flywheel Score: 15/20**
**Weakest Loop:** Data & Trust Loop – The system's ability to learn and improve depends on accurately classifying unstructured emails, extracting order information from multiple formats (text, Excel, PDF), and building enough user confidence to progressively increase automation levels.
**Fix for weakest loop:** Start with high-volume, low-complexity reload orders (70% of total volume) and implement a human-in-the-loop approval process. Capture every correction made by customer service managers as training data, establish confidence thresholds for automation, and progressively expand autonomy only when accuracy targets are consistently achieved. This creates a reinforcement cycle where each reviewed order improves the model, increases trust, and enables higher automation rates.

---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** Microsoft Copilot Studio / Salesforce Agentforce
**Vector:** Native AI agents that can classify emails, extract information from documents, orchestrate workflows, and trigger actions across enterprise applications.
**Time-to-threat:** 12-24 months
**% of value at risk:** 35%

### 2. Vertical Competitor
**Attacker:** Customer service automation platforms specialized in case management and order processing (e.g., Salesforce Service Cloud AI, Zendesk AI, ServiceNow AI Agents)
**Vector:** Industry-specific solutions that offer pre-built workflows for request classification, document processing, business rule validation, and operational automation.
**Time-to-threat:** 6-12 months
**% of value at risk:** 40%

### 3. Adjacent Expansion
**Attacker:** Enterprise automation platforms such as UiPath, Microsoft Power Platform, Automation Anywhere, or Celonis
**Vector:** Expansion from workflow automation into AI-driven operational agents capable of processing emails, extracting data, and executing transactions across multiple systems.
**Time-to-threat:** 18-36 months
**% of value at risk:** 25%

---

## 90-Day Encroachment Plan

*Your partner played the Big Tech attacker. What was their plan to kill you?*

**Attacker:** Microsoft Copilot / Salesforce Einstein launching a pre-built AI Operations Agent for customer order processing.
**Attack vector (target the weakest loop):** Attack the Data & Trust Loop by offering instant email classification, document extraction, and workflow automation bundled into existing enterprise licenses, reducing the perceived value of a custom Edenred solution.
**Weeks 1-4 - what they ship:** Out-of-the-box email and attachment understanding (PDF, Excel, text).
Salesforce-native case classification.
Generic order-processing agents.
No-code workflow builder for customer service teams.
**Weeks 5-8 - how they poach users:** Offer faster deployment and lower implementation costs.
Bundle capabilities into existing Microsoft or Salesforce contracts.
Demonstrate similar automation rates without custom development.
Position custom solutions as expensive and difficult to maintain.
**Weeks 9-12 - why users don't come back:** Customer service teams become dependent on the platform ecosystem.
New automations are created directly within the vendor platform.
Procurement prefers a standard enterprise solution over a bespoke product.
Users perceive AI capabilities as a commodity.
**Your defense:** The AI is not the product; the operational knowledge is.
Big Tech would commoditize the AI layer and bundle it into Salesforce/Microsoft platforms. Our defense is owning the workflow layer and continuously accumulating proprietary operational data, customer rules, and TRI2 process knowledge that become harder to replicate over time.
