# 📊 QuantFolio Analyzer

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)

A comprehensive quantitative financial analysis project analyzing ETF portfolios with Python, SQL, and Power BI.

## 📋 Project Overview

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

## 📁 Project Structure

QuantFolioAnalyzer/
├── data/
│ ├── raw/ # Raw downloaded data
│ └── processed/ # Cleaned and processed data
├── notebooks/ # Jupyter notebooks for analysis
│ ├── 01_data_collection.ipynb
│ ├── 02_eda_cleaning.ipynb
│ ├── 03_statistical_analysis.ipynb
│ └── 04_portfolio_optimization.ipynb
├── src/ # Reusable Python modules
│ ├── data_fetcher.py
│ ├── analysis_utils.py
│ └── visualization.py
├── docs/ # Documentation
│ └── methodology.md
├── requirements.txt # Python dependencies
├── .gitignore
└── README.md

## 🚀 Quick Start

### Option 1: Run on GitHub (View Only)
Simply browse the notebooks in order on GitHub. The analysis is fully documented.

### Option 2: Run Locally (Recommended)

1. **Clone the repository:**
```bash
git clone https://github.com/YOUR_USERNAME/QuantFolioAnalysis.git
cd QuantFolioAnalysis

2. **Install dependencies:**

pip install -r requirements.txt

3. **Launch Jupyter:**

jupyter notebook

4. **Run notebooks in order:**

Start with 01_data_collection.ipynb to understand data sourcing

Then run 02_eda_cleaning.ipynb for the analysis

## 📊 What's Included

### Notebook 1: Data Collection

- Downloads historical ETF data from Yahoo Finance (2005-2025)
- Uses yfinance library for reliable data fetching
- Saves data for reproducible analysis

### Notebook 2: Exploratory Data Analysis

- Price visualization: See how each ETF evolved over 20 years
- Returns calculation: Both simple and logarithmic returns
- Cumulative returns: Track growth of $1 investment
- Correlation analysis: Understand diversification benefits

## 📈 Key Insights (So Far)
1. Price Evolution (2005-2025)
IVV: Shows strong long-term growth with cyclical patterns

IEF: Steady, low-volatility growth typical of bonds

GLD: "Safe-haven" asset with inflation-resistant properties

2. Correlation Structure
IVV and GLD show moderate correlation

IEF shows negative correlation with IVV (diversification benefit)

These relationships inform portfolio construction

## 🔮 Next Steps Planned

- Statistical Analysis - Volatility, stationarity tests, Sharpe ratios
- Portfolio Optimization - Markowitz efficient frontier
- SQL Integration - Store and query data efficiently
- Power BI Dashboard - Interactive visualizations
- Risk Metrics - VaR, CVaR, maximum drawdown

## 🛠️ Technical Details

### Data Source
- Provider: Yahoo Finance (free, reliable historical data)
- Frequency: Daily prices
- Adjustments: Auto-adjusted for splits and dividends
- Period: 2005-01-01 to 2025-10-01

### Key Calculations
- Simple returns: r_t = (P_t - P_{t-1}) / P_{t-1}
- Logarithmic returns: ln(P_t / P_{t-1})
- Cumulative returns: (1 + r_1) × (1 + r_2) × ... × (1 + r_n) - 1

## 🤝 Contributing
This is a learning project. Suggestions and improvements are welcome!

1. Fork the repository
2. Create a feature branch (git checkout -b feature/analysis-enhancement)
3. Commit changes (git commit -m 'Add some feature')
4. Push to branch (git push origin feature/analysis-enhancement)
5. Open a Pull Request

## 📚 Learning Resources
Yahoo Finance API Documentation
Pandas for Financial Analysis
Modern Portfolio Theory

## 📝 License
This project is for educational purposes. Data is sourced from Yahoo Finance.
