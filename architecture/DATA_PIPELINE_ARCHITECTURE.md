# Data Pipeline Architecture

## Overview

OCIOS is designed around a layered data workflow. The goal is to make market inputs, macro signals, options-chain data, model outputs, and diagnostics visible in one research dashboard.

---

## Conceptual Data Flow

```text
Live quote / market data
        ↓
Portfolio and position context
        ↓
Macro indicator inputs
        ↓
Options-chain capture
        ↓
Candidate generation
        ↓
Scoring and inference
        ↓
Recommendation output
        ↓
Dashboard display and diagnostics
```

---

## Data Categories

### Live Market Data

Market data may include:

- symbol
- last price
- bid
- ask
- daily change
- daily percent change
- volume
- timestamp
- source

### Macro Regime Inputs

Macro inputs may include broad-market, volatility, yield, dollar, and commodity-sensitive indicators.

Example indicators:

- SPY
- QQQ
- VIX
- TNX / 10Y proxy
- UUP
- GLD
- SLV
- USO

### Options-Chain Data

Options-chain data may include:

- underlying symbol
- expiration
- strike
- call / put
- bid
- ask
- last
- volume
- open interest
- implied volatility
- Greeks, where available
- data timestamp

### Candidate Strategy Data

Candidate strategy rows may include:

- symbol
- strategy type
- direction
- expiration
- short leg
- long leg
- spread width
- credit / debit estimate
- probability estimate
- max risk
- max reward
- score
- confidence label
- model/scenario status

### Diagnostics Data

Diagnostics include:

- backend health
- API status
- data-source status
- quote source
- model discovery status
- inference status
- recommendation file freshness
- pipeline run time
- error messages

---

## Data Freshness

OCIOS should show freshness directly in the interface.

Important freshness fields include:

```text
E*TRADE refresh time
fallback market-data refresh time
macro snapshot time
inference run time
data-through timestamp
recommendation file update time
```

---

## Source Priority

A preferred source order is:

```text
1. George / broker bridge live data
2. locally captured live quote files
3. option-chain capture files
4. macro snapshot files
5. fallback market-data providers
6. scenario-only fallback logic
```

---

## Public Showcase Note

This public repository does not include live account data, raw brokerage responses, credentials, tokens, or private market-data files.
