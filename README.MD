# Sentiment and Short-Horizon Returns (StockNet)

This project studies whether **Twitter-derived sentiment** contains explanatory power for **short-horizon equity returns**, and how this relationship varies across **volatility regimes**. The analysis is exploratory and research-oriented, using panel data regression and regime-based comparisons.

---

## Dataset

We use the **StockNet** dataset, which pairs two years of Twitter activity with aligned daily market data for **88 U.S. equities** across **nine sectors**.

- **Text side:** Tweets are aggregated into a daily sentiment signal.
- **Market side:** We use short-horizon returns, recent realized volatility, and lagged returns.

The final cleaned dataset contains **10,000+ observations** (ticker–date panel).  
The original cleaning script was lost, so the preprocessing steps are documented below.

---

## Features Used

- `ticker`: equity identifier  
- `date`: trading date  
- `sent_weighted`: daily aggregated sentiment score  
- `ret_5d`: forward 5-day return (target)  
- `past_ret_5d`: lagged 5-day return  
- `past_vol_5d`: realized volatility over the previous 5 days  

---

## Data Preparation (Notebook)

1. **Parsing and sorting**
   - Convert `date` to datetime
   - Sort by `ticker` and `date`

2. **Filtering**
   - Retain only the fields listed above
   - Drop rows with missing values

3. **Winsorization**
   - All continuous variables are winsorized at the 1st and 99th percentiles to reduce the influence of outliers

4. **Volatility regimes**
   - Assets are grouped into `low`, `mid`, and `high` volatility regimes using terciles of `past_vol_5d`

5. **Binning for visualization**
   - Sentiment is rank-transformed and split into deciles for nonparametric analysis

---

## Methodology

### Regression Analysis

We estimate OLS regressions with **HAC (Newey–West) standard errors** to account for heteroskedasticity and serial correlation induced by overlapping return horizons.

Baseline specification:
