# 🏠 Texas Housing Markets 2025  
**A Data-Centric Exploration of Texas Rental Trends, Pandemic Impact, and Affordability Forecasting**

---

## 📘 Overview
This repository is part of my **AI Engineer Roadmap (Month 1 – Week 2)** and serves as a real-world exercise in **NumPy + Pandas fluency**, applied to authentic Zillow housing market data for Texas metros.

The focus has now expanded beyond initial cleaning and visualization into **pandemic-period annotation, growth differentials, and forward forecasting**.  
Through this exploration, the project begins bridging the gap between *descriptive analytics* (what happened) and *predictive modeling* (what might happen next).

Ultimately, this work contributes toward building a **Texas Housing Affordability Index**, integrating rent, income, and mortgage trends.

---

## 🧩 Project Structure
```plaintext
texas-housing-markets-2025/
│
├── notebooks/
│   ├── Texas_Rent_Trends_Analysis_2015_2025.ipynb      # Original ZORI analysis & annual summaries
│   └── texas_housing_trends_analysis.ipynb              # Annotated pandemic visuals + forecasting models
│
├── data/
│   ├── raw/
│   │   └── Metro_zori_uc_sfrcondomfr_sm_month.csv       # Zillow ZORI dataset (public CSV)
│   └── processed/
│       └── texas_rent_trends_yearly.csv                 # Aggregated + YoY data (clean output)
│
├── visuals/
│   ├── zori_trends_texas.png                            # Base rent index plot
│   ├── yoy_rent_growth_texas.png                        # Year-over-year rent growth visualization
│   ├── texas_pandemic_annotation.png                    # 2020–2022 shaded annotation
│   ├── texas_growth_differentials.png                   # Pre- vs post-pandemic growth bar chart
│   └── austin_forecast_comparison.png                   # Linear vs exponential forecast example
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
```python
focus_metros = ['Austin, TX', 'Dallas, TX', 'Houston, TX', 'San Antonio, TX']
tx_focus = df_long[df_long['RegionName'].isin(focus_metros)]
```

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

## 🔍 Key Takeaways
- **Pandemic shock (2020–2022)** produced the steepest rent inflation in modern Texas history.  
- Post-2023 data indicates **softening demand** and **partial normalization**.  
- **Linear models** capture broad trajectory but miss inflection points.  
- **Exponential smoothing** adapts to short-term corrections, showing potential price stabilization or mild decline.  
- Defining **clear analytical questions** before modeling is essential:  
  > “Which pandemic-era effects will persist, and which will revert to pre-trend behavior?”

---

## 🚀 Next Steps
1. Integrate **Texas income + mortgage-rate datasets** to begin a prototype **Affordability Index**.  
2. Extend exponential models to all four metros for side-by-side comparison.  
3. Save finalized charts to `/visuals` and document within notebooks.  
4. Summarize results in a technical report or blog-style README section.  

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
| Oct 7 2025 | Visualization & YoY Analysis | Created annual summaries + growth plots. |
| Oct 9 2025 | Forecasting Phase Added | Annotated 2020–2022 period, quantified pre/post growth, implemented linear + exponential forecasts, and added new visuals. |
| Upcoming | Affordability Index Integration | Merge rent + income + mortgage data to compute Texas Affordability Index. |

---

## 🪶 Author
**Cleburn Walker**  
AI Engineer (in progress) | Real Estate Investor | Writer  
📍 Boerne, Texas  
🔗 [GitHub](https://github.com/cleburn) | [LinkedIn](https://linkedin.com/in/cleburnwalker)