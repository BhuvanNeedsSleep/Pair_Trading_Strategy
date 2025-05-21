#  Pair Trading Strategy – Statistical Arbitrage on US IT Stocks

This repository implements a **pair trading strategy** based on **mean reversion and statistical arbitrage**, applied to US IT sector stocks listed on the NYSE. The strategy includes pair selection using correlation and cointegration, dynamic signal generation using spread and standard deviations, and full backtesting with performance metrics.

---

## Overview

Pair trading is a **market-neutral strategy** that profits from the relative movement of two historically correlated stocks. It involves identifying temporary mispricings between two stocks that typically move together and trading on the assumption they will revert to their historical relationship.

---

##  Key Concepts Used

- **Mean Reversion**: Prices of strongly correlated stocks tend to revert back to their historical relationship.
- **Correlation & Cointegration**: Used to identify optimal stock pairs.
- **Z-Score of Spread**: Determines trade signals (+1 or -1 standard deviation).
- **Beta Hedge**: Used to calculate an adjusted spread that accounts for stock sensitivity.
- **Backtesting Metrics**: Cumulative returns, Sharpe ratio, and drawdown analysis.

---

## 🧾 Dataset

- Historical price data (01/01/2019 – 31/12/2023)
- Fetched using [`yfinance`] for:
  - Alphabet Inc. (GOOGL)
  - Accenture (ACN)

---

##  Pair Selection

From a universe of 10 NYSE-listed US IT stocks, the pair **GOOGL–ACN** was selected based on:

-  **High Correlation** (moves similarly)
-  **Low Cointegration P-value** (< 0.05)
-  **Visual Price Movement Similarity** (post normalization)

---

##  Strategy Logic

1. **Normalize Prices**: To allow for direct comparison.
2. **Calculate Spread**:
   - Raw spread: `GOOGL - ACN`
   - Adjusted spread: `GOOGL - β * ACN` (via linear regression)
3. **Generate Signals**:
   - If spread > +1 std: `Short GOOGL, Long ACN`
   - If spread < –1 std: `Long GOOGL, Short ACN`
4. **Backtest**: Simulate strategy over historical data to analyze profitability.

---

##  Backtesting Results

-  **Cumulative Return**: **221.78%**
-  **Return Multiplier**: **3.22×**
-  **Consistent Mean Reversion Observed**


