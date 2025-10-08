# 🏠 Texas Housing Markets 2025  
**A Data-Centric Exploration of Texas Rental Trends and Affordability**

---

## 📘 Overview
This repository is part of the **AI Engineer Roadmap (Month 1 – Week 2)** and serves as a real-world exercise in **NumPy and Pandas fluency**, applied to authentic Texas housing market data.

The current focus is on analyzing **rental trends from 2015–2025** using Zillow’s **Zillow Observed Rent Index (ZORI)**.  
Our objective: to explore how Texas rental markets responded to the **2020 pandemic**, whether a **market correction** has occurred, and what **trajectory** appears most likely for the years ahead.

This analysis builds toward the broader goal of a **Texas Housing Affordability Index**, integrating rent, income, and mortgage data in future phases.

---

## 🧩 Project Structure
```plaintext
texas-housing-markets-2025/
│
├── notebooks/
│   └── Texas_Rent_Trends_Analysis_2015_2025.ipynb   # ZORI-based analysis & visualizations
│
├── data/
│   ├── raw/
│   │   └── Metro_zori_uc_sfrcondomfr_sm_month.csv   # Zillow ZORI dataset (public CSV)
│   └── processed/
│       └── texas_rent_trends_yearly.csv             # Aggregated + YoY data (clean output)
│
├── visuals/
│   ├── zori_trends_texas.png                        # Rent index plot
│   └── yoy_rent_growth_texas.png                    # Year-over-year growth visualization
│
└── README.md
```

---

## 🧠 Objectives
- Strengthen **Pandas data-wrangling** workflow with real-world housing data.  
- Transform monthly → annual → trend datasets for long-term market insight.  
- Visualize **rent growth and corrections** around the 2020 pandemic period.  
- Prepare clean, reusable datasets for integration with income and mortgage series.

---

## ⚙️ Methods & Workflow

### 1. Load Zillow ZORI Data
```python
url = "https://files.zillowstatic.com/research/public_csvs/zori/Metro_zori_uc_sfrcondomfr_sm_month.csv"
df = pd.read_csv(url)
```

### 2. Filter for Major Texas Metros
```python
texas_cities = ['Austin, TX', 'Dallas, TX', 'Houston, TX', 'San Antonio, TX']
df_tx = df[df['RegionName'].isin(texas_cities)]
```

### 3. Reshape, Clean, and Convert Dates
```python
df_tx_melted = df_tx.melt(id_vars=['RegionName','StateName'],
                          var_name='Date', value_name='ZORI')
df_tx_melted['Date'] = pd.to_datetime(df_tx_melted['Date'], format='%Y-%m-%d', errors='coerce')
```

### 4. Aggregate to Yearly Averages + YoY Growth
```python
df_tx_melted['Year'] = df_tx_melted['Date'].dt.year
df_yearly = (df_tx_melted.groupby(['RegionName','StateName','Year'], as_index=False)['ZORI'].mean())
df_yearly['YoY_%'] = df_yearly.groupby('RegionName')['ZORI'].pct_change() * 100
```

### 5. Visualize
- **Annual ZORI trends (2015–2025)**  
- **Year-over-Year rent-growth (%)**

---

## 🔍 Preliminary Insights
- All major Texas metros experienced **sharp rental acceleration 2020 → 2022**, aligned with pandemic-driven migration and supply shocks.  
- **Austin** showed the steepest rent inflation (~30 % YoY peak), followed by **Dallas and Houston**.  
- 2023–2025 indicates **partial normalization**, though median rents remain significantly above pre-pandemic baselines.  
- Trend extrapolation suggests **moderate continued growth** unless major economic tightening or housing supply expansion occurs.

---

## 🚧 Next Steps
1. **Annotate 2020–2022 pandemic period** in visualizations.  
2. **Quantify pre- vs post-pandemic growth differentials** per metro.  
3. **Model forward trajectory (2026–2028)** using linear regression or exponential smoothing.  
4. Integrate **income and mortgage rate datasets** for a Texas Affordability Index prototype.  
5. Document findings and visualization outputs in the repo’s `/visuals` directory.

---

## 🧭 Alignment with Long-Term Goals
This project directly contributes to the **Month 1 Capstone: “Texas Real Estate Investment Analyzer.”**  
By completing this phase, you’ll establish a solid foundation for modeling housing costs, income ratios, and affordability trends—skills essential for both **AI-driven analytics** and **data-backed investment strategy**.

---

## 🧰 Tools & Libraries
- **Python** (3.10+)  
- **NumPy**  
- **Pandas**  
- **Matplotlib**  
- **Jupyter Lab**

---

## 📈 Version History
| Date | Update | Description |
|------|---------|-------------|
| Oct 6 2025 | Initial Commit | Repository created with setup files. |
| Oct 7 2025 | Zillow ZORI Integration | Added raw Zillow ZORI dataset and `Texas_Rent_Trends_Analysis_2015_2025.ipynb` notebook. |
| Oct 7 2025 | Visualization & YoY Analysis | Aggregated to annual data, calculated YoY rent growth, and visualized Texas metro trends. |
| Upcoming | Affordability Index | Merge rent + income + mortgage data for affordability computation. |

---

## 🪶 Author
**Cleburn Walker**  
AI Engineer (in progress) | Real Estate Investor | Writer  
📍 Boerne, Texas  
🔗 [GitHub](https://github.com/cleburn) | [LinkedIn](https://linkedin.com/in/cleburnwalker)