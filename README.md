Independent researcher in statistical finance. Public work below - systematic trend-following with live broker execution, multi-asset correlation and volatility analysis, equity options risk analytics. Hand-rolled implementations validated against reference libraries; limitations stated alongside each method.

## Projects

### [Trend Following: Research and Live IG Execution](https://github.com/alexeyklek10/Trend_following)

Single repository combining a systematic trend-following research package and its live IG broker integration as a sub-package, so backtest and live signals cannot silently diverge. Universe of 43 liquid futures-tracking CFDs plus a 5-instrument equity/macro overlay. Signal is a moving-average crossover (20/80-day on non-equity, 50/200 on equity), z-score normalised over 252 days with a hysteresis entry/exit band; TSMOM, Donchian breakout, regime filters and noise filters were tested in the research sweep and dropped from the champion. Equal Risk Contribution (correlation-aware) sizing rescaled to a 10% annualised portfolio volatility target; 1.5x ATR trailing stop with 1.0 ATR activation and 40-day minimum holding. Walk-forward over 2015-2024 with permutation significance testing: single-MA-pair champion at OOS Sharpe 1.68; a two-MA-speed stack (50/200 + 100/200) reaches 2.17. Live runs the single-tier variant. Live daily orchestrator runs against IG via the `trading-ig` client; hard-coded protocols enforced as gates between pipeline stages (HALT kill-switch, data-freshness and gap guards, per-account layer attribution, 35% max-order sanity cap). ~1,220 tests across research and live; two independent code-audit passes; two documented incidents (silent data failure 2026-04-22; layer attribution 2026-04-20/21) with postmortems. Live paper-trading on two IG demo accounts since 2026-04-12; not running real money.

### [Options Risk Dashboard](https://github.com/alexeyklek10/Options_Risk_Dashboard) - [live demo](https://optionsriskdashboard-habdkbmbe7f7gckmsqunii.streamlit.app/)

Streamlit app and methodology notebook for multi-source options-chain analytics on US-listed equity options. Multi-provider aggregation (yfinance, optional Tradier and Polygon) with cross-source validation; hand-rolled Black-Scholes-Merton pricer and seven Greeks (delta, gamma, vega, theta, rho, vanna, charm); Manaster-Koehler initial guess plus Newton-Raphson on vega with Brent fallback for the IV solver. Eleven views including IV surface, 25-delta skew, max pain, gamma exposure under the SqueezeMetrics dealer-sign convention, Breeden-Litzenberger implied PDF, and a multi-leg strategy builder. Closed-form Greeks validated against `py_vollib` on a 1024-point Sobol grid.

### [Security Analysis: Correlation and Volatility](https://github.com/alexeyklek10/Security_Analysis)

Two Jupyter notebooks analysing correlation structure and volatility regimes across a multi-asset ETF book. Multi-method historical correlation (Pearson, Spearman, Kendall, RiskMetrics EWMA) with tail-regime correlation at the 5th, 10th, and 15th percentile of anchor returns. Seven OHLC volatility estimators including Garman-Klass, Yang-Zhang, and GARCH(1,1) with persistence and half-life. Bias-corrected Hurst exponent (Anis-Lloyd 1976), Lo-MacKinlay variance ratio, PCA plus entropy-based ENB diversification scorecard, hierarchical clustering with Mantegna's ultrametric distance.

## Stack

Python (NumPy, SciPy, pandas, statsmodels, Plotly, Streamlit, arch, numba, yfinance, trading-ig), pytest, mypy, ruff, black, GitHub Actions, Docker.

## Contact

alexeyklek@gmail.com
