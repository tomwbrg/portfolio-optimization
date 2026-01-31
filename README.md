# Markowitz Portfolio Optimization

A Monte Carlo approach to mean-variance portfolio optimization.

## Objective

This project implements a simple Markowitz portfolio optimization using Monte Carlo simulation. It identifies optimal long-only portfolios (maximum Sharpe ratio and minimum volatility) from a universe of 5 stocks, then backtests the resulting allocations against an equal-weight portfolio and the S&P 500 benchmark.

## Asset Universe

| Ticker | Sector |
|--------|--------|
| AAPL | Technology |
| MSFT | Technology |
| JNJ | Healthcare |
| PG | Consumer Staples |
| JPM | Financials |

**Benchmark:** SPY (S&P 500 ETF)

## Data

- **Source:** Yahoo Finance (adjusted close prices)
- **Period:** January 2018 to present (~7 years)
- **Frequency:** Daily

## Methodology

### Returns Computation
- Daily simple returns: `r_t = (P_t / P_{t-1}) - 1`
- **Annual return:** Compounded (CAGR), not arithmetic mean
  - `CAGR = (cumulative_return)^(1/years) - 1`
- **Annual volatility:** `std(daily_returns) * sqrt(252)`
- **Sharpe ratio:** `(CAGR - Rf) / volatility`
  - Risk-free rate: 3% annual

### Portfolio Optimization
- Monte Carlo simulation of 10,000 random portfolios
- Constraints: long-only (weights >= 0), fully invested (weights sum to 1)
- Identification of:
  - **Max Sharpe portfolio:** highest risk-adjusted return
  - **Min Volatility portfolio:** lowest annualized standard deviation

### Backtesting
- Initial investment: $10,000
- Strategies compared:
  - Max Sharpe portfolio
  - Min Volatility portfolio
  - Equal-weight portfolio (20% each)
  - SPY benchmark
- Metrics: total return, CAGR, volatility, Sharpe ratio, maximum drawdown

## Project Structure

```
portfolio-optimization/
├── notebooks/
│   └── portfolio_optimization.ipynb
├── requirements.txt
└── README.md
```

## Requirements

```
numpy
pandas
yfinance
matplotlib
```

## Usage

```bash
pip install -r requirements.txt
jupyter notebook notebooks/portfolio_optimization.ipynb
```

Data downloads automatically from Yahoo Finance.

## Limitations

- Optimization is based on historical data; future performance may differ.
- Monte Carlo sampling approximates the efficient frontier but may not find the global optimum.
- Transaction costs and rebalancing frictions are not modeled.
- Results are sensitive to the sample period chosen.

## License

MIT License

## References

- Markowitz, H. (1952). Portfolio Selection. *The Journal of Finance*, 7(1), 77-91.
