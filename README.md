# Stress Testing & Scenario Analysis Engine for Equity & ETF Portfolios

**Author:** Enrique Sabariego  
**Target Roles:** Market Risk Analyst / Quantitative Analyst  
**Context:** Banking & Asset Management Risk Practices  

This project demonstrates a **Market Risk Stress Testing Engine** for a diversified equity and ETF portfolio using Python. It showcases a full risk analysis workflow commonly applied in banking, asset management, and quantitative finance. The focus is on **Value-at-Risk (VaR)**, **Expected Shortfall (ES)**, historical and hypothetical stress scenarios, and sensitivity analysis to market risk factors.

---

## Project Objectives

- Analyze a diversified equity and ETF portfolio from 2005 to 2023.  
- Compute descriptive statistics and baseline risk metrics:
  - Historical VaR (95%, 99%)  
  - Expected Shortfall (95%, 99%)  
  - Maximum drawdown  
- Implement a modular **stress testing framework** including:
  - Historical scenario replay (2008 Global Financial Crisis, COVID-19)  
  - Hypothetical shocks (volatility and correlation stress)  
- Perform sensitivity analysis to key market risk drivers.  
- Provide actionable insights for **risk committees**, **internal risk appetite monitoring**, and **regulatory stress exercises**.

---

## Data

- **Source:** Yahoo Finance  
- **Assets included:** SPY (US Equity), EFA (Developed Markets ex-US), EEM (Emerging Markets), QQQ (US Tech/Growth)  
- **Frequency:** Daily  
- **Period:** 2005-01-01 to 2023-12-31  
- **Adjusted closing prices** are used for calculations.  

---

## Methodology

### 1. Portfolio Construction

- Construct a long-only portfolio with fixed weights:
  - SPY: 35%  
  - EFA: 25%  
  - EEM: 20%  
  - QQQ: 20%  
- Compute **daily log-returns** and cumulative **Net Asset Value (NAV)**.

### 2. Baseline Market Risk Metrics

- Compute:
  - Historical VaR & Expected Shortfall  
  - Maximum drawdown  
- Analyze the **distribution of portfolio returns** to assess tail risk.

### 3. Stress Testing Framework

- Implemented via a **modular Python class (`StressTestEngine`)**:
  - `historical_scenario(start, end)` — replay historical crisis periods  
  - `volatility_shock(multiplier)` — apply hypothetical volatility shocks  
- Ensures reproducibility and flexibility for multiple stress scenarios.

### 4. Historical Stress Scenarios

- **2008 Global Financial Crisis**:
  - Extreme drawdowns, volatility spikes, cross-asset correlations  
- **COVID-19 Crisis (2020)**:
  - Short, intense volatility regime, rapid market collapse  
- Visualize cumulative NAV and normalized performance for comparison.

### 5. Hypothetical Stress Scenarios

- Apply **volatility shocks (×2, ×2.5, ×3)** to assess potential portfolio losses  
- Explore conceptual correlation breakdowns for multi-asset risk sensitivity.

### 6. Sensitivity Analysis

- Evaluate portfolio exposure to:
  - Volatility changes  
  - Correlation regimes  
- Identify dominant drivers of risk under stressed conditions.

---

## Key Findings

- Stressed losses **significantly exceed baseline VaR and ES**.  
- COVID-like scenarios produce **faster drawdowns** than 2008, despite being shorter.  
- Portfolio vulnerability is largely driven by **volatility clustering**.  
- Insights are directly applicable for:
  - Risk committees  
  - Internal risk appetite monitoring  
  - Regulatory stress exercises  

---

## Visualizations

The notebook includes:

- **Portfolio NAV** over the full period  
- **Drawdowns** highlighting extreme losses  
- **Distribution of daily returns** with tail risk visualization  
- **Cumulative performance** during 2008 and COVID-19 crises  
- **Impact of hypothetical volatility shocks**  
- All visualizations are embedded in the notebook (`stress-testing-portfolio.ipynb`) for easy reference.

---

## How to Run

Clone the repository:

```bash
git clone https://github.com/EnriqueSabariego/stress-testing-portfolio.git
cd stress-testing-portfolio
