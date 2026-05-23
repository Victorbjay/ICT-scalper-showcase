# 🗺️ Project Roadmap: Institutional ICT/SMC Scalping Engine

Welcome to the official development roadmap of the **ICT/SMC Automated Scalping Bot**. This document outlines the strategic progression from our foundation to a high-capacity, machine-learning-gated institutional trading execution engine.

---

## 📊 Strategic Architecture Timeline

| Phase | Milestone | Focus Area | Status | Core Impact |
| :--- | :--- | :--- | :--- | :--- |
| **Phase 1** | **Core Foundation** | Direct Execution & Structure | `COMPLETE` | Establishes low-latency MT5 pipeline and base logic. |
| **Phase 2** | **Execution Hardening** | Slip Minimization & Resilience | `COMPLETE` | Solves execution errors, dynamic spreads, and H1 trend filters. |
| **Phase 3** | **Commercial Readiness** | Security & Intellectual Property | `COMPLETE` | Obfuscation, standalone bundling, and client deployment setups. |
| **Phase 4** | **AI/ML & HTF Integration**| Selective Probability Filters | `COMPLETE` | Employs Random Forest gating and walk-forward MTF context. |
| **Phase 5** | **Cloud & Scale Operations** | High-Capacity Infrastructure | `IN PLANNING` | Transitions to MetaAPI, web visualizers, and multi-accounts. |

---

## 🏛️ In-Depth Phase Breakdown

### 🔹 Phase 1: Core Architectural Foundation `[COMPLETE]`

*Objective: Build a resilient, high-speed connection to MT5 brokers via asynchronous execution, detecting clean Smart Money Concepts (SMC) geometry.*

- [x] **Asynchronous Execution Loop**: Built on Python `asyncio` for concurrent symbol polling, reducing scan-to-execution latency to sub-100ms.
- [x] **Algorithmic SMC Detection**: Precise structural math to identify **Breaks of Structure (BOS)**, **Fair Value Gaps (FVG)**, and **Order Blocks (OB)** based on pure price action.
- [x] **MetaTrader 5 Direct Bridge**: Deep integration with MT5 C-APIs for real-time market data streaming and instant execution.
- [x] **Base Risk Engine**: Integrated standard risk parameters including hard stop-losses, daily drawdowns, and spread gates to protect capital.
- [x] **Telegram Journaling Bridge**: Real-time broadcast of signal setups, orders, and closed trades with complete institutional reasoning.

---

### 🔹 Phase 2: Execution Hardening & Slippage Mitigation `[COMPLETE]`

*Objective: Maximize execution efficiency on Exness high-spread conditions and protect strategy margins from retail-broker manipulation.*

- [x] **Auto LIMIT-to-MARKET Converter**: Implemented a fail-safe that catches MT5 error `10015` (Invalid Price) during high-velocity spikes, automatically switching to a safe market entry with strict dollar risk limits.
- [x] **Stochastic ATR-Based Target Engine**: Replaced static targets with dynamic Take Profit models (3.0x to 5.0x ATR) scaling with recent volatility.
- [x] **Bid/Ask Tick Validator**: Bypassed broker delay by verifying pricing via direct tick books, preventing entries on artificial spread widening.
- [x] **H1 Trend & Structure Filter**: Hard directional gate requiring M5 setups to align with Higher Timeframe H1 trend direction.
- [x] **Unicode Logging Sanitization**: Cleaned standard terminal logging outputs to resolve terminal encoding issues on remote Windows VPS.

---

### 🔹 Phase 3: Commercial Readiness & Client Deployment `[COMPLETE]`

*Objective: Secure intellectual property and package the algorithm into a professional, commercial-grade product.*

- [x] **Decoupled JSON Configuration**: Completely separated trading parameters and broker credentials into a clean, secure `config.json` template.
- [x] **PyArmor Intellectual Property Protection**: Obfuscated core strategy modules and mathematical logic to prevent decompilation and reverse-engineering.
- [x] **Single-Executable Compilation**: Bundled the Python runtime, dependencies, and resources into a single lightweight `.exe` using PyInstaller.
- [x] **Rigorous Forward Testing (V1.0)**: Completed an extensive demo/live validation cycle proving stability with a **54.5% win rate** under optimal conditions.

---

### 🔹 Phase 4: V2 Multi-Timeframe Bias & Machine Learning Gating `[COMPLETE]`

*Objective: Combat drawdown in choppy/non-trending markets by introducing deep structural context and predictive AI filters.*

> [!NOTE]
> **Why AI Gating is Essential**: Pure rule-based SMC scalping works well during high-momentum session windows but bleeds capital in sideways trading. Phase 4 introduces a **Random Forest Classifier** acting as an intelligent probability gate, blocking low-probability entries before they touch the broker.

- [x] **V2 Walk-Forward Backtester (`backtest/engine_v2.py`)**: Built a multi-timeframe backtester running historical data with zero look-ahead bias, exporting full feature datasets to `logs/ml_training_data.csv`.
- [x] **Triple-Timeframe Context Scanner**: Scanner concurrently tracks **Daily (D1)**, **4-Hour (H4)**, and **5-Minute (M5)** structures to confirm institutional directional bias.
- [x] **Machine Learning Engine (`src/ml/model.py`)**: Implemented a scikit-learn pipeline utilizing Random Forest algorithms. Automatically handles:
  - Categorical Hot Encoding for pairs and trend bias values.
  - Min-Max scaling for ATR, ADX, and Risk-Reward configurations.
- [x] **AI Probability Gate**: Enforces a strict **`>= 55%` predicted win probability** check on the live broker execution path, with fail-closed mechanisms and an untrained fail-open bootstrapper.

---

### 🔭 Phase 5: High-Capacity Scale & Cloud Infrastructure `[IN PLANNING]`

*Objective: Elevate the bot from local VPS terminals to a massive, multi-account commercial SaaS platform.*

- [ ] **Multi-Account Allocation Manager**:
  - Implement master-slave copy trading functionality.
  - Allow a single VPS instance to distribute signals across multiple client terminals simultaneously with dynamic lot scaling.
- [ ] **MetaAPI Cloud Integration**:
  - Transition from local MT5 desktop installations to serverless cloud endpoints via MetaAPI.
  - Eliminates VPS hardware dependency, reducing execution latencies to local exchange hubs.
- [ ] **Next.js Real-Time Web Dashboard**:
  - Develop a premium Web UI to monitor open positions, equity curves, win/loss distributions, and ML gate decisions.
  - Integrate secure REST APIs to pause/resume the bot remotely.
- [ ] **Dynamic Sweep Trailing Stop Engine**:
  - Programmatic trailing stops that lock in profits by moving the stop-loss behind recently swept market structure highs/lows.
  - Protects floating profits during sudden counter-trend news reversals.
- [ ] **Adaptive Sentiment & News Integration**:
  - Direct integration with high-impact economic calendars via REST interfaces.
  - Dynamic lot reduction or trading pause (e.g., 30 mins pre- and post-FOMC/NFP events).

---
*Document Version: 2.0.0*  
*Last Audited: May 23, 2026*  
