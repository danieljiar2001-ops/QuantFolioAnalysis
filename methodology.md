# Methodology: Quantitative Analysis of ETFs

## Project Overview

This project analyzes three major Exchange-Traded Funds (ETFs) to understand their historical behavior, risk characteristics, and diversification potential. The analysis implements a comprehensive pipeline from data collection to predictive modeling.

## Analysis Universe: Three Core Asset Classes

### 1. **IVV** (iShares Core S&P 500 ETF) → U.S. Large-Cap Equities
- **Objective**: Tracks the S&P 500 Index (500 largest U.S. companies)
- **Characteristics**: 
  - High growth potential with significant volatility
  - Represents U.S. economic performance
  - Historically provided the highest long-term returns among the three
- **Role in Portfolio**: Growth/risk asset

### 2. **IEF** (iShares 7-10 Year Treasury Bond ETF) → U.S. Government Bonds
- **Objective**: Holds U.S. Treasury bonds with 7-10 year maturities
- **Characteristics**:
  - Lower volatility with steady income generation
  - Classic "flight to safety" asset during market stress
  - Negative correlation with stocks during crises (diversification benefit)
- **Role in Portfolio**: Income/stability asset

### 3. **GLD** (SPDR Gold Shares) → Physical Gold
- **Objective**: Direct exposure to gold bullion prices
- **Characteristics**:
  - Zero income generation (no dividends or interest)
  - Pure price appreciation asset
  - Inflation hedge and geopolitical uncertainty protection
  - Often moves independently of stocks and bonds
- **Role in Portfolio**: Inflation hedge/diversifier

## Data Specifications

### Time Period
- **Start**: 2005-01-01
- **End**: 2025-10-01
- **Duration**: Approximately 20 years

### Frequency
- **Primary**: Daily prices (≈5,200 trading days per ETF)
- **Basis for Analysis**: Adjusted closing prices

### Adjustments
All prices are **auto-adjusted** for:
- Stock splits
- Dividends
- Other corporate actions

This ensures accurate return calculations that reflect total investment returns.

### Source
- **Provider**: Yahoo Finance
- **API**: yFinance Python library
- **Reliability**: Widely used in academic and professional research

## Analytical Framework

### 1. Returns Calculation

#### Simple Returns
\[
r_t = \frac{P_t - P_{t-1}}{P_{t-1}}
\]

**Advantages**:
- Intuitive interpretation (percentage change)
- Directly relates to portfolio value changes

#### Logarithmic Returns
\[
l_t = \ln\left(\frac{P_t}{P_{t-1}}\right)
\]

**Advantages**:
- Time-additive: \(\sum l_t = \ln(P_T/P_0)\)
- Symmetric (log of 10% gain ≈ log of 10% loss in magnitude)
- Better statistical properties for modeling

#### Relationship
For small returns: \(l_t \approx r_t\)
For larger returns: \(l_t = \ln(1 + r_t)\)

### 2. Key Financial Concepts

#### Volatility
- **Definition**: Standard deviation of returns
- **Annualization**: \(\sigma_{\text{annual}} = \sigma_{\text{daily}} \times \sqrt{252}\)
- **Interpretation**: Measures investment risk/dispersion

#### Sharpe Ratio
\[
\text{Sharpe Ratio} = \frac{E[R] - R_f}{\sigma}
\]

**Components**:
- \(E[R]\): Expected return (annualized)
- \(R_f\): Risk-free rate (assumed 2% annual)
- \(\sigma\): Annualized volatility

**Interpretation**:
- >1.0: Excellent risk-adjusted return
- 0.5-1.0: Good
- 0-0.5: Acceptable
- <0: Poor

#### Maximum Drawdown
- **Definition**: Largest peak-to-trough decline
- **Formula**: \(\text{MDD} = \frac{\text{Trough} - \text{Peak}}{\text{Peak}}\)
- **Interpretation**: Worst historical loss experience

#### Value at Risk (VaR)
- **Definition**: Maximum loss at given confidence level
- **Calculation**: 5th percentile of return distribution (for 95% confidence)
- **Limitation**: Doesn't measure extreme tail losses

#### Conditional VaR (CVaR)
- **Definition**: Expected loss given VaR breach
- **Advantage**: Captures tail risk better than VaR

### 3. Statistical Tests

#### Stationarity Tests
- **ADF Test**: Tests for unit root (null: non-stationary)
- **KPSS Test**: Tests for stationarity (null: stationary)
- **Interpretation**: Returns should be stationary for time series modeling

#### Normality Tests
- **Jarque-Bera Test**: Tests skewness and kurtosis against normal distribution
- **Shapiro-Wilk Test**: General normality test
- **QQ Plots**: Visual comparison with normal distribution

#### Autocorrelation Tests
- **Ljung-Box Test**: Tests for autocorrelation in time series
- **ACF/PACF Plots**: Visualize correlation structure

## Analytical Pipeline

### Phase 1: Data Collection (`01_data_collection.ipynb`)
1. Environment setup and library imports
2. Parameter definition (tickers, date ranges)
3. Data download from Yahoo Finance
4. Initial storage in CSV format

### Phase 2: Exploratory Analysis (`02_eda_cleaning.ipynb`)
1. Data loading and price extraction
2. Returns calculation (simple and logarithmic)
3. Cumulative performance visualization
4. Correlation and covariance analysis
5. Enhanced analysis:
   - Rolling statistics (volatility, correlation)
   - Distribution analysis (skewness, kurtosis, normality tests)
   - Risk metrics calculation (Sharpe, Sortino, drawdowns, VaR)

### Phase 3: Statistical Analysis (`03_statistical_analysis.ipynb`)
1. Descriptive statistics
2. Stationarity testing (ADF, KPSS)
3. Normality testing and distribution analysis
4. Volatility analysis (rolling, EWMA, clustering)
5. Autocorrelation analysis (returns, absolute returns, squared returns)
6. Comprehensive risk assessment

### Phase 4: Advanced Modeling (`04_portfolio_optimization.ipynb`)
1. Portfolio optimization (Modern Portfolio Theory)
2. Time series forecasting (SARIMAX models)
3. Volatility modeling (GARCH family)
4. Machine learning applications 

## Technical Implementation

### Libraries Used
- **Data Manipulation**: pandas, numpy
- **Data Collection**: yfinance
- **Visualization**: matplotlib, seaborn
- **Statistics**: scipy, statsmodels
- **Machine Learning**: scikit-learn (future)

### Data Structure
```bash
data/
├── sample_data.csv # Raw OHLCV data
├── risk_metrics_summary.csv # Enhanced analysis results
└── statistical_results.csv # Statistical analysis results
```


### Reproducibility
- **Seed Setting**: Random seeds for reproducible results
- **Parameter Storage**: All parameters documented in notebooks
- **Version Control**: Git for tracking changes

## Assumptions and Limitations

### Key Assumptions
1. **Trading Days**: 252 days per year for annualization
2. **Risk-Free Rate**: 2% annual (approximate historical average)
3. **Liquidity**: All ETFs sufficiently liquid for daily trading
4. **Expense Ratios**: Ignored in return calculations (typically small)
5. **Taxes**: Not considered in analysis

### Limitations
1. **Historical Analysis**: Past performance ≠ future results
2. **Market Regimes**: Analysis spans multiple market regimes
3. **Transaction Costs**: Not included in return calculations
4. **Reinvestment**: Dividends assumed reinvested (via adjusted prices)
5. **Data Quality**: Dependent on Yahoo Finance accuracy

## Future Enhancements

### Planned Extensions
1. **Portfolio Optimization**: Efficient frontier calculation
2. **Predictive Modeling**: SARIMAX for return forecasting
3. **Risk Management**: Dynamic hedging strategies
4. **Alternative Data**: Integration of macroeconomic indicators

### Advanced Topics
1. **Regime Switching Models**: Capture different market states
2. **Copula Models**: Advanced dependence structure modeling
3. **Machine Learning**: Non-linear pattern recognition
4. **High-Frequency Data**: Intraday analysis possibilities

## References

### Academic Foundations
- Markowitz, H. (1952). Portfolio Selection
- Sharpe, W. F. (1966). Mutual Fund Performance
- Engle, R. F. (1982). Autoregressive Conditional Heteroskedasticity
- Bollerslev, T. (1986). Generalized Autoregressive Conditional Heteroskedasticity

### Practical Resources
- Yahoo Finance API Documentation
- pandas User Guide for Financial Analysis
- QuantConnect Educational Resources
- CFA Institute Research Foundation

---

*This methodology document will be updated as the analysis evolves. Last updated: December 2025*
