# Golden Dataset & Reliability Contract

## Golden Dataset Spec

| # | Input | Expected Output | Edge Case? | Judge Type |
|---|-------|----------------|-----------|-----------|
| 1 | Email requesting 10 Ticket Restaurant card reloads with all employee IDs attached in Excel | Order identified as Reload. Data extracted. Ready for TRI2 creation. | N | rule |
| 2 | Email requesting 2 duplicate cards due to loss | Duplicate Card Order. Customer identified. Ready for creation. | N | rule |
| 3 | Email requesting cancellation of 5 cards | Card Cancellation Order. Extract impacted cards. | N | rule |
| 4 | Email asking "Where is my last order?" | Classified as Inquiry, not Order. Route to Customer Service. | N | rule |
| 5 | Email containing marketing newsletter forwarded accidentally | Classified as Non-Order. Close case.| N | rule |
| 6 | Reload request with PDF attachment missing employee identifiers | Reload detected but flagged for missing mandatory data. Human review required. | Y | rule |
| 7 | Email containing multiple orders: reload + duplicate card request | Detect two orders and create two structured outputs. | Y | rule + LLM |
| 8 | Large account reload request exceeding normal order volume threshold | Correct extraction plus risk flag for approval workflow. | Y | rule |
| 9 | Free-text email with informal language: "Please top up everyone's cards like last month" | Detect ambiguity and request clarification. | Y | LLM |
| 10 | Email in Spanish with Excel attachment and mixed instructions | Extract correctly and map to structured order workflow. | N | rule + LLM |
| 11 | Email contains both a complaint and a hidden reload request | Correctly identify reload order and separate complaint. | Y | LLM |
| 12 | Excel attachment contains incorrect employee IDs and duplicate rows | Detect validation errors and stop automation. | Y | rule |
| 13 | High-value reload request sent by unauthorized sender | Reject automated execution and escalate to human review.| Y | rule |

**Adversarial rows included:** 3
**Dataset health**
- Total: 13
- Edge cases: 7 (53.8%)
- Judge mix: 69% rule / 15% LLM / 15% both

## Confidence UX Design

**Approach:** The AI shows confidence, extracted data, validation results, and reasons behind its decision. Automation level depends on confidence, order value, customer risk profile, and completeness of required information.

**Confident (>90%):** ✅ Green confidence badge: "Ready for Automation (96%)"

**Uncertain (50-90%):** 🟡 Amber confidence badge: "Review Recommended (74%)"

**Not confident (<50%):** 🔴 Red confidence badge: "Human Review Required (42%)"

**User control surface:** 

The system uses a tiered confidence model with explainability and human oversight. High-confidence orders can be processed automatically, medium-confidence orders require review or clarification, and low-confidence orders are blocked and escalated. Every user correction feeds the evaluation dataset, improving future automation rates and strengthening Edenred's proprietary operational knowledge base.

- Users adjust the confidence threshold
- Users see AI reasoning / drivers
- Users correct & override outputs
- Corrections feed back into the model / dataset

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | 92% | Weekly evaluation against the Golden Dataset (~150 curated customer order cases including reloads, new cards, duplicates, cancellations, inquiries, spam, and edge cases). Measure: Correct classification (Order vs Non-Order) · Correct order type identification · Correct data extraction · Correct routing decision · Correct TRI2 action recommendation | <88% → trigger gold-set audit |
| Hallucination rate | <0.5% | Weekly review of AI-generated outputs to detect: Invented employee IDs · Invented customer data · Invented card quantities · Invented validation results · Invented business-rule decisions. 
- Any field not present in the email, attachment, OneForce record, or enterprise source is considered a hallucination. | >2% → auto-rollback to last good model |
| Latency (p95) | <15 seconds | Monitor end-to-end workflow: Email analysis · Attachment processing · Validation execution · AI recommendation generation. 
- Measured through Azure AI Foundry monitoring and workflow telemetry. | >30 seconds for 15 minutes → page on-call |
| Drift velocity | <1% accuracy decay/month | Monthly comparison of: Golden Dataset performance · Production order outcomes · Human corrections
New customer formats · New attachment patterns. 
- Track degradation in classification and extraction accuracy. | >3% accuracy decay/month → trigger gold-set audit |

## HITL Architecture

**Trigger:** Human review is automatically triggered when: Confidence score <90% · Missing mandatory order information
High-value order · Large strategic account · Business-rule conflict detected · Unauthorized sender detected · Validation failure occurs.

**Reviewer:** Customer Service Manager (DAC Large Accounts Team) & Senior Customer Service Agent for business hours coverage

**Feedback loop:** - All reviewer actions are captured: Classification corrections · Data extraction corrections · Missing-field identification · Validation overrides · Order-type changes · Approval/rejection decisions. 

- Corrections are added to: Golden Dataset (weekly) · Evaluation benchmark (monthly) · Future model improvement cycles.
