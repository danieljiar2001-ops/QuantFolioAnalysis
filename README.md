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

## 🚀 Getting Started

### Prerequisites
- Python 3.9+
- Git
- Jupyter Notebook/Lab

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/QuantFolioAnalyzer.git
cd QuantFolioAnalyzer
