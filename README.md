# 🏠 Texas Housing Markets 2025  
**A Data-Centric Exploration of Texas Rental Trends, Pandemic Impact, and Affordability Forecasting**

---

## 📘 Overview
This repository is part of my **AI Engineer Roadmap (Month 1 – Week 2)** and serves as a real-world exercise in **NumPy + Pandas fluency**, applied to authentic Zillow housing market data for Texas metros.

The focus has now expanded beyond initial cleaning and visualization into **pandemic-period annotation, growth differentials, and forward forecasting**.  
This exploration bridges the gap between descriptive analytics (what happened) and predictive modeling (what’s likely ahead).

Ultimately, this work contributes toward building a **Texas Housing Affordability Index**, integrating rent, income, and mortgage trends.

---

## 🧩 Project Structure
```plaintext
texas-housing-markets-2025/
│
├── notebooks/
│   ├── Texas_Rent_Trends_Analysis_2015_2025.ipynb      # Original ZORI analysis & annual summaries
│   └── texas_housing_trends_analysis.ipynb              # Annotated pandemic visuals + forecasting models (Austin + all metros)
│
├── data/
│   ├── raw/
│   │   └── Metro_zori_uc_sfrcondomfr_sm_month.csv       # Zillow ZORI dataset (public CSV)
│   └── processed/
│       └── texas_rent_trends_yearly.csv                 # Aggregated + YoY data (clean output)
│
├── visuals/
│   ├── zori_trends_texas.png                            # Baseline rent index plot (2015–2025)
│   ├── yoy_rent_growth_texas.png                        # Year-over-year rent growth visualization
│   ├── texas_pandemic_annotation.png                    # 2020–2022 shaded pandemic impact chart
│   ├── texas_growth_differentials.png                   # Pre- vs post-pandemic growth comparison
│   ├── austin_forecast_comparison.png                   # Linear vs exponential forecast for Austin
│   ├── austin_tx_holt_forecast.png                      # Austin exponential smoothing forecast (2025–2028)
│   ├── dallas_tx_holt_forecast.png                      # Dallas exponential smoothing forecast (2025–2028)
│   ├── houston_tx_holt_forecast.png                     # Houston exponential smoothing forecast (2025–2028)
│   ├── san_antonio_tx_holt_forecast.png                 # San Antonio exponential smoothing forecast (2025–2028)
│   └── forecast_all_texas.png                           # Combined 2×2 grid of all metro forecasts
│
└── README.md
```

---

## 🧠 Objectives
- Strengthen **data wrangling + visual storytelling** through Pandas and Matplotlib.  
- Quantify **pre-, during-, and post-pandemic market behavior**.  
- Compare **modeling approaches** (Linear Regression vs Exponential Smoothing).  
- Build reusable, transparent code pipelines for future affordability modeling.  
- Practice version-controlled, reproducible data-science workflow in GitHub.

---

## ⚙️ Methods & Workflow

### 1. Load & Reshape Zillow ZORI Data
Converted the dataset from *wide → long* format using `pd.melt()`, creating a tidy time series for all U.S. metros.

### 2. Filter for Texas Metros
['Austin, TX', 'Dallas, TX', 'Houston, TX', 'San Antonio, TX']

### 3. Visualize Baseline Trends
Created multi-line plots for the four major metros showing 2015–2025 rental trajectories.

### 4. Annotate Pandemic Period (2020–2022)
Added shaded regions to visualize the pandemic’s disruption window.

### 5. Quantify Pre- vs Post-Pandemic Growth
Calculated 2019 vs 2023–2024 average rent levels per metro and percentage change, revealing Dallas > Austin > Houston > San Antonio in relative growth.

### 6. Forecast Future Trajectory (2026–2028)
Implemented two forecasting paradigms:
- **Linear Regression** → projects a steady, long-term trend.  
- **Exponential Smoothing (Holt)** → gives recent data more weight, illustrating near-term corrections.

The contrast between these models demonstrates how **model choice encodes assumptions** about market momentum and recency weighting.

---

### 📊 Results Summary & Reflections  

Across four major Texas metros, the exponential-smoothing models captured near-term market behavior more responsively than the linear baseline:  

| Metro | 2019 → 2024 % Change | Near-Term Trend (2025–2028) | Observation |
|-------|----------------------|------------------------------|--------------|
| Austin | ≈ +37 % | Slight softening → plateau | Pandemic surge moderating but remains above trend |
| Dallas | ≈ +42 % | Gradual cool-down | Maintains strong upward momentum |
| Houston | ≈ +29 % | Stable → mild growth | Less volatile market response |
| San Antonio | ≈ +24 % | Steady low growth | Consistent affordability advantage |

**Key Insights**
- Exponential smoothing emphasizes recent corrections, revealing early signs of stabilization across Texas rental markets.  
- Linear models offer a useful long-run anchor but can’t adapt to post-pandemic deceleration.  
- Pandemic (2020–22) remains the clear structural break point for Texas housing costs.  
- 2023–25 data suggests markets are normalizing rather than reverting fully to pre-trend levels.  

**Reflection**
This week deepened my fluency with NumPy and Pandas for time-series work, expanded my understanding of forecasting models in practice, and reinforced how data-driven storytelling bridges technical and business insight. Completing the multi-city pipeline and automated chart generation marks the first fully-reproducible data product in my AI Engineer roadmap. 

---

## 🧭 Alignment with Long-Term Goals
This project advances the **Month 1 Capstone** in the *AI Engineer Roadmap*:  
> “Texas Real Estate Investment Analyzer.”  

It demonstrates practical command of **data cleaning, EDA, visualization, and simple forecasting**, all foundational for later ML and API-based real-estate intelligence systems.

---

## 🧰 Tools & Libraries
- **Python (3.10+)**  
- **NumPy**, **Pandas**  
- **Matplotlib**, **Seaborn**  
- **Scikit-Learn** (Linear Regression)  
- **Statsmodels** (Holt Exponential Smoothing)  
- **Jupyter Lab**

---

## 📈 Version History
| Date | Update | Description |
|------|---------|-------------|
| Oct 6 2025 | Initial Commit | Repo created with baseline structure. |
| Oct 7 2025 | ZORI Integration | Added raw dataset + first analysis notebook. |
| Oct 8 2025 | Visualization & YoY Analysis | Created annual summaries + growth plots. |
| Oct 9 2025 | Forecasting Phase Added | Annotated 2020–2022 period, quantified pre/post growth, implemented linear + exponential forecasts, and added new visuals. |
| Oct 10 2025 | Multi-City Forecast Expansion | Added Holt Exponential Smoothing for all four metros + combined visualization grid.|

---

## 🪶 Author
**Cleburn Walker**  
AI Engineer (in progress) | Real Estate Investor | Writer  
📍 Boerne, Texas  
🔗 [GitHub](https://github.com/cleburn) | [LinkedIn](https://linkedin.com/in/cleburnwalker)