Independent researcher in statistical finance. Public work below - multi-asset correlation and volatility analysis, equity options risk analytics. Hand-rolled implementations validated against reference libraries; limitations stated alongside each method.

## Projects

### [Options Risk Dashboard](https://github.com/alexeyklek10/Options_Risk_Dashboard) - [live demo](https://optionsriskdashboard-habdkbmbe7f7gckmsqunii.streamlit.app/)

Streamlit app and methodology notebook for multi-source options-chain analytics on US-listed equity options. Multi-provider aggregation (yfinance, optional Tradier and Polygon) with cross-source validation; hand-rolled Black-Scholes-Merton pricer and seven Greeks (delta, gamma, vega, theta, rho, vanna, charm); Manaster-Koehler initial guess plus Newton-Raphson on vega with Brent fallback for the IV solver. Eleven views including IV surface, 25-delta skew, max pain, gamma exposure under the SqueezeMetrics dealer-sign convention, Breeden-Litzenberger implied PDF, and a multi-leg strategy builder. Closed-form Greeks validated against `py_vollib` on a 1024-point Sobol grid.

### [Security Analysis: Correlation and Volatility](https://github.com/alexeyklek10/Security_Analysis)

Two Jupyter notebooks analysing correlation structure and volatility regimes across a multi-asset ETF book. Multi-method historical correlation (Pearson, Spearman, Kendall, RiskMetrics EWMA) with tail-regime correlation at the 5th, 10th, and 15th percentile of anchor returns. Seven OHLC volatility estimators including Garman-Klass, Yang-Zhang, and GARCH(1,1) with persistence and half-life. Bias-corrected Hurst exponent (Anis-Lloyd 1976), Lo-MacKinlay variance ratio, PCA plus entropy-based ENB diversification scorecard, hierarchical clustering with Mantegna's ultrametric distance.

## Stack

Python (NumPy, SciPy, pandas, Plotly, Streamlit, arch, yfinance), pytest, mypy, ruff, black, GitHub Actions, Docker.

## Contact

alexeyklek@gmail.com
