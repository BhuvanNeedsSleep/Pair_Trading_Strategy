#  My First Pair Trading Strategy – Learning Quant from Scratch

This repository contains the full implementation of my **first ever quant trading strategy** — a **mean reversion-based pair trading model**. This project was my entry point into the world of quantitative finance, built entirely from scratch with no prior background.

It also serves as part of my application for the **Quant Strategist/Lead role** in my college's Quantitative Investment Program (QIP).

---

##  Why This Project?

I started learning quantitative finance from zero around Jan 7 for the Zelta Hackathon. With growing interest, I spent the next few days exploring statistical arbitrage and **pair trading**, focusing on real, implementable strategies that don’t require complex machine learning.

This project is the result of that exploration — a serious, self-driven effort to learn, build, test, and deliver something meaningful.

---

##  Strategy Overview

Pair trading is a **market-neutral strategy** that exploits the relative mispricing between two historically correlated stocks. The core idea is simple: when their price relationship diverges beyond a certain threshold, we bet on it reverting to the mean.

---

##  Key Components

###  Pair Selection

- Universe: Indian IT sector stocks (e.g., TCS, INFY, HCLTECH, etc.)
- Used **Correlation** to identify short-term comovement
- Used **Cointegration (ADF test p-value)** to ensure long-term mean-reverting relationship
- Selected: **TCS & HCLTECH** — Correlation ≈ 0.93, Cointegration p-value ≈ 0.01

###  Data Processing

- Fetched historical stock prices using `yfinance`
- Normalized and visualized price movements
- Generated **spread** as the difference in adjusted prices

###  Mean Reversion Strategy

- Entry:
  - Go long/short when spread exceeds ±1 standard deviation
- Exit:
  - Close position when spread reverts to mean (or crosses 0)
- Position Sizing: Fixed exposure based on historical spread behavior

---

##  Backtesting Results

- Traded TCS vs HCLTECH from 2019–2023
- Metrics calculated:
  -  **Cumulative Return**
  -  **Sharpe Ratio**
  - **Max Drawdown**
- Results showed **positive alpha**, confirming strategy validity

---

##  Bonus Attempts

- Tried implementing AI-based forecasting but didn't yield good results (negative returns)
- Decided to focus on **robust statistical logic** over hype-driven complexity
- Plan to revisit AI modeling after mastering fundamentals

---

## Tech Stack

- Python
- `pandas`, `numpy`, `statsmodels`
- `matplotlib`, `seaborn`
- `yfinance`

---


