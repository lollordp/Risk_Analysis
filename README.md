# ⚠️ Risk Analysis Project

## Overview
This project explores financial risk assessment through Value-at-Risk (VaR) estimation, portfolio construction, and fixed-income analysis. It combines top-down and bottom-up VaR models, applies robust portfolio optimization techniques, and evaluates risk in a bond instrument using simulation and analytical tools.

The project consists of:

- Multiple VaR estimation models, both parametric and non-parametric
- Construction and evaluation of three portfolio strategies
- Bond risk analysis using Delta, Delta-Gamma, and full revaluation methods

---

## Project Setup

### Data
- Time Frame: 10 years of daily data
- Assets: AAPL, MSFT, IBM, NVDA, GOOGL, AMZN
- Fixed-Income: 10-year bond with 5% annual coupon, priced at 99
- Yield Volatility: Gaussian i.i.d. process with σ = 0.006

---

## Tools & Technologies
- **Python**
- NumPy, Pandas for numerical and data processing
- Matplotlib, Seaborn for visualization
- Statsmodels, SciPy for distribution tests and fitting
- Optimization libraries for portfolio construction
- Monte Carlo simulation for VaR and ES

---

## Methodology

### 📊 1. VaR Forecasting Models
Implemented and compared six models:

- **Top-down Normal (AP1_VaR)**: Rolling mean & std. with Gaussian assumption  
- **Top-down t-Distribution (AP1t_VaR)**: Captures fat tails  
- **Delta-Gamma (AP1B_VaR)**: Uses Cornish-Fisher expansion for skewness & kurtosis  
- **Non-Parametric Bootstrap (AP2_VaR)**: Empirical, data-driven VaR  
- **Monte Carlo with EWMA (AP3_VaR)**: 2000 simulations, log-returns  
- **Analytical Taylor Approximation (AP4_VaR)**: Bottom-up RiskMetrics with λ=0.94

Each model was evaluated via:

- Violation rates at 90% and 99% confidence levels  
- Kupiec’s Unconditional Coverage Test  
- Christoffersen’s Conditional Coverage Test

### 📈 2. Portfolio Construction
Constructed three portfolio strategies using the above asset universe:

- **Risk Parity Portfolio (RPP)**: Equal risk contribution via Component VaR  
- **Maximum Diversification Portfolio (MDP)**: Maximizes diversification ratio  
- **Equally Weighted Portfolio (EWP)**: Simple benchmark strategy

### 🔍 3. Performance Metrics
Assessed portfolios based on:

| Metric                | RPP      | MDP      | EWP      |
|----------------------|----------|----------|----------|
| Sharpe Ratio         | 0.92     | 0.94     | 0.97     |
| Max Drawdown         | -0.70    | -6.55    | -19.29   |
| VaR Violations (95%) | 106–121  | 96–106   | 121–126  |
| Skewness             | -0.52    | -0.55    | -0.47    |
| Excess Kurtosis      | 6.59     | 6.69     | 5.53     |

📉 All portfolios showed non-normal return distributions based on:
- Shapiro-Wilk Test
- Kolmogorov-Smirnov Test
- Jarque-Bera Test  
→ Parametric VaR models may underestimate tail risks.

### 💵 4. Bond Risk Analysis
Assessed a fixed-income instrument using six VaR estimation methods (99% confidence):

- **Exact Revaluation**
- **Delta Approximation**
- **Delta-Gamma Approximation**
- **Monte Carlo (Delta)**
- **Monte Carlo (Delta-Gamma)**
- **Monte Carlo (Full Revaluation)**

Key outcomes:

- Probability of 10% bond price drop in 30 days: **~34.64%**
- Expected Shortfall (99%) over 90 days (MC full revaluation): **£61.46**
- Delta-Gamma gives good short-term accuracy, but underestimates long-term risk

---

## Results Summary

### ✅ Best performing model (VaR 90%):  
**Bottom-up Monte Carlo with EWMA** — strong unconditional and conditional coverage

### ✅ Best performing portfolio:  
**Maximum Diversification Portfolio** — highest Sharpe, but higher drawdowns

### ✅ Most stable strategy:  
**Risk Parity Portfolio** — better downside control and fewer VaR violations

---

## Conclusion
- **Parametric models** are efficient but suffer under non-normal return conditions
- **Bootstrapping and simulations** better capture fat tails and volatility clusters
- **Risk Parity** balances returns and risk better than naïve equal-weighting
- **Bond VaR** estimation benefits from full revaluation and non-linear risk modeling

---

## 📬 Contact
**Lorenzo Rossi**  
📧 Email: lollordp@gmail.com  
🔗 LinkedIn: [Lorenzo Rossi](https://www.linkedin.com/in/lorenzo-rossi-profile)

