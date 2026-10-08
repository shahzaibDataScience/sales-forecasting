# 📈 Sales Forecasting (Time Series Basics)

Predict future daily store sales from past sales — learning the core ideas of **time series** analysis: trend, seasonality, and time-based splitting.

## What you'll learn

- What a **time series** is and why the order of rows matters
- How to reveal a **trend** with a rolling mean
- How to find **seasonality** by grouping on weekday
- Why you must **NEVER shuffle** a time series when splitting train/test
- How to build **baseline forecasts** (naive, moving average) and score them with **MAE**

## Dataset

`data/daily_sales.csv` — 1095 days of daily sales, generated with seed 42:

| Column | Meaning |
|---|---|
| Date | the day (2024-01-01 → 2026-12-31) |
| Sales | units sold that day |

The data contains a steady upward trend, weekend seasonality (weekends ≈ 1.4× weekdays), and random noise.

## How to run

```bash
pip install -r requirements.txt
jupyter notebook sales_forecasting.ipynb
```

## Key findings

- Clear **upward trend** over 3 years (30-day rolling mean)
- Strong **weekly seasonality**: weekends are the busiest days
- Time-based split: first 1035 days train, last 60 days test
- **7-day moving average beats the naive forecast** on MAE — because it captures the weekly rhythm

## 🎓 Explain it yourself

1. Why must you never shuffle a time series before splitting into train and test?
2. What is the difference between *trend* and *seasonality*? Give an example of each from this data.
3. What does a 30-day rolling mean do, and why is it useful?
4. What is MAE, and why is "lower is better"?
5. The 7-day average beat the naive baseline here — in what situation might the naive forecast win instead?
