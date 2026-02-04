# Trader Performance vs Market Sentiment Analysis

## Overview
This project investigates the relationship between Bitcoin market sentiment (Fear/Greed Index) and trader behavior and performance on Hyperliquid. The aim is to find insights that can be used to develop more intelligent trading systems.

---

## Dataset

### 1) Fear & Greed Index
- Columns: date, classification, value  
- Daily sentiment label (Fear / Greed / etc.)

### 2) Hyperliquid Historical Trades
- 200k+ trade records  
- Includes PnL, size, side, timestamps, and trader account

---

## Methodology

### Data Cleaning
- Dropped duplicates
- Renamed columns to be consistent
- Converted timestamp columns to datetime format
- Aggregated trades to **daily trader level**

### Feature Engineering
Traders' most important metrics on a daily basis:
- Daily PnL
- Win rate
- Average trade size (USD)
- Number of trades
- Long/short ratio
- Sentiment score
- Lagged PnL
- Rolling win rate
- PnL volatility

### Merge
Merged trader data with sentiment data on daily date.

---

## Modeling
Target:
- Binary classification: above-median daily profitability

Model:
- Random Forest (hyperparameter-optimized)

Validation:
- 80/20 split with stratification

---

## How to Run

1. Clone repo
2. Install dependencies:

```bash
pip install pandas numpy matplotlib scikit-learn

Place datasets in project folder

Run:python analysis.py