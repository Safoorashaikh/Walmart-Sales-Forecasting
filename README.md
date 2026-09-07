# Walmart-Sales-Forecasting
A data science capstone project analyzing weekly sales across Walmart stores and forecasting future sales using time-series models (ARIMA/SARIMA).
                                        
## Problem Statement
A retail chain with multiple outlets struggles to match inventory supply with demand across stores. This project uses historical sales data to generate actionable insights and build forecasting models to predict sales for upcoming weeks/months.

## Objectives
1. Derive insights from historical sales data that individual stores can use to improve performance.
2. Forecast weekly sales for each store for the next 12 weeks.

## Dataset
The dataset contains weekly sales records with the following features:

| Column | Description |
|---|---|
| Store | Store identifier |
| Date | Week of sales |
| Weekly_Sales | Sales for the store that week |
| Holiday_Flag | Whether the week included a holiday |
| Temperature | Temperature on the day of sale |
| Fuel_Price | Regional fuel cost |
| CPI | Consumer Price Index |
| Unemployment | Regional unemployment rate |

## Approach
1. **Data Cleaning & Inspection** — checked shape, types, nulls, duplicates.
2. **Exploratory Data Analysis** — correlation analysis (sales vs. unemployment, temperature, CPI, fuel price), top/bottom performing stores, seasonal trend analysis.
3. **Stationarity Testing** — Augmented Dickey-Fuller (ADF) test, differencing to achieve stationarity.
4. **Modeling** — ARIMA and SARIMA models (order selection via `pmdarima.auto_arima`, ACF/PACF plots).
5. **Forecasting** — generated a 12-week sales forecast per store.

## Key Insights
- Weekly sales show measurable correlation with unemployment, most notably at Store 32 and Store 40.
- Sales vary widely by store — Store 20 is the top performer, Store 33 the lowest.
- Sales exhibit clear seasonality, peaking around holiday periods and dipping in summer/winter.

## Why ARIMA & SARIMA
ARIMA (AutoRegressive Integrated Moving Average) and SARIMA (Seasonal ARIMA) were chosen because they explicitly model trend and, in SARIMA's case, seasonality — both of which are present in this weekly retail sales data.

## Tech Stack
- Python, pandas, NumPy
- matplotlib, seaborn (visualization)
- statsmodels (ADF test, ACF/PACF, SARIMAX)
- pmdarima (automatic ARIMA order selection)

## Future Business Applications
- Targeted holiday promotions and in-store events to capitalize on seasonal peaks.
- Corrective interventions for consistently underperforming stores.
- Festival-season campaigns (contests, bundled offers) aligned with observed demand spikes.
