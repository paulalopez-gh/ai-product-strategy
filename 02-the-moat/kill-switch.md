# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | Azure AI Foundry + Azure OpenAI planned as primary AI platform | M | Identify a secondary provider (Anthropic via Bedrock or Gemini) and document migration dependencies. |
| **Abstraction** | Business logic separated from model prompts, but still coupled to Azure services and Document Intelligence | M | Define a model abstraction interface so classification, extraction, and validation services can be swapped without changing workflow logic. |
| **Routing** | Single-provider architecture during MVP and Beta | H | Create a proof of concept using the same order-processing workflow with a second model to validate portability. |
| **Eval** | Human-in-the-loop review by Customer Service Manager with operational validation | L | Build an evaluation dataset of historical orders with expected outputs and benchmark accuracy across providers. |

## Portability Score
<!-- Ready / Partial / Locked --> Partial

## If [primary vendor] doubles pricing tomorrow:
<!-- What's your 48-hour response? --> Freeze expansion to new use cases and customers.
Measure actual AI cost per processed order versus operational savings.
Prioritize only high-volume, high-confidence workflows (starting with reload requests).
Increase confidence thresholds to reduce unnecessary model calls.

## If [primary vendor] ships a competing product:
<!-- What's defensible that they can't replicate? --> Microsoft can replicate the AI capability, but it cannot easily replicate years of accumulated operational knowledge, customer behaviour patterns, workflow exceptions, and business logic embedded in Edenred's order processing ecosystem.
