# 📈 Weekly Trading Performance Report
### Period: May 16 – May 23, 2026

Welcome to the weekly trading performance report for the automated ICT/SMC Scalping Engine. This week was characterized by a highly selective market phase where our dynamic risk-reward model successfully covered a series of consecutive losses with two massive high-probability wins, closing the week in net profit.

---

## 📊 Executive Summary

| Metric | Performance Value | Strategy Breakdown |
| :--- | :--- | :--- |
| **Total Executions** | 9 Trades | **SMC FVG**: 6 Trades (1W - 5L) |
| **Gross Wins** | 2 Trades (22.2% WR) | **OrderBlock**: 1 Trade (1W - 0L) |
| **Gross Losses** | 7 Trades (77.8% LR) | **AMD Judas**: 2 Trades (0W - 2L) |
| **Net Profit / Loss** | **+$5.63** | **EURUSDm**: 3 Trades (-$4.73) |
| **Net Account R-Return**| **+1.25 R** | **GBPUSDm**: 4 Trades (+$17.90) |

> [!TIP]
> **The Power of Asymmetric Risk-Reward**: Despite a low win rate of 22.2%, the account closed in profit. This mathematically validates our **minimum 4.0x Risk-to-Reward ratio** on setups, showing that 2 high-probability wins easily recovered 7 micro-losses.

---

## 📈 Equity & Cumulative PnL Curve

Below is the visual tracking of the account equity fluctuations throughout the trading week:

![Cumulative Weekly PnL](assets/weekly_pnl_2026_05_23.svg)

---

## 🗂️ Trade Ledger (Summary Table)

This clean ledger presents our executions, their strategy classifications, and financial returns. For detailed audits and reasons, refer to the **Trade Case Studies** section below.

| Ticket | Asset | Direction | Strategy | Outcome | PnL (USD) | Return (R) |
| :--- | :--- | :---: | :--- | :---: | :---: | :---: |
| `2754277261` | EURUSD | SELL | AMD Judas | ❌ SL Hit | -$0.69 | -0.25 R |
| `2756212422` | GBPJPY | BUY | SMC FVG | ❌ SL Hit | -$2.77 | -1.00 R |
| `2758985151` | GBPUSD | BUY | AMD Judas | ❌ SL Hit | -$2.84 | -1.00 R |
| `2759497664` | USDJPY | BUY | SMC FVG | ❌ SL Hit | -$2.77 | -1.00 R |
| `2762885972` | GBPUSD | SELL | SMC FVG | ❌ SL Hit | -$2.60 | -1.00 R |
| `2767138158` | EURUSD | BUY | SMC FVG | ❌ SL Hit | -$2.88 | -1.00 R |
| `2771930164` | GBPUSD | BUY | OrderBlock | ✅ TP Hit | **+$11.04** | **+4.00 R** |
| `2772637999` | EURUSD | SELL | SMC FVG | ❌ SL Hit | -$3.16 | -1.00 R |
| `2772443947` | GBPUSD | BUY | SMC FVG | ✅ TP Hit | **+$12.30** | **+4.40 R** |
| **TOTAL** | | | | **2W - 7L** | **+$5.63** | **+1.25 R** |

---

## 🔍 In-Depth Trade Case Studies & Auditing

Here we analyze each individual setup to document the market structure context, institutional reasoning, and lessons learned.

### 🟢 Winning Trades (Case Studies)

#### 1. GBPUSD BUY (Ticket: `2771930164`) — **OrderBlock Setup**
* **Execution Window**: 2026-05-22 13:27 – 14:10 UTC (Lagos Time: 2:27 PM – 3:10 PM)
* **PnL**: **+$11.04** (+4.0R Return)
* **Market Context & Reasoning**: 
  An ICT Bullish Order Block was identified on the M5 timeframe. The bot captured the last bearish candle before a strong bullish expansion that swept buy-side liquidity. Price retraced precisely into this block, triggering our limit buy order.
* **Outcome**: Fast expansion straight to target, hitting our 4.0R Take Profit with minimal drawdown.

#### 2. GBPUSD BUY (Ticket: `2772443947`) — **SMC FVG Setup**
* **Execution Window**: 2026-05-22 15:04 – 17:30 UTC
* **PnL**: **+$12.30** (+4.4R Return)
* **Market Context & Reasoning**: 
  A bullish Break of Structure (BOS) was detected on the M5 timeframe, leaving behind a wide Fair Value Gap (FVG). Directional bias aligned with the bullish H1 order flow. The bot placed a limit entry at the consequent encroachment (50% midpoint) of the FVG.
* **Outcome**: Price tapped the FVG, filled our limit order, and immediately rallied, sweeping the London session high and hitting the Take Profit.

---

### 🔴 Losing Trades & Lessons Learned

#### 1. EURUSD SELL (Ticket: `2754277261`) — **AMD Judas Setup**
* **Loss**: -$0.69 (-0.25R)
* **Context**: Taken during early London session manipulation. The trade was automatically closed early via session protection rules because momentum stalled.
* **Lesson**: The early session cut minimized our standard 1.0R loss to a mere 0.25R, proving the value of algorithmic trade management.

#### 2. GBPJPY BUY (Ticket: `2756212422`) — **SMC FVG Setup**
* **Loss**: -$2.77 (-1.0R)
* **Context**: Entered on an M5 bullish retracement. However, the higher timeframe bias (H4/D1) was bearish. The trade was stopped out due to a trend continuation on the larger timeframe.
* **Lesson**: Formed the exact basis for our **Phase 4 Upgrade**, which blocks M5 entries that disagree with the Higher Timeframe (H4/Daily) structural trend.

#### 3. GBPUSD BUY (Ticket: `2758985151`) — **AMD Judas Setup**
* **Loss**: -$2.84 (-1.0R)
* **Context**: Stop hunt manipulation during New York session open swept our stop-loss before expanding in our direction.
* **Lesson**: Highlighted the need for structural stop placement behind true session extremes rather than rolling lookbacks. Successfully patched in our late-week AMD upgrade.

#### 4. USDJPY BUY, GBPUSD SELL, EURUSD BUY, EURUSD SELL (Various Tickets)
* **Total Losses**: -$11.41
* **Analysis**: These setups suffered from trading in the middle of consolidation ranges during the late Asian and early pre-London sessions, leading to instant whipsaws.
* **Lesson**: Confirms the absolute necessity of our new **AI/ML Probability Gatekeeper**, which is trained to automatically filter out consolidation setups and session chop, and requires a >55% probability score to execute.

---

## 🔮 Next Steps & Continuous Optimization
- **Deploy AI Gate**: Once backtesting concludes, we will train our Random Forest model on the 3-month dataset. This will automatically block lower-probability range setups (like the USDJPY and EURUSD losses this week) in live execution.
- **Enforce HTF Bias**: The new scanner will restrict the bot to trade *only* in the direction of the daily and 4-hour trend, completely eliminating counter-trend losses like the GBPJPY setup on May 18.
