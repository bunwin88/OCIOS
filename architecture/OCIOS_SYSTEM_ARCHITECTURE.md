# OCIOS System Architecture

## Purpose

OCIOS is structured as a market-intelligence and options-chain decision-support environment. The system is designed to organize market inputs, options-chain data, macro regime signals, model/scenario scoring, diagnostics, and human review into a single research cockpit.

The architecture separates research workflows from execution workflows. The system is intended to support analysis and review, not automatic order placement.

---

## High-Level Architecture

```text
George OS Workstation
        ↓
Shared market-data and portfolio bridge
        ↓
OCIOS Desktop Research Shell
        ↓
Python / FastAPI Backend
        ↓
Market Data, Option Chain, Macro, Model, and Recommendation Modules
        ↓
Dashboard, Diagnostics, and Human Review
```

---

## Major Components

### 1. George OS Bridge

George OS acts as the broader workstation environment. In the working prototype, George can provide shared context such as:

- live quote data
- portfolio context
- account-level visibility
- authentication status
- local runtime paths
- model and data freshness metadata

OCIOS uses this bridge so the research module does not need to duplicate every upstream integration.

### 2. OCIOS C# / WPF Shell

The desktop shell provides the main research interface.

Primary UI areas include:

- Dashboard
- Options Chain
- AI Intelligence
- Macro Regime
- News & Events
- Trade Ideas
- Data Center
- Portfolio
- Diagnostics / System

### 3. Python / FastAPI Backend

The backend organizes research services and data endpoints.

Conceptual backend responsibilities include:

- quote retrieval
- macro snapshot generation
- options-chain capture
- candidate scoring
- model discovery
- inference-status reporting
- recommendation file generation
- diagnostics and health reporting

### 4. Data and Recommendation Layer

The data layer stores intermediate research outputs such as:

- live quote snapshots
- macro snapshots
- options-chain captures
- candidate scores
- recommendation files
- model discovery summaries
- diagnostics output

### 5. Human Review Layer

OCIOS intentionally keeps a human in the loop.

The dashboard provides:

- candidate strategy visibility
- score and confidence labels
- macro regime context
- model/inference status
- diagnostic warnings
- explanation panels
- Go / No-Go research summaries

---

## Design Principles

- Keep research separate from execution.
- Show data freshness clearly.
- Show model status honestly.
- Label fallback/scenario-only ideas clearly.
- Avoid hidden automation.
- Make diagnostics visible.
- Preserve human review and control.
- Treat AI output as decision support, not instruction.
