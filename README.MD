# Sentiment and Short-Horizon Returns (StockNet)

This project explores whether Twitter-derived sentiment helps explain short-horizon equity returns, and how this relationship changes across different volatility regimes.

---

## Dataset

We use the StockNet dataset, which pairs two years of Twitter activity with daily market data for 88 U.S. equities across nine sectors. Tweets are aggregated into a daily sentiment measure, and market data includes short-horizon returns, recent realized volatility, and lagged returns.

The dataset used in this project contains over 10,000 cleaned ticker–date observations.

---

## What I Did

- Cleaned and filtered the StockNet dataset  
- Aggregated sentiment at the daily level  
- Constructed forward 5-day returns, lagged returns, and recent volatility measures  
- Winsorized variables to reduce the influence of outliers  
- Grouped observations into low-, mid-, and high-volatility regimes  
- Ran regressions to test whether sentiment adds explanatory power beyond recent price dynamics  
- Visualized return behavior across sentiment levels and volatility regimes  

---

## Tools

- Python  
- pandas  
- numpy  
- matplotlib  
- statsmodels  

---

## Notes

This is an exploratory analysis intended for research and learning purposes, not a trading strategy.

---

## Author

Indranil Biswas  
Applied Mathematics, Stony Brook University
