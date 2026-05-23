# 🤖 ICT/SMC Institutional Scalping Bot (v1.0)

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Trading](https://img.shields.io/badge/Trading-ICT%20%2F%20SMC-green.svg)](https://www.metatrader5.com/)
[![Security](https://img.shields.io/badge/Security-Obfuscated-red.svg)](https://pyarmor.readthedocs.io/)

An institutional-grade automated trading engine designed for **MetaTrader 5**. This bot utilizes **Smart Money Concepts (SMC)** and **ICT Power of 3** logic to identify high-probability scalping setups on M5 timeframes with H1 directional bias.

---

## 🏛️ Trading Philosophy
Unlike retail bots that rely on lagging indicators (RSI, MACD), this engine trades **Market Structure**:
- **Liquidity Sweeps**: Identifies "stop hunts" where retail liquidity is taken.
- **Break of Structure (BOS)**: Confirms institutional displacement.
- **Fair Value Gaps (FVG)**: Targets imbalances for precise entries.
- **Order Blocks (OB)**: Enters at institutional footprints.

## 🚀 Key Technical Features
- **Async Engine**: Built on `asyncio` for low-latency market scanning and execution.
- **Dynamic Risk Management**: 
  - Adaptive Risk-Reward (RR) based on ATR volatility.
  - Hard stop-loss management based on structural invalidation.
- **Execution Hardening**: 
  - Automatic **Limit-to-Market** correction to prevent MT5 "Invalid Price" errors.
  - Live tick-validation for ultra-precise fills.
- **News Guard**: Automatic pausing during high-impact economic events.
- **Automated Journaling**: Full ICT-reasoning recorded for every trade to enable professional audits.

## 📦 Deployment & Security
The bot is distributed as a protected executable using **PyArmor** obfuscation, ensuring the proprietary trading logic remains secure from reverse-engineering while being easy for clients to run via a simple `config.json` setup.

---

## 🛠️ Quick Start (Developer Mode)

1. **Clone the repo**:
   ```bash
   git clone https://github.com/yourusername/exness_scalping_bot.git
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure**:
   Copy `config_template.json` to `config.json` and enter your Exness MT5 credentials.

4. **Run**:
   ```bash
   python run.py
   ```

---

## 📊 Performance & Roadmap
- [**V2 AI/ML & HTF Integration Guide**](docs/AI_V2_INTEGRATION.md) — Documentation on our Multi-Timeframe and AI Probability Gatekeeper.
- [**Weekly Performance Report (May 16-23)**](docs/WEEKLY_REPORT_2026_05_23.md) — 22.2% Win Rate (+$5.63 PnL).
- [**Weekly Performance Report (May 09-16)**](docs/WEEKLY_REPORT_2026_05_16.md) — 54.5% Win Rate.
- [**Project Roadmap**](docs/ROADMAP.md) — See our development journey and future goals.
- [**Trade Case Studies**](docs/PERFORMANCE.md) — View logic breakdowns of our best setups.
- **Trade Analysis** — Detailed ICT-reasoning recorded for every trade to enable professional audits.

---

**Disclaimer**: *Trading involves significant risk. This software is for educational and automated execution purposes only. Past performance does not guarantee future results.*
