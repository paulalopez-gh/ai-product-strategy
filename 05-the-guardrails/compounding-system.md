# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Customer Service Manager corrections, order approvals, extraction fixes, classification changes, exception handling decisions. | Updated golden dataset, improved prompts, new validation rules, higher automation accuracy. | Y | active |
| Cross-Domain Transfer | Order data across reloads, new cards, duplicates, cancellations, customer accounts, and document formats. | Shared operational knowledge and improved handling of new order types and customers. | Y | broken |
| Network Intelligence | Aggregated order patterns from 2,000-2,500 customer accounts. | Operational insights and benchmark patterns. | N | missing |

**Broken loop identified by partner:** Cross-Domain Transfer: operational knowledge and corrections are not yet systematically shared across all order types, customers, and workflows.

**Fix plan:** Create a centralized feedback pipeline that converts reviewer corrections, exception patterns, and business-rule updates into Golden Dataset rows, shared validation rules, and model improvements reviewed weekly.

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** Customer emails → OneForce cases → AI classification and extraction → DAC review → TRI2 execution → correction logs → Golden Dataset → model evaluation and workflow improvements.

**Where it silos:** Customer-specific exceptions, reviewer decisions, and operational know-how still reside within DAC teams and are not yet consistently transformed into reusable knowledge that benefits the entire system.

## Governance Policy

<!-- Governance Policy, Edenred Order Copilot v1.0 -->

**Scope:** This policy governs the AI-powered customer order automation workflow used to process customer requests received through OneForce and execute or prepare orders in TRI2.

The policy applies to: Email classification and triage. PDF and Excel attachment processing. Order data extraction. Customer and sender validation. Business-rule validation. Confidence scoring. Order creation recommendations. Autonomous and human-approved order execution. Human review and correction workflows. Audit logging and model evaluation processes. Excludes: This policy does not cover: Non-order customer service requests (complaints, support inquiries, commercial questions).
Internal reporting or analytics dashboards. Marketing communications. Independent AI tools not integrated into the order-processing workflow.

**Autonomy boundaries:** Classify email as Order / Inquiry / Incident / Spam, auto. Generate customer clarification email draft, auto. Generate order summary and TRI2 recommendation, auto. Approve low-value reload orders with confidence >95%, human approval required. Create order in TRI2 for standard customers, human approval required. Create order for large strategic accounts, human approval required. Execute high-value reload orders, human approval required. Override business validation rules, never auto. Execute orders from unauthorized senders, never auto. Create orders with missing mandatory information, never auto. Modify customer permissions or authorization matrix, never auto. Change business rules or approval thresholds, never auto. Execute orders when confidence <90%, never auto.

**Escalation triggers:** 1. Confidence score <90%. 2. Missing mandatory order information. 3. Unauthorized sender detected. 4. High-value transaction exceeds threshold. 5. Strategic account customer. 6. Business-rule validation failure. 7. Email and attachment data conflict. 8. New document format not in Golden Dataset. 9. Multiple valid interpretations detected. 10. Customer explicitly requests human support. 11. Attachment extraction failure. 12. Order affects permissions or account configuration.

**Audit cadence:** Daily, Escalated cases, failed validations, low-confidence orders (<90%), unauthorized sender attempts, processing incidents. (DAC Large Accounts Manager). Weekly, Golden Dataset performance, classification accuracy, extraction accuracy, human overrides, recurring correction patterns. (Product Owner (Paula Lopez) + DAC Large Accounts Manager). Monthly, Model drift, automation rate, false positives/false negatives, compliance audit, business-rule effectiveness, new edge cases. (Product Owner + Customer Service Director + AI Governance Lead).

**Regulatory exposure (EU AI Act / other):** - GDPR (General Data Protection Regulation)
- EU AI Act
- Edenred Information Security Policies
- Data Retention & Audit Requirements
- Customer Authorization & Financial Control Procedures
- Third-Party Vendor Governance (Azure AI Services). Risk tier: limited. Controls: - Human-in-the-loop approval for strategic accounts and high-value orders.
- Confidence thresholds before automation.
- Full audit trail of every AI recommendation and action.
- GDPR-compliant processing and data retention controls.
- Role-based access control for customer and order data.
- Sender authorization validation before order execution.
- No autonomous execution when mandatory information is missing.
- Golden Dataset evaluation before production releases.
- Model performance monitoring, drift detection, and escalation workflows.
- Azure-hosted AI services with EU data residency requirements..

## Agent Topology

Email Triage Agent
Can classify requests as Order, Inquiry, Incident, or Spam.
Cannot create orders.
Approval owner: DAC Manager.

Document Intelligence Agent
Can extract information from emails, PDFs, and Excel attachments.
Cannot modify extracted data once approved.
Approval owner: Human Reviewer.

Business Validation Agent
Can validate customer permissions, sender authorization, and business rules.
Cannot override validation failures.
Approval owner: DAC Manager.

Order Orchestration Agent
Can prepare TRI2 order payloads and recommend execution actions.
Cannot execute strategic-account or high-value orders autonomously.
Approval owner: Customer Service Manager.

Learning & Audit Agent
Can collect corrections, confidence scores, audit logs, and Golden Dataset updates.
Cannot modify business rules or production thresholds.
Approval owner: Product Owner.

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**


Shadow AI Audit (user-side), Module 5

## Discover, User-Side Workarounds
| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
Agents copy customer emails and Excel attachments into ChatGPT or Copilot to classify the request, identify the order type, and summarize the actions required. | source: User interview | signal: Workflow gap | freq: H | spend: $2000/mo | decision: Build
Customer Service Managers manually validate extracted information from emails and build internal Excel trackers to control approvals, exceptions, and special customer rules. | source: User interview | signal: Workflow gap | freq: H | spend: $3000/mo | decision: Build
Agents use AI tools to draft customer responses confirming orders, requesting missing information, or explaining validation issues. | source: Support ticket | signal: Trust gap | freq: M | spend: $500/mo | decision: Partner

## Pattern Assessment
- Workarounds found: 3
- Build candidates: 2
- Partner candidates: 1
- Ignore decisions: 0
- Adjacent spend: $5500/mo
- Dominant signal: Workflow gap

## Action Plan
### Build
1. Native email and attachment understanding.
The product will automatically classify incoming emails, identify order types, extract data from PDFs and Excel files, and prepare structured order information without requiring agents to use external AI tools.

2. Automated business-rule validation and exception handling.
Customer-specific validations, authorization checks, mandatory field verification, and approval workflows will be built directly into the product instead of relying on manual Excel trackers and operational knowledge.

3. Review and approval workspace.
Managers will review low-confidence cases, approve exceptions, and provide corrections directly within the product, feeding the Golden Dataset and improving future automation rates.

Sequencing:
Phase 1 → Email classification and extraction.
Phase 2 → Business validation and approval workflows.
Phase 3 → TRI2 order orchestration and autonomous execution for low-risk orders.

### Partner
Microsoft Copilot for email drafting and communication assistance.

Integration:
The AI agent generates structured order outcomes and recommended customer communications. Microsoft Copilot can be used to enhance message drafting, tone adjustment, translation, and productivity tasks while keeping operational decisions inside the Edenred platform.

Data Flow:
OneForce → AI Order Agent → Structured output → Copilot-assisted communication (optional).

### Ignore + Monitor
General-purpose AI usage for productivity tasks such as meeting notes, email rewriting, document summarization, translation, and brainstorming.

Rationale:
These activities are not part of the core order-processing workflow and do not create strategic differentiation for Edenred.

Signals to re-evaluate:
- More than 30% of DAC users adopting the same external AI workflow.
- Significant time spent outside OneForce and TRI2.
- Repeated requests for the same capability during user interviews.
- Operational risks caused by users moving customer data into unmanaged tools.

## Roadmap Brief
Based on your audit: 3 user-side workarounds discovered.
Decisions: 2 build · 1 partner · 0 ignore · 0 TBD.
Estimated adjacent spend: $5500/mo across surveyed users.
Dominant signal: Workflow gap.

Recommended next step: Workflow gaps dominate, your users are stitching your product into multi-step pipelines. Strongest near-term move is partner integrations with the AI tools they already chain in.

Sequence the Build column by frequency × strategic relevance. Confirm Partner candidates with the external tools' partnership teams. Re-run this audit each quarter, workarounds shift fast.

