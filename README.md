# Portfolio Optimization with Modern Portfolio Theory

![Python](https://img.shields.io/badge/python-3.9+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## Project Overview

Professional portfolio optimization system implementing Markowitz's Modern Portfolio Theory. Uses quadratic optimization to construct efficient portfolios that maximize risk-adjusted returns across 10 diversified stocks.

## Key Features

- Efficient frontier generation (10,000 simulated portfolios)
- Convex optimization for optimal asset allocation
- Risk metrics: VaR, CVaR, Beta, Maximum Drawdown
- Backtesting on historical data
- Professional visualizations with Plotly

## Results

### Portfolio Performance

| Portfolio | Return | Volatility | Sharpe Ratio |
|-----------|--------|------------|--------------|
| **Max Sharpe** | **38.06%** | 17.14% | **2.10** |
| Equal Weight | 18.09% | 11.95% | 1.35 |
| Min Volatility | 12.34% | 10.19% | 1.01 |

### Key Findings

**Maximum Sharpe Portfolio (Sharpe 2.10 - Exceptional):**
- Top 10% performance vs professional hedge funds
- Optimal allocation: JPM 41%, GOOGL 36%, JNJ 10%, Others 13%
- Significantly outperforms S&P 500 benchmark (Sharpe ~0.5-0.8)

**Minimum Volatility Portfolio:**
- Lowest risk at 10.19% volatility
- Defensive allocation: KO 26%, JNJ 18%, PG 14%
- Ideal for capital preservation

### What Makes These Results Strong

- **Sharpe 2.10:** Exceptional risk-adjusted returns (professional target: 1.5-2.0)
- **Intelligent diversification:** Balanced across tech, finance, and defensive sectors
- **Realistic assumptions:** 3 years historical data, 2% risk-free rate
- **Controlled volatility:** 17% vol for 38% return is excellent

## Stock Universe

10 stocks across 5 sectors:
- Tech: AAPL, MSFT, GOOGL
- Finance: JPM, BAC
- Consumer: PG, KO
- Healthcare: JNJ, UNH
- Energy: XOM

Benchmark: SPY (S&P 500)

## Mathematical Framework

**Portfolio Return:** Rp = Σ(wi × Ri)

**Portfolio Variance:** σp² = w'Σw

**Sharpe Ratio:** S = (Rp - Rf) / σp

## Technologies

- **PyPortfolioOpt:** Mean-variance optimization
- **yfinance:** Automated data download
- **NumPy/Pandas:** Numerical analysis
- **Plotly:** Interactive visualizations
- **CVXPY:** Convex optimization backend

## Quick Start
```bash
# Clone repository
git clone https://github.com/tomwbrg/portfolio-optimization.git
cd portfolio-optimization

# Install dependencies
pip install -r requirements.txt

# Run notebook
jupyter notebook notebooks/portfolio_optimization.ipynb
```

Data downloads automatically - no manual setup required.

## Project Structure
```
portfolio-optimization/
├── notebooks/
│   └── portfolio_optimization.ipynb    # Complete analysis
├── requirements.txt
└── README.md
```

## Real-World Applications

- **Asset Management:** Institutional portfolio construction
- **Wealth Management:** Client-specific allocations
- **Risk Management:** Portfolio risk assessment
- **Quantitative Finance:** Research and strategy development

Used by hedge funds and asset managers for optimal capital allocation.

## Future Improvements

- Factor-based optimization (Fama-French factors)
- Transaction cost modeling
- Dynamic rebalancing strategies
- Regime-dependent allocations
- Constraints on sector exposure

## Disclaimer

Educational project demonstrating Modern Portfolio Theory implementation. Past performance does not guarantee future results. Consult financial professionals before making investment decisions.

## License

MIT License

## Author

**Tom Weinberg**
- GitHub: [@tomwbrg](https://github.com/tomwbrg)

## Acknowledgments

- Harry Markowitz for Modern Portfolio Theory
- PyPortfolioOpt library for optimization tools
- Yahoo Finance for historical data

---

*Professional quantitative finance project showcasing optimization, risk management, and data-driven investment strategies.*
