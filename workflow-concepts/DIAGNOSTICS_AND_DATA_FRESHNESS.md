# Diagnostics and Data Freshness

## Why Diagnostics Matter

A decision-support system is only useful if the user can see whether the underlying data and models are working.

OCIOS is designed to make system state visible.

---

## Key Diagnostic Questions

The dashboard should help answer:

- Is the backend running?
- Is the data bridge available?
- Are quotes fresh?
- Is macro data fresh?
- Did option-chain capture run?
- Did candidate scoring run?
- Were model files discovered?
- Were runnable models loaded?
- Was trained-model inference applied?
- Was fallback scenario inference used?
- When was the recommendation file last updated?

---

## Data Freshness Fields

Important freshness fields include:

```text
broker / quote refresh time
fallback market-data refresh time
macro snapshot time
option-chain capture time
inference run time
data-through timestamp
recommendation output time
```

---

## Diagnostic States

Example diagnostic states:

```text
BACKEND_HEALTHY
BRIDGE_READY
QUOTE_SOURCE_LIVE
FALLBACK_DATA_USED
MODEL_FILES_FOUND
MODEL_LOAD_FAILED
MODEL_INFERENCE_APPLIED
SCENARIO_ONLY_FALLBACK
NO_CURRENT_RECOMMENDATIONS
DATA_STALE
```

---

## Design Principle

A blank dashboard is not enough.

If output is missing, the system should explain why:

```text
No chain data found.
No model files discovered.
Quote source unavailable.
Recommendation file stale.
Scenario fallback used.
Model incompatible with current features.
```
