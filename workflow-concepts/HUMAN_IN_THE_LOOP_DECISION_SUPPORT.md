# Human-in-the-Loop Decision Support

## Purpose

OCIOS is designed around human review.

The system can organize data, score candidates, surface risks, and summarize scenarios, but it should not replace human judgment.

---

## Human-in-the-Loop Design

The dashboard is intended to help a user review:

- current market context
- macro regime
- data freshness
- strategy candidates
- model/scenario confidence
- risk/reward structure
- missing data
- diagnostics
- explanation quality

---

## Separation of Workflow Types

OCIOS separates:

```text
research
recommendation review
execution
```

Research output should not automatically become execution.

---

## Review Questions

Before acting on any candidate, the user should be able to answer:

- What data source produced this?
- Is the data fresh?
- Is this model-backed or scenario-only?
- What regime is the system reporting?
- What is the confidence label?
- What are the key risks?
- Is the option-chain data complete?
- Is the recommendation watchlist-only?
- Did the system flag missing or stale data?

---

## Safety Principle

The system should be useful even when it says:

```text
This is weak.
This is scenario-only.
Model confirmation is unavailable.
Data is stale.
Manual review required.
```
