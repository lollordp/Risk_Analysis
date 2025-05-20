⚠️ Risk Analysis Project
Overview
This project provides a comprehensive evaluation of market risk through Value-at-Risk (VaR) modeling, portfolio construction, and bond risk analysis. It investigates both the statistical properties of returns and the effectiveness of various VaR estimation techniques. The analysis culminates in constructing optimized portfolios and assessing the risk of a fixed-income instrument using Monte Carlo simulations and analytical approximations.

📂 Project Structure
The project is divided into three core components:

VaR Forecasting Models: Comparison of six different VaR estimation techniques on equity portfolio returns.

Portfolio Construction & Evaluation: Implementation and analysis of three portfolio strategies (Risk Parity, Maximum Diversification, Equally Weighted).

Bond Risk Analysis: VaR and Expected Shortfall estimation for a bond using analytical and simulation-based approaches.

📅 Data & Instruments
Asset Class: Equities (AAPL, MSFT, IBM, NVDA, GOOGL, AMZN)

Bond: 10-year maturity, 5% annual coupon, priced at 99

Time Horizon: 10 years of daily data

Risk-Free Rate: Assumed zero for Sharpe Ratio calculations

YTM Model: Gaussian i.i.d. process with σ = 0.006

🧰 Tools & Technologies
Python

NumPy, Pandas for data analysis

Matplotlib, Seaborn for visualizations

SciPy, Statsmodels for statistical testing

Optimization Libraries for portfolio weights

Monte Carlo Simulations for VaR & ES estimation

🧪 Methodology
📊 1. VaR Forecasting Models
Tested six approaches on a multi-asset portfolio:

Top-down Normal VaR (AP1)

Top-down t-Distribution VaR (AP1t)

Delta-Gamma VaR using Cornish-Fisher Expansion (AP1B)

Non-Parametric Bootstrap VaR (AP2)

Monte Carlo Simulation with EWMA Covariance (AP3)

Analytical Taylor Approximation with RiskMetrics (AP4)

Performance was evaluated using:

VaR violation rate (90% and 99%)

Kupiec's Unconditional Coverage Test

Christoffersen's Conditional Coverage Test

📈 2. Portfolio Construction & Risk Metrics
Built and evaluated three portfolio strategies:

Risk Parity Portfolio (RPP) using Component VaR

Maximum Diversification Portfolio (MDP) optimizing diversification ratio

Equally Weighted Portfolio (EWP) as benchmark

Performance metrics:

Metric	RPP	MDP	EWP
Sharpe Ratio	0.92	0.94	0.97
Max Drawdown	-0.70	-6.55	-19.29
VaR Violations (95%)	106–121	96–106	121–126
Skewness	-0.52	-0.55	-0.47
Excess Kurtosis	6.59	6.69	5.53

All return series rejected normality assumptions based on Shapiro-Wilk, K-S, and Jarque-Bera tests.

💵 3. Bond Risk Analysis
Computed 99% VaR and Expected Shortfall over 1 to 90 days for a bond using:

Exact revaluation

Delta and Delta-Gamma approximations

Monte Carlo simulations (10,000 paths)

Key insights:

Delta-Gamma approximation tracks full revaluation well for short horizons but underestimates risk at longer durations.

Probability of a 10% drop in bond price within 30 days: ~34.6%

ES (99%) over 90 days: £61.46

📌 Key Takeaways
Non-normal return distributions invalidate normal-based VaR models.

Risk Parity Portfolio offers stable performance and lower drawdowns, ideal for risk-averse investors.

Maximum Diversification delivers best Sharpe Ratio but higher downside risk.

Bootstrapping and Monte Carlo methods better capture fat tails and volatility clustering.

Analytical bond risk approximations become unreliable for longer horizons or larger YTM shifts.

📬 Contact
Lorenzo Rossi
📧 Email: lollordp@gmail.com
🔗 LinkedIn: Lorenzo Rossi
