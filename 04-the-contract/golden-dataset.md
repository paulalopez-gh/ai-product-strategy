# Golden Dataset & Reliability Contract

Golden Dataset, Module 4

Test cases:
  1. Edge: N · Judge: rule, IN: Email requesting 10 Ticket Restaurant card reloads with all employee IDs attached in Excel → OUT: Order identified as Reload. Data extracted. Ready for TRI2 creation.
  2. Edge: N · Judge: rule, IN: Email requesting 2 duplicate cards due to loss → OUT: Duplicate Card Order. Customer identified. Ready for creation.
  3. Edge: N · Judge: rule, IN: Email requesting cancellation of 5 cards → OUT: Card Cancellation Order. Extract impacted cards.
  4. Edge: N · Judge: rule, IN: Email asking "Where is my last order?" → OUT: Classified as Inquiry, not Order. Route to Customer Service.
  5. Edge: N · Judge: rule, IN: Email containing marketing newsletter forwarded accidentally → OUT: Classified as Non-Order. Close case.
  6. Edge: Y · Judge: rule, IN: Reload request with PDF attachment missing employee identifiers → OUT: Reload detected but flagged for missing mandatory data. Human review required.
  7. Edge: Y · Judge: both, IN: Email containing multiple orders: reload + duplicate card request → OUT: Detect two orders and create two structured outputs.
  8. Edge: Y · Judge: rule, IN: Large account reload request exceeding normal order volume threshold → OUT: Correct extraction plus risk flag for approval workflow.
  9. Edge: Y · Judge: LLM, IN: Free-text email with informal language: "Please top up everyone's cards like last month" → OUT: Detect ambiguity and request clarification.
  10. Edge: N · Judge: both, IN: Email in Spanish with Excel attachment and mixed instructions → OUT: Extract correctly and map to structured order workflow.
  11. Edge: Y · Judge: LLM, IN: Email contains both a complaint and a hidden reload request → OUT: Correctly identify reload order and separate complaint.
  12. Edge: Y · Judge: rule, IN: Excel attachment contains incorrect employee IDs and duplicate rows → OUT: Detect validation errors and stop automation.
  13. Edge: Y · Judge: rule, IN: High-value reload request sent by unauthorized sender → OUT: Reject automated execution and escalate to human review.

Dataset health
- Total: 13
- Edge cases: 7 (53.8%)
- Judge mix: 69% rule / 15% LLM / 15% both


## Golden Dataset Spec

| # | Input | Expected Output | Edge Case? | Judge Type |
|---|-------|----------------|-----------|-----------|
| 1 | | | Y/N | rule / LLM |
| 2 | | | Y/N | rule / LLM |
| 3 | | | Y/N | rule / LLM |
| 4 | | | Y/N | rule / LLM |
| 5 | | | Y/N | rule / LLM |

**Adversarial rows included:** __
**Coverage gaps identified by partner:**

## Confidence UX Design

**Approach:** show uncertainty / tiered confidence / human-in-loop trigger

**High confidence (>90%):**
**Medium confidence (70-90%):**
**Low confidence (<70%):**

**User control surface:**

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | | | |
| Hallucination rate | | | |
| Latency (p95) | | | |
| Drift velocity | | | |

## HITL Architecture
<!-- When does a human step in? What's the escalation path? -->

## Red-Team Findings
*What failure mode did your partner find that you missed?*
