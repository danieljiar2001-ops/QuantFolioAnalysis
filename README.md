# QuantFolio Analyzer

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)

A comprehensive quantitative financial analysis project analyzing ETF portfolios with Python, SQL, and Power BI.

## Project Overview

This project analyzes three major ETFs to understand their historical performance, risk characteristics, and diversification benefits:
- **IVV** (iShares Core S&P 500 ETF) - U.S. Large-Cap Stocks
- **IEF** (iShares 7-10 Year Treasury Bond ETF) - U.S. Government Bonds
- **GLD** (SPDR Gold Shares) - Physical Gold

The analysis includes:
- Data collection and preprocessing
- Returns calculation and visualization
- Statistical analysis and risk metrics
- Portfolio optimization insights
- Interactive Power BI dashboards (coming soon)

## Documentation

Detailed methodology and analytical framework available in [docs/methodology.md](docs/methodology.md).

## 📁 Project Structure
```bash
QuantFolioAnalyzer/
├── data/
│ ├── sample_data.csv
| ├── statistical_results.csv 
| ├── risk_summary.csv 
| ├── risk_metrics_summary.csv
| ├── backtest_results.csv
| ├── portfolio_weights.csv
| ├── portfolio_performance.csv
├── notebooks/ 
│ ├── 01_data_collection.ipynb
│ ├── 02_eda_cleaning.ipynb
│ ├── 03_statistical_analysis.ipynb
│ └── 04_portfolio_optimization.ipynb # New!
├── docs/ # Documentation
│ └── methodology.md
├── requirements.txt # Python dependencies
└── README.md
```
## Quick Start

### Option 1: Run on GitHub (View Only)
Simply browse the notebooks in order on GitHub. The analysis is fully documented.

### Option 2: Run Locally (Recommended)

1. **Clone the repository:**
```bash
git clone https://github.com/YOUR_USERNAME/QuantFolioAnalysis.git
cd QuantFolioAnalysis
```
2. **Install dependencies:**
```bash
pip install -r requirements.txt
```
3. **Launch Jupyter:**
```bash
jupyter notebook
```
4. **Run notebooks in order:**

Start with 01_data_collection.ipynb to understand data sourcing
Then run 02_eda_cleaning.ipynb for the analysis

## What's Included

### Notebook 1: Data Collection
- Downloads historical ETF data from Yahoo Finance (2005-2025)
- Uses yfinance library for reliable data fetching
- Saves data for reproducible analysis

### Notebook 2: Exploratory Data Analysis
- Price visualization: See how each ETF evolved over 20 years
- Returns calculation: Both simple and logarithmic returns
- Cumulative returns: Track growth of $1 investment
- Correlation analysis: Understand diversification benefits

### Notebook 3: Statistical Analysis (03_statistical_analysis.ipynb)
- Stationarity testing (ADF, KPSS tests)
- Normality testing (Jarque-Bera, Shapiro-Wilk)
- Volatility analysis with GARCH effects detection
- Autocorrelation analysis (returns, absolute returns, squared returns)
- Comprehensive risk metrics (Sharpe, Sortino, VaR, CVaR, Maximum Drawdown)

### Notebook 4: Portfolio Optimization (04_portfolio_optimization.ipynb)
- Modern Portfolio Theory implementation
- Efficient frontier visualization
- Optimal portfolios: Maximum Sharpe, Minimum Variance, Risk Parity
- Backtesting with $10,000 initial investment
- Performance comparison across market regimes

## Key Achivements

### Completed Analysis:
- 20-year historical analysis (2005-2025, ~5,200 trading days)
- Comprehensive statistical testing (ADF, KPSS, Jarque-Bera, Shapiro-Wilk)
- Advanced risk metrics (Sharpe, Sortino, CVaR, Maximum Drawdown, Omega Ratio)
- Volatility clustering and GARCH effects identification
- Correlation dynamics and diversification benefits analysis
- Modern Portfolio Theory implementation with efficient frontier
- Four optimized portfolios with backtesting results

### Key Findings:
- Non-Normal Distributions: All ETF returns reject normality (fat tails, skewness)
- Stationary Returns: Log returns are stationary (suitable for time series modeling)
- Volatility Clustering: GARCH effects present across all assets
- Diversification Benefits: Negative correlation between IVV and IEF during crises
- Optimal Allocation: Maximum Sharpe portfolio outperforms individual assets

### Optimal Portfolio Results:

| Portfolio | IVV | IEF | GLD | Return | Volatility | Sharpe | Max DD |
|-----------|-----|-----|-----|--------|------------|--------|--------|
| **Max Sharpe** | 58.3% | 35.2% | 6.5% | 8.92% | 12.45% | 0.716 | -34.2% |
| **Min Variance** | 24.1% | 68.5% | 7.4% | 6.21% | 6.89% | 0.611 | -15.8% |
| **Equal Weight** | 33.3% | 33.3% | 33.3% | 7.45% | 9.12% | 0.598 | -24.5% |
| **Risk Parity** | 42.7% | 48.1% | 9.2% | 7.89% | 8.34% | 0.706 | -19.3% |

## Next Steps Planned

- SQL database integration for results storage and querying
- Power BI dashboard for interactive visualization
- Automated data pipeline for daily updates

## Technical Details

### Data Source
- Provider: Yahoo Finance (free, reliable historical data)
- Frequency: Daily prices
- Adjustments: Auto-adjusted for splits and dividends
- Period: 2005-01-01 to 2025-10-01

### Key Calculations

- Simple Returns: $r_t = (P_t - P_{t-1}) / P_{t-1}$
- Logarithmic Returns: $\ln(P_t / P_{t-1})$
- Cumulative Returns: $(1 + r_1) \times (1 + r_2) \times ... \times (1 + r_n) - 1$
- Annualized Volatility: $\sigma_{\text{annual}} = \sigma_{\text{daily}} \times \sqrt{252}$
- Sharpe Ratio: $\frac{E[R] - R_f}{\sigma}$
- Maximum Drawdown: $\text{MDD} = \frac{\text{Trough} - \text{Peak}}{\text{Peak}}$

## Contributing
This is a learning project. Suggestions and improvements are welcome!

1. Fork the repository
2. Create a feature branch (git checkout -b feature/analysis-enhancement)
3. Commit changes (git commit -m 'Add some feature')
4. Push to branch (git push origin feature/analysis-enhancement)
5. Open a Pull Request

## Learning Resources
Yahoo Finance API Documentation
Pandas for Financial Analysis
Modern Portfolio Theory

## License
This project is for educational purposes. Data is sourced from Yahoo Finance.

## Live Dashboard (Coming Soon)
[![PowerBI Dashboard](https://img.shields.io/badge/PowerBI-Dashboard-yellow)](link-to-dashboard)

## Tech Stack
- **Data Collection**: yFinance, Yahoo Finance API
- **Analysis**: Pandas, NumPy, SciPy, Statsmodels
- **Visualization**: Matplotlib, Seaborn, Plotly
- **Database**: PostgreSQL/SQLite, SQLAlchemy
- **Dashboard**: PowerBI, Plotly Dash

🌟 Star this repo if you found it helpful!
📬 Contact: [dani.j.aracil@gmail.com]
🐛 Issues: Please use GitHub Issues for bug reports and feature requests
