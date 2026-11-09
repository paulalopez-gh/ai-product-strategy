# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Customer Service Manager corrections, order approvals, extraction fixes, classification changes, exception handling decisions. | Updated golden dataset, improved prompts, new validation rules, higher automation accuracy. | Y | active |
| Cross-Domain Transfer | Order data across reloads, new cards, duplicates, cancellations, customer accounts, and document formats. | Shared operational knowledge and improved handling of new order types and customers. | Y | broken |
| Network Intelligence | Aggregated order patterns from 2,000-2,500 customer accounts. | Operational insights and benchmark patterns. | N | missing |

**Broken loop identified by partner:** Cross-Domain Transfer: corrections and operational knowledge captured in one order type or customer segment are not yet systematically reused across all order categories, customers, and workflows.
**Fix plan:** Create a centralized operational knowledge layer that captures business rules, exception patterns, validation logic, and reviewer corrections from all order types. Establish a weekly review process where recurring corrections are converted into shared validation rules, Golden Dataset additions, and confidence model updates.

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** Customer emails and attachments → OneForce case creation → AI classification and extraction → DAC Manager review → TRI2 execution → correction logs → Golden Dataset → model evaluation and workflow improvements.

**Where it silos:** Knowledge about exceptions, customer-specific rules, and reviewer decisions still resides largely within DAC processes and individual reviewers. Without a structured mechanism to transform those corrections into reusable rules, Golden Dataset updates, and shared validation logic, part of the operational knowledge remains siloed and does not compound across the system.

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

## Governance Policy

**Scope:**
**Autonomy boundaries:**
**Escalation triggers:**
**Audit cadence:**
**Regulatory exposure (EU AI Act / other):**

## Agent Topology
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**
