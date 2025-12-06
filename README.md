# Texas Housing Markets 2025

Analysis of rental trends across major Texas metros (Austin, Dallas, Houston, San Antonio) using Zillow ZORI data, with pandemic impact analysis and 2025-2028 forecasting.

## Key Findings

| Metro | 2019-2024 Change | Forecast Trend |
|-------|------------------|----------------|
| Dallas | +42% | Gradual cool-down |
| Austin | +37% | Plateau after surge |
| Houston | +29% | Stable, mild growth |
| San Antonio | +24% | Steady, most affordable |

## Methods

- **Pandemic annotation** - Quantified pre/post 2020-2022 growth differentials
- **Linear regression** - Long-term trend projection
- **Exponential smoothing (Holt)** - Near-term forecasts weighted toward recent data

## Tech Stack

Python · Pandas · NumPy · Matplotlib · Scikit-learn · Statsmodels

## Data Source

[Zillow ZORI](https://www.zillow.com/research/data/) - Observed Rent Index by metro
