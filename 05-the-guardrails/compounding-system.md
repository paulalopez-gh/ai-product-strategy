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
