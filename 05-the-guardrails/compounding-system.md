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
