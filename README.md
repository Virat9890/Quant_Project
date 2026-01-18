# Quantitative Trading Strategy using Market Regime Detection and Machine Learning

## 📌 Project Overview
This project implements an end-to-end **quantitative trading system** on **NIFTY 50 intraday data (5-minute interval)**.  
The system combines **technical indicators**, **options-based features**, **market regime detection using Hidden Markov Models (HMM)**, and **machine learning (XGBoost)** to improve trading performance.

The goal is to demonstrate skills in:
- Data engineering
- Feature engineering
- Regime detection
- Algorithmic trading strategy design
- Machine learning–based trade filtering
- Statistical trade analysis

---

## 📊 Data Description

### Datasets Used
| Dataset | Description |
|------|------------|
| NIFTY Spot (5-min) | Intraday OHLC data |
| NIFTY Futures (5-min) | Derived futures prices & open interest |
| NIFTY Options (5-min) | Simulated ATM Call & Put data |

> **Note:**  
> Due to the unavailability of free historical intraday futures and options data, futures prices were derived from spot prices using cost-of-carry approximation, and options data was simulated for ATM strikes for academic analysis. This approach is commonly accepted in academic and research-oriented projects.

---

## 📁 Project Structure

Quant_Trading_Project/
│
├── data/
│ ├── nifty_spot_5min_cleaned.csv
│ ├── nifty_futures_5min.csv
│ ├── nifty_options_5min.csv
│ ├── nifty_merged_features_5min.csv
│ ├── nifty_with_regime_5min.csv
│ ├── trades_log.csv
│ └── trades_with_ml_prediction.csv
│
├── notebooks/
│ ├── 02_data_cleaning.ipynb
│ ├── 03_futures_data_creation.ipynb
│ ├── 04_options_data_creation.ipynb
│ ├── 05_data_merging_and_features.ipynb
│ ├── 06_regime_detection.ipynb
│ ├── 07_trading_strategy_backtest.ipynb
│ ├── 08_ml_trade_filter.ipynb
│ └── 09_outlier_trade_analysis.ipynb
│
├── models/
│ └── xgboost_model.pkl
│
├── plots/
│ ├── equity_curve.png
│ ├── pnl_vs_duration.png
│ ├── outlier_boxplot.png
│ └── feature_correlation.png
│
├── results/
│ ├── strategy_metrics.txt
│ └── outlier_insights.txt
│
└── README.md

Methodology
🔹 1. Data Cleaning

Timestamp alignment

Missing value handling using forward fill

Removal of invalid candles

Market hours filtering

Outlier filtering using Z-score

🔹 2. Feature Engineering

EMA (5, 15)

Spot & futures returns

Futures basis

Average IV and IV spread

Put-Call Ratio (OI & Volume based)

🔹 3. Market Regime Detection

Gaussian Hidden Markov Model (3 states)

Regimes classified as:

+1 → Uptrend

0 → Sideways

-1 → Downtrend

Regime labeling based on average spot returns

🔹 4. Trading Strategy

EMA (5/15) crossover strategy

Regime-based filtering

No trades during sideways regime

Intraday backtesting

🔹 5. Machine Learning Enhancement

Binary classification of trade profitability

XGBoost classifier

Time-series–aware feature selection

Trades filtered using confidence threshold (>0.5)

🔹 6. Outlier Trade Analysis

Identification of high-performance trades using 3-sigma rule

Analysis across:

Market regime

Time of day

Volatility & PCR

Trade duration

Name: Virat
Role: Aspiring Quant / ML Engineer
Submission: Quantitative Trading Strategy Assignment