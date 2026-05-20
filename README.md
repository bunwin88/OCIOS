# OCIOS — Options Chain Intelligence Operating System

**AI-Assisted Market Research & Decision-Support Prototype**

OCIOS is an independent applied AI and workflow systems project exploring how live brokerage data, options-chain intelligence, macro regime monitoring, model/scenario scoring, portfolio visibility, diagnostics, and AI-assisted explanation can be combined into a single market research and decision-support cockpit.

The project is designed as a **research and decision-support environment**, not an automated trading platform. It focuses on surfacing market context, strategy candidates, model status, data freshness, and workflow diagnostics so a human user can review decisions with better visibility.

---

## What OCIOS Does

OCIOS is built around a unified research workflow:

```text
Live brokerage / market data
        ↓
Watchlist and portfolio visibility
        ↓
Options-chain capture and inspection
        ↓
Macro regime and market signal monitoring
        ↓
Candidate strategy scoring
        ↓
Model / scenario inference review
        ↓
AI-assisted narrative explanation
        ↓
Human decision-support dashboard
```

The system currently explores:

- Live quote and portfolio data integration
- Options-chain capture and inspection
- Spread candidate generation and scoring
- Macro regime monitoring using SPY, QQQ, VIX, TNX, UUP, GLD, SLV, and USO-style market inputs
- Model discovery and inference-status visibility
- Scenario-only fallback scoring when trained model confidence is unavailable
- AI-assisted explanation of candidate trades and market context
- Diagnostics for backend health, data freshness, model availability, and source status
- Separation between research recommendations and execution workflows

---

## Architecture

OCIOS runs as a C# / WPF desktop shell with a Python / FastAPI backend.

```text
OCIOS C# WPF shell
        ↓
Python FastAPI backend
        ↓
Market data, option-chain, macro, model, and recommendation modules
        ↓
Research dashboard and decision-support output
```

In the working local build, OCIOS can integrate with a broader workstation environment that owns primary brokerage authentication and passes sanitized quote, portfolio, and account context into OCIOS through a local bridge. The public repository should avoid including credentials, tokens, raw account identifiers, or private brokerage payloads.

---

## Core Dashboard Areas

- **Dashboard** — live quote context, candidate strategies, macro regime, AI insight, and Go/No-Go summary
- **Options Chain** — captured option-chain data, expirations, strikes, bid/ask context, and contract inspection
- **AI Intelligence** — model discovery, model status, inference mode, scenario/rule inference, and confidence visibility
- **Macro Regime** — market signal components, macro score, and regime classification
- **News & Events** — market context and event-risk inputs
- **Trade Ideas** — ranked strategy candidates and narrative review
- **Data Center** — data files, candidate outputs, model files, and local cache status
- **Portfolio** — portfolio/position context when connected to a local data bridge
- **Diagnostics / System** — backend health, API status, data freshness, and runtime diagnostics

---

## Key Concepts

### Live Market Data Dashboard

OCIOS displays quote and market context for watchlist symbols and macro indicators. Data freshness is shown directly in the header, including brokerage refresh time, fallback data refresh time, inference time, and data-through timestamp.

### Macro Regime Monitoring

The system tracks market inputs such as broad market indexes, volatility proxies, yields, dollar strength, and commodity-sensitive indicators. These inputs feed into a macro score and named regime label, for example:

```text
REGIME: RISK_ON_NEUTRAL
MACRO SCORE: 52 / 100
```

### Options-Chain Intelligence

OCIOS captures and reviews options-chain data for strategy research. The goal is to support inspection of expirations, strikes, bid/ask behavior, spread structure, and scenario-based trade candidates.

### Candidate Scoring

The system scores candidate strategies using available option-chain data, live quote data, scenario rules, and model outputs where available. If trained model output is unavailable, OCIOS can still generate lower-confidence scenario-only candidates and clearly label them as such.

### Model and Inference Visibility

OCIOS includes model-discovery and inference-status reporting. It distinguishes between:

- model files discovered
- model files loaded
- trained-model inference applied
- rules/scenario inference applied
- fallback candidate generation

This avoids hiding behind a generic “AI” label and instead shows what the system is actually using.

### AI-Assisted Narrative Review

The AI bridge is designed to summarize the strategy, explain the macro backdrop, identify risk factors, and clarify whether a candidate is model-backed, scenario-only, weak, or higher-confidence.

---

## Technologies and Concepts Explored

- C# / WPF
- Python
- FastAPI
- REST API design
- Brokerage API integration concepts
- Options-chain data workflows
- Model registry and inference-status tracking
- Scenario scoring
- Macro regime monitoring
- JSON / CSV / SQLite data pipelines
- Local desktop dashboard design
- Workflow orchestration
- Applied AI decision-support systems
- Operational intelligence dashboards

---

## Example Workflow

```text
1. Load market quote, portfolio, and account context from a local data bridge.
2. Capture or refresh option-chain and macro inputs.
3. Score candidate strategies using scenario/rule logic and available model artifacts.
4. Check model registry and inference status.
5. Generate candidate rankings and recommendation files.
6. Display top ideas, macro regime, quote data, diagnostics, and explanation.
7. Keep execution separate from research and require human review.
```

---

## Repository Status

Status: **active research prototype / portfolio showcase**

This repository is intended to demonstrate applied AI workflow design, market-data orchestration, options-chain research tooling, dashboard architecture, model-status visibility, and diagnostic thinking.

It is **not** financial advice, investment advice, or a live automated trading system.

---

## Safety and Privacy Notes

Before publishing any working code, remove or redact:

- API keys
- OAuth tokens
- brokerage credentials
- account IDs
- live portfolio values
- raw order logs
- personal file paths
- local IPs
- private model outputs
- unredacted screenshots
- virtual environments
- cache folders
- large raw market-data files

---

## Professional Relevance

OCIOS demonstrates hands-on experience building an applied AI workflow system that combines data ingestion, backend services, desktop UI design, model visibility, diagnostics, and decision-support workflows.

The broader professional value is not the market domain itself, but the operating-system-style approach to complex information workflows:

- ingest multiple data sources
- normalize the data
- surface operational status
- run scoring/inference logic
- explain the output
- preserve human review and control
- separate research from execution
