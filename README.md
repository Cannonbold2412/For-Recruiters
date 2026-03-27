# Trading Strategy Analysis Portfolio

A collection of quantitative trading strategy implementations and backtesting frameworks demonstrating expertise in algorithmic trading, technical analysis, and performance optimization.

## Overview

This repository showcases advanced trading strategy development and analysis across multiple asset classes including Indian equities (NSE) and commodities (Gold/XAU). The projects demonstrate proficiency in:

- Quantitative strategy development using technical indicators
- High-performance backtesting with parallel processing
- Risk management and portfolio optimization
- Statistical analysis and performance metrics
- Data visualization and reporting

## Projects

### 1. Accumulation/Distribution Strategy - NSE Equities
**File:** `Accumulation_Distribution.ipynb`

A sophisticated intraday trading strategy for 48 NSE stocks using accumulation phase detection combined with momentum breakouts.

**Key Features:**
- **Technical Indicators:** ADX, MFI, ATR, VWAP with custom implementations using NumPy
- **Strategy Logic:**
  - Detects accumulation phases (low volatility, high volume periods)
  - Triggers breakout trades on momentum confirmation
  - Fixed risk per trade (0.8% of capital)
  - ATR-based take profit with 3:1 risk-reward ratio
- **Performance:**
  - Dataset: 42.8M rows across 48 tickers (2015-2024)
  - 23,419 trades executed
  - Parallel processing using Joblib for optimal speed
- **Risk Management:**
  - Fixed percentage stop-loss (3% of capital)
  - Dynamic position sizing based on risk
  - Slippage and brokerage modeling (0.01% and 0.1%)

**Technical Highlights:**
- Efficient vectorized calculations for indicator computation
- Rolling window analysis for accumulation detection
- Intraday time-based filters (no entries after 15:15, force exit at 15:25)

### 2. JMA Gold Strategy - XAU/USD
**File:** `JMA_Gold.ipynb`

A mean-reversion strategy for gold trading using Jurik Moving Average (JMA) with normalized signals and volatility filtering.

**Key Features:**
- **Custom JMA Implementation:** Smooth exponential moving average with adaptive period
- **Signal Generation:**
  - Z-score normalization (90-period window)
  - Rogers-Satchell volatility estimator
  - Threshold-based entry signals (long: >2.0, short: <-2.5)
- **Dataset:** 6.5M rows of 1-minute gold data (2004-2025), resampled to 15-minute bars
- **Backtesting Results:**
  - 51 trades over 5-year period (2020-2025)
  - 10% take profit, 2% stop loss
  - Final P&L: ₹107,293 (107.3% return)
  - Transaction costs included (0.04% fee, 0.05% slippage)

**Advanced Features:**
- **Hyperparameter Optimization:**
  - Grid search across 8 parameters
  - Multi-objective scoring: Profit/Drawdown ratio, R², monthly consistency
  - Total combinations tested with parallel processing
- **Statistical Metrics:**
  - Equity curve R² for smoothness evaluation
  - Monthly return consistency (mean/std)
  - Composite scoring function for optimization

### 3. Tradebook Analysis Framework v2
**File:** `Tradebook_analysis_v2.ipynb`

A comprehensive, production-ready analysis framework for evaluating trading performance across any market.

**Key Features:**
- **Universal Compatibility:**
  - Auto-detects column names from multiple formats
  - Supports equities, crypto, futures, forex
  - Works in Google Colab and local Jupyter environments
- **Performance Metrics:**
  - Win rate, profit factor, expectancy
  - Sharpe, Sortino, and Calmar ratios
  - Drawdown analysis (absolute, percentage, duration)
  - Time-in-market calculations
- **Visualizations (17 types):**
  - P&L distributions and heatmaps
  - Cumulative equity curves with drawdown
  - Rolling Sharpe ratio per ticker
  - Hourly, daily, weekly, monthly breakdowns
  - Volatility regime analysis
  - Correlation matrices
- **Risk Analysis:**
  - Monte Carlo simulation (10,000 paths)
  - Margin call risk calculator
  - Weighted portfolio analysis
  - Benchmark comparison

**Technical Excellence:**
- Robust error handling and data validation
- Configurable parameters through single config dict
- Interactive Plotly visualizations
- Professional formatting and reporting

**Example Results:**
- Sample dataset: 341 trades (ICICIBANK, 2022-2024)
- Total return: 28.39%
- Sharpe ratio: 1.742
- Win rate: 51.91%
- Max drawdown: 14.61%

## Technical Stack

**Languages & Libraries:**
- **Python 3.x**
- **Data Processing:** Pandas, NumPy
- **Visualization:** Plotly, Matplotlib, Seaborn
- **Performance:** Joblib (parallel processing), tqdm (progress tracking)
- **Machine Learning:** Scikit-learn (for metric calculations)

**Development Environment:**
- Google Colab for cloud-based execution
- Jupyter Notebook for local development

## Key Competencies Demonstrated

1. **Quantitative Analysis:**
   - Technical indicator implementation from scratch
   - Statistical analysis and hypothesis testing
   - Time series analysis and pattern recognition

2. **Software Engineering:**
   - High-performance computing with parallel processing
   - Clean, modular, and reusable code
   - Comprehensive error handling and validation
   - Configuration-driven design

3. **Financial Modeling:**
   - Risk management and position sizing
   - Transaction cost modeling (slippage, brokerage)
   - Portfolio optimization and diversification
   - Performance attribution analysis

4. **Data Engineering:**
   - Efficient handling of large datasets (40M+ rows)
   - Memory-optimized operations
   - Data cleaning and preprocessing pipelines

5. **Visualization & Reporting:**
   - Professional-grade interactive charts
   - Multi-dimensional analysis dashboards
   - Clear communication of complex concepts

## Related Projects

This portfolio complements other repositories:
- **CONPAY:** Payment processing and financial transaction systems
- **CONWEB:** Web application development

## Usage

Each notebook is self-contained and includes:
- Detailed markdown documentation
- Configuration sections for easy customization
- Step-by-step execution flow
- Comprehensive output analysis

To run any notebook:
1. Open in Google Colab or Jupyter
2. Update the file paths in the configuration section
3. Run all cells sequentially

## Performance Note

The strategies shown are for educational and demonstration purposes. Past performance does not guarantee future results. All backtests include realistic transaction costs and slippage assumptions.

## Contact

This repository is maintained as a portfolio showcase. For professional inquiries or collaboration opportunities, please reach out through GitHub.

---

**Note:** All data and results are based on historical simulations for demonstration purposes.
