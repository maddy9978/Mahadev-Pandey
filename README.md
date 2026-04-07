<img width="1536" height="1024" alt="ChatGPT Image Apr 7, 2026, 02_00_52 PM" src="https://github.com/user-attachments/assets/56bd95d4-a2c0-4ee0-87ea-ba20fef342f7" />[README_Amazon_Sales.md](https://github.com/user-attachments/files/26540489/README_Amazon_Sales.md)
# 📦 Amazon Sales Analysis — Python EDA + Power BI Dashboard

<img width="1536" height="1024" alt="ChatGPT Image Apr 7, 2026, 02_00_52 PM" src="https://github.com/user-attachments/assets/b938c664-85d9-4ca2-a408-cf4ce2682356" />

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Seaborn-4C8CBF?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
  <img src="https://img.shields.io/badge/Status-Completed-00897B?style=for-the-badge"/>
</p>

> An end-to-end sales analytics project on Amazon global sales data — combining Python EDA and a 3-page Power BI dashboard to uncover revenue trends, profitability drivers, regional performance, and operational inefficiencies across 7 regions, 12 product categories, and multiple countries.

---

## 📌 Problem Statement

Amazon operates across multiple global regions with diverse product categories and sales channels. Without proper data analysis, it becomes impossible to identify:
- Which regions and products are most profitable?
- Is Offline or Online channel performing better?
- Are there seasonal dips in revenue that need attention?
- Where is money being lost — high cost, low margin products?

This project answers all of these questions using real sales data.

---

## 🖼️ Dashboard Preview

### Page 1 — Sales Overview
<img width="1356" height="759" alt="image" src="https://github.com/user-attachments/assets/6d7b3e97-a77b-4837-ab80-7f411024cf08" />

### Page 2 — Trends & Priority Analysis
<img width="1341" height="747" alt="image" src="https://github.com/user-attachments/assets/081f2c52-680e-4660-af48-1b3605415edb" />


### Page 3  — Sales Performance Analysis
<img width="1331" height="744" alt="image" src="https://github.com/user-attachments/assets/b8f490ca-a356-4a15-802f-ae2896fa41d6" />




---

## 🗂️ Project Structure

```
amazon-sales-analysis/
│
├── 📁 data/
│   └── Amazon_Sales_data.csv         ← Dataset (100 records, 14 columns)
│
├── 📁 notebooks/
│   └── Analyzing_Amazon_Sales_data.ipynb  ← Python EDA (74 cells, 20 business questions)
│
├── 📁 powerbi/
│   └── Amazon_Sales_Dashboard.pbix   ← 3-page Power BI dashboard
│
├── 📁 screenshots/
│   ├── dashboard_page1.png           ← Sales Overview dashboard
│   └── dashboard_page2.png           ← Trends & Priority Analysis dashboard
│
└── README.md
```

---

## 📊 Dataset Overview

| Feature | Details |
|---|---|
| **Records** | 100 rows |
| **Columns** | 14 |
| **Time Period** | 2010 – 2017 |
| **Regions** | 7 (Sub-Saharan Africa, Europe, Asia, Australia & Oceania, Middle East & North Africa, Central America, North America) |
| **Item Types** | 12 (Cosmetics, Household, Office Supplies, Clothes, Baby Food, Cereal, etc.) |
| **Sales Channels** | Online / Offline |
| **Order Priority** | C (Critical) / H (High) / M (Medium) / L (Low) |

**Key Columns:** Region, Country, Item Type, Sales Channel, Order Priority, Order Date, Ship Date, Units Sold, Unit Price, Unit Cost, Total Revenue, Total Cost, Total Profit

---

## 🔧 Tools & Technologies

| Tool | Purpose |
|---|---|
| **Python 3** | Core programming language |
| **Pandas** | Data loading, cleaning, groupby aggregations |
| **NumPy** | Null value handling, numerical operations |
| **Matplotlib** | Bar, line, scatter, pie, boxplot visualizations |
| **Seaborn** | Styled heatmaps, barplots, lineplots |
| **Power BI** | Interactive 2-page dashboard with KPI cards, maps, donuts |
| **Jupyter Notebook / Google Colab** | Development environment |

---

## 📐 Methodology

```
Raw CSV Data
    ↓
Data Loading & Inspection (shape, dtypes, columns)
    ↓
Data Cleaning (null check, datetime conversion, mean imputation)
    ↓
Exploratory Data Analysis (20 Business Questions)
    ↓
Data Visualization (bar, line, pie, scatter, boxplot, heatmap)
    ↓
Power BI Dashboard (KPI cards, map, donut, trend line)
    ↓
Business Insights & Recommendations
```

---

## 💡 Key Business Insights

### 💰 Revenue & Profitability
- **Total Revenue: $137.35M** across 100 orders from 2010–2017
- **Overall Profit Margin: 32.2%** — healthy but with major variation by product
- **Sub-Saharan Africa** is the top revenue region at **$39.67M (28.9%)**, followed by Europe at **$33.37M**
- **North America** is the lowest revenue region at just **$5.64M** — significant growth opportunity

### 🏆 Product Performance
- **Cosmetics** is the #1 product by total profit — **$14.56M** in profit
- **Clothes** has the highest profit margin at **67.2%** — best return on cost
- **Meat** has the lowest profit margin at only **13.56%** — high cost, low return
- **Fruits** generates the least total profit at **$0.12M** — consider reducing inventory or repricing

### 🛒 Online vs Offline Channel
- **Offline dominates revenue** at **$79.09M (57.6%)** vs Online at **$58.25M (42.4%)**
- However, **Online orders ship in just 1.2 days** vs Offline at **18.1 days**
- Online channel is operationally far more efficient — scaling it could significantly reduce costs

### ⏱️ Operational Efficiency
- **Average order processing time: 9.6 days** across all channels
- The **18.1-day offline processing time** is a major operational bottleneck
- Reducing offline processing time to under 10 days could directly improve customer satisfaction

### 📅 Seasonal Trends
- **2012 had the highest revenue at $31.9M** — peak performance year
- Revenue has been declining since 2012 — from $31.9M down to $13.4M in 2017
- This signals a **strategic concern** — either market saturation, competition, or product mix issues
- **2011 was the weakest year at $11.1M** — likely an early-stage growth dip

### 🌍 Geographic Concentration Risk
- Top 5 countries by profit: Djibouti, Myanmar, Pakistan, Samoa, Honduras
- Heavy dependence on emerging markets — **North America and Europe are underperforming** relative to their market potential

---

## 📊 20 Business Questions Answered in EDA

| # | Business Question | Method Used |
|---|---|---|
| 1 | Which region has the highest total revenue? | `groupby` + `idxmax()` + line plot |
| 2 | Average unit price and cost by item type? | `groupby` + `mean()` + DataFrame |
| 3 | Which country has the highest total profit? | `groupby` + `idxmax()` + bar plot |
| 4 | How does sales channel affect order priority? | `groupby` + `value_counts()` + grouped bar |
| 5 | Average order processing time by channel? | Date subtraction + `groupby` + bar plot |
| 6 | Highest and lowest total sales by item type? | `idxmax()` + `idxmin()` + scatter plot |
| 7 | Order priority distribution by region? | `groupby` + `value_counts()` + bar plot |
| 8 | Correlation between unit price and profit? | `.corr()` coefficient |
| 9 | Seasonal trends in sales data? | `dt.month` + monthly groupby + bar plot |
| 10 | Units sold variation by country? | `groupby` + large bar plot |
| 11 | Total revenue variation by country? | `groupby` + bar plot |
| 12 | Unit price distribution by item type? | Pie chart |
| 13 | Which sales channel has highest avg unit price? | `groupby` + pie chart |
| 14 | Are there outliers in total cost? | **IQR Method** (Q1, Q3, fences) + boxplot |
| 15 | Total profit variation by item type? | `groupby` + sum |
| 16 | Average processing time by country? | `groupby` + mean |
| 17 | Highest avg revenue per order by region? | Derived column + `groupby` |
| 18 | Units sold vs total profit correlation? | `.corr()` coefficient |
| 19 | Order priority variation by item type? | `groupby` + `value_counts()` |
| 20 | Revenue trend over years 2010–2017? | Date extraction + yearly groupby |

---

## 📋 Power BI Dashboard Summary

### Page 1 — Sales Overview
- **6 KPI Cards:** Total Units Sold (513K), Avg Unit Price ($27.68K), Avg Unit Cost ($19.10K), Total Revenue ($137.35M), Total Profit ($44.17M), Total Cost ($93.18M)
- **Bar Chart:** Total Revenue by Region — Sub-Saharan Africa leads at $40M
- **Horizontal Bar Chart:** Total Profit by Item Type — Cosmetics at $14.56M dominates
- **World Map:** Country-level revenue bubbles showing geographic concentration
- **3 Donut Charts:** Online vs Offline split for Revenue, Profit, and Units Sold

### Page 2 — Trends & Priority Analysis
- **6 KPI Cards:** Average metrics for Cost, Profit, Revenue, Unit Cost, Unit Price, Units Sold
- **Line Chart:** Units Sold trend from 2010–2017 showing fluctuation patterns
- **Donut Chart:** Revenue breakdown by Item Type — Cosmetics = 26.65% share
- **Clustered Bar Chart:** Order Priority count by Region (Critical/High/Medium/Low breakdown)

- ### Page 3 – Sales Performance Analysis
- **Region Table:** Regional comparison of Sum of Unit Price, with Sub-Saharan Africa leading at 9.35K
- **Pie Chart:** Item Type contribution to Sum of Unit Price – Office Supplies holds the largest share at 28.24%, followed by Household and Cosmetics
- **Stacked Column Chart:** Total Profit by Item Type and Sales Channel – Cosmetics is the most profitable category across Online and Offline sales
- **Funnel Chart:** Total Cost by Item Type – Office Supplies, Household, and Cosmetics are the highest cost-driving categories
- **Stacked Bar Chart:** Total Profit by Order Priority and Item Type – High priority orders contribute the highest profit, led mainly by Cosmetics and Household




---

## 🚀 How to Run This Project

1. Clone the repository:
   ```bash
   git clone https://github.com/maddy9978/amazon-sales-analysis.git
   ```

2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

3. Open the notebook:
   ```bash
   jupyter notebook notebooks/Analyzing_Amazon_Sales_data.ipynb
   ```
   Or open directly in Google Colab.

4. Open `powerbi/Amazon_Sales_Dashboard.pbix` in Power BI Desktop.
   - If data source error: **Transform Data → Data Source Settings → update CSV path**

---

## 🎯 Business Recommendations

1. **Scale Online Channel** — 1.2-day processing vs 18.1-day offline is a massive advantage. Invest in online marketing and inventory management.
2. **Push Cosmetics and Clothes** — Highest profit and margins. Increase SKUs and regional availability.
3. **Review Meat and Fruits Strategy** — Margins of 13.56% and 25.83% are weak. Consider price revision or discontinuation.
4. **Expand in North America** — Only $5.64M revenue from the world's largest consumer market. Major untapped opportunity.
5. **Investigate Post-2012 Revenue Decline** — Revenue halved from $31.9M (2012) to $13.4M (2017). Root cause analysis needed.
6. **Reduce Offline Processing Time** — 18.1 days is unacceptable in modern e-commerce. Target under 7 days.

---

## 📬 Contact

**Mahadev Pandey** | mohitpandey535@gmail.com | [LinkedIn](https://www.linkedin.com/in/YOUR_LINKEDIN) | [GitHub](https://github.com/maddy9978)
