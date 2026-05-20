# Model and Inference Architecture

## Purpose

OCIOS is designed to make model and inference status visible. The dashboard should not simply say “AI” without showing whether trained models are actually loaded and applied.

---

## Inference Modes

OCIOS conceptually supports multiple inference modes:

```text
rules/scenario inference
trained model inference
model overlay scoring
fallback candidate generation
AI-assisted narrative explanation
```

---

## Model Discovery

The system is designed to scan known model locations for trained artifacts such as:

```text
.joblib
.pkl
.pickle
.sav
.keras
.h5
.pt
.pth
.onnx
.xgb
.lgb
.cbm
```

Model discovery should distinguish between:

- model files found
- scaler files found
- training scripts found
- runnable models loaded
- incompatible models skipped
- model inference successfully applied

---

## Candidate Scoring Flow

```text
candidate row
   ↓
feature extraction
   ↓
scenario/rule scoring
   ↓
model compatibility check
   ↓
trained model overlay, if available
   ↓
confidence label
   ↓
recommendation output
```

---

## Confidence Labels

OCIOS should clearly label candidate quality.

Example labels:

```text
AUTO_AGENT_CURRENT
LOW_CONFIDENCE_SCENARIO_ONLY
SCENARIO_ONLY_NO_LIVE_CHAIN_OR_MODEL_CONFIRMATION
MODEL_BACKED
MODEL_INCOMPATIBLE_FEATURES
WATCHLIST_ONLY
```

---

## AI Explanation Layer

The AI explanation layer should summarize:

- strategy type
- market backdrop
- macro regime
- model/scenario status
- key risks
- why the setup may be weak or strong
- whether the setup is watchlist-only
- what data is missing or stale

---

## Important Design Principle

If no trained model is active, the system should still produce research output, but it must clearly label that output as rules/scenario-based rather than model-backed.
