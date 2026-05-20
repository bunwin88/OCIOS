# OCIOS Research Workflow

## Overview

OCIOS is organized around a repeatable research workflow.

The goal is to avoid scattered, manual review across separate tools by bringing the major research steps into one operational dashboard.

---

## Workflow

```text
1. Refresh market and portfolio context
2. Capture or refresh options-chain data
3. Update macro regime inputs
4. Generate candidate strategies
5. Score candidates with rules/scenarios
6. Apply trained model overlay where available
7. Generate narrative explanation
8. Review dashboard and diagnostics
9. Preserve human decision control
```

---

## Research Outputs

The workflow may produce:

- candidate strategy list
- macro regime summary
- model/inference status
- confidence labels
- scenario-only warnings
- AI-assisted explanation
- Go / No-Go research snapshot
- diagnostics and freshness status

---

## Candidate Quality Labels

Example labels:

```text
MODEL_BACKED
AUTO_AGENT_CURRENT
LOW_CONFIDENCE_SCENARIO_ONLY
WATCHLIST_ONLY
MODEL_INCOMPATIBLE_FEATURES
NO_LIVE_CHAIN_CONFIRMATION
```

---

## Operating Principle

The system should always explain what it is using.

A candidate should not simply appear as an “AI trade.” It should show whether it was produced by:

- live option-chain data
- rule/scenario scoring
- trained model overlay
- macro regime context
- fallback logic
- stale or incomplete data
