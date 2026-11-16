# Three-Horizon Roadmap & Board Pitch

## Roadmap

### Horizon 1 — Now (0-3 months)
*Quick wins. Ship with existing capabilities.* 

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
|Build AI copilot for email classification and order extraction | >90% classification accuracy| H |
|Create Golden Dataset and Human-in-the-Loop workflow |100% reviewed corrections captured | H |
|Pilot low-risk reload orders with DAC Manager | 15% reduction in processing time | M |

### Horizon 2 — Next (3-9 months)
*Bets. Requires new capabilities or integrations.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
|Integrate AI agent with TRI2 for order creation | 70% autonomous processing of eligible orders| H |
|Deploy customer-specific validation and approval rules | <5% exception rate on automated orders| H |
|Expand automation to new cards, duplicates, and cancellations | 85% of low-complexity orders automated | M |

### Horizon 3 — Bet (9-18 months)
*Moonshots. High uncertainty, high potential.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
|Fully autonomous AI Operations Agent across all order types |85%+ end-to-end automation | L |
|Cross-product automation (Restaurant, Mobility, Nursery, future benefits) | 25% operational cost reduction |L |

## Board Pitch

**Thesis (1 sentence):** Edenred can transform customer order processing from a manual workflow into an AI-native operation, reducing costs and processing times while continuously improving through proprietary operational data.

**The case:**
1. Why now: ~3,000 monthly requests, repetitive workflows, mature AI capabilities, and a clear operational cost-reduction opportunity.
2. What's defensible: Deep integration with OneForce and TRI2, proprietary business rules, customer-specific patterns, and a growing feedback loop from DAC corrections.
3. The economics: AI processing costs are a fraction of current manual processing costs, enabling scalable automation with positive unit economics.

**The risks:**
1. Trust / failure modes: Incorrect extraction or order creation could reduce user trust and slow adoption.
2. Scale / governance: Maintaining quality, compliance, and auditability while increasing automation.
3. Competitive: Microsoft Copilot, Salesforce Agentforce, and enterprise automation platforms could commoditize parts of the AI layer.

**The ask:** Fund and support a phased rollout starting with low-risk reload orders, while building the feedback loops, governance, and operational knowledge needed to reach 85% automation.

## M1 Baseline vs. Now
*Your 3-sentence AI strategy from Module 1 vs. what you'd say now:*

**M1 baseline:** Use AI to help Customer Service process customer orders faster.

**Now:** Build an AI-native operations agent that understands customer emails, validates business rules, creates orders in TRI2, learns from human feedback, and progressively automates Edenred's order-processing workflow at scale.

## AI Product Strategy Evaluation
# AI-Native Order Processing Automation for OneForce & TRI2

---

## Bet Validation, Score: 4/5

### Strengths
- Strong user and operational signal: ~3,000 requests/month with repetitive workflows.
- Clear business pain point and cost-reduction opportunity.
- Explicit and falsifiable kill criteria.
- Phased rollout with Human-in-the-Loop reduces execution risk.

### Gaps
- Limited evidence on current processing costs, exception rates, and review effort.
- Confidence level remains Medium rather than High due to unvalidated assumptions.
- ROI assumptions are not yet supported by pilot data.

### Recommendation
Run a 4–6 week pilot focused on reload orders and measure:
- Classification accuracy
- Extraction accuracy
- Exception rate
- Human review effort
- Cost-per-order reduction

---

## Capability Assessment, Score: 4/5

### Strengths
- Required technical capabilities are clearly identified:
  - Email understanding
  - Document extraction
  - Business-rule validation
  - TRI2 integration
  - Confidence scoring
  - Audit logging
  - Human review workflows
- Strong understanding of operational requirements.

### Gaps
- Evaluation pipelines are not yet mature.
- Golden Dataset maintenance process is not fully defined.
- TRI2 integration complexity is still an assumption.
- MLOps and governance capabilities need further development.

### Recommendation
Treat evaluation infrastructure as a product feature and build:
- Golden Dataset management
- Drift monitoring
- Evaluation pipelines
- Feedback capture mechanisms

before increasing autonomy levels.

---

## Impact Analysis, Score: 5/5

### Strengths
- Directly tied to operational cost reduction.
- Large enough volume to generate meaningful savings.
- Potential for step-change improvement rather than incremental optimization.
- Benefits compound through automation and learning.

### Gaps
- Alternative investment opportunities have not been assessed.
- Comparison with traditional RPA approaches is missing.

### Recommendation
Build a quantified business case including:
- Current cost per order
- AI-assisted cost per order
- Fully automated cost per order
- Expected annual savings at 60%, 75%, and 85% automation levels

---

## Defensibility Check, Score: 4/5

### Strengths
- Strong workflow depth.
- Deep integration with:
  - OneForce
  - TRI2
  - Customer-specific business rules
  - Approval processes
- Real learning loops through operational feedback.

### Gaps
- Data flywheel is still emerging rather than fully established.
- Microsoft Copilot Studio and Salesforce Agentforce remain credible threats.
- Proprietary data advantage is still being built.

### Recommendation
Ensure every correction, override, and exception becomes structured data that feeds:
- Golden Dataset
- Business rules
- Evaluation framework
- Model improvement process

---

## Pricing Alignment, Score: 3.5/5

### Strengths
- Outcome-based pricing aligns with delivered value.
- Operational cost reduction is the correct economic lens.
- AI costs appear significantly lower than manual processing costs.

### Gaps
- No external willingness-to-pay signal exists.
- Break-even point is undefined.
- Margin assumptions remain largely theoretical.

### Recommendation
Focus less on pricing models and more on proving:
- Cost per automated order
- Cost per reviewed order
- Operational savings generated

These metrics should serve as the primary economic proof points.

---

## Trust & Reliability, Score: 4/5

### Strengths
- Strong reliability framework:
  - Golden Dataset
  - Confidence UX
  - Reliability targets
  - HITL architecture
  - Escalation paths
  - Hallucination controls
- Clear confidence-based workflow design.

### Gaps
- Golden Dataset is too small (13 examples).
- Failure mode coverage remains limited.
- Production-grade validation has not yet occurred.

### Recommendation
Expand the Golden Dataset to at least 100–150 representative examples covering:
- All order types
- Strategic accounts
- Different attachment formats
- Malformed inputs
- Edge cases
- Adversarial scenarios

---

## Governance & Scale, Score: 4.5/5

### Strengths
- Excellent governance maturity.
- Clear autonomy boundaries.
- Well-defined escalation triggers.
- Strong audit cadence.
- GDPR considerations are already present.
- Human ownership is clearly defined.

### Gaps
- Cross-Domain Transfer remains weak.
- Knowledge captured in one workflow is not yet systematically reused across others.
- Some operational knowledge remains trapped in subject-matter experts.

### Recommendation
Build a centralized operational knowledge layer that converts:
- Corrections
- Exceptions
- Validation outcomes
- Business-rule changes

into reusable assets across all order
