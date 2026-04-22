<img width="1536" height="1024" alt="ChatGPT Image Apr 7, 2026, 12_09_11 AM" src="https://github.com/user-attachments/assets/7cb631f0-32f2-4ec8-b88e-0ba0e42fb979" />
[README_Customer_Behavior.md](https://github.com/user-attachments/files/26531576/README_Customer_Behavior.md)
# 🛒 Customer Behavior Analysis

<p align="left">
  <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
  <img src="https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white"/>
  <img src="https://img.shields.io/badge/RFM%20Analysis-00897B?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Completed-00897B?style=for-the-badge"/>
</p>

> A customer segmentation and behavioral analytics project using **RFM (Recency, Frequency, Monetary)** methodology — helping businesses identify high-value customers, detect churn risk, and drive targeted marketing decisions.

---

## 📌 Problem Statement

Businesses often treat all customers the same — same discounts, same campaigns, same messaging. This project proves that **not all customers are equal** and segments them using data to enable personalized, ROI-driven strategies.

---

## 🎯 Key Business Questions Answered

- Who are the **top 20% of customers** driving 80% of revenue? (Pareto Analysis)
- Which customers are **at risk of churning** and need re-engagement?
- What is the **average order value and purchase frequency** by segment?
- Which **product categories** drive repeat purchases?
- How has **customer acquisition and retention** trended over time?

---

## 🖼️ Dashboard Preview

> 📸 <img width="1380" height="755" alt="image" src="https://github.com/user-attachments/assets/6fe85b03-d1b3-4fb5-9c00-5799e5b0ce71" />





---

## 🗂️ Project Structure

```
customer-behavior-analysis/
│
├── 📁 data/
│   ├── raw/
│   │   └── customer_transactions.csv
│   └── processed/
│       └── rfm_scores.csv
│
├── 📁 sql/
│   ├── 01_data_exploration.sql
│   ├── 02_rfm_calculation.sql
│   ├── 03_customer_segments.sql
│   └── 04_cohort_analysis.sql
│
├── 📁 powerbi/
│   └── Customer_Behavior_Dashboard.pbix
│
├── 📁 screenshots/
│   ├── 01_overview.png
│   └── 02_rfm_segments.png
│
└── README.md
```

---

## 🔧 Tools & Technologies

| Tool | Purpose |
|---|---|
| **SQL** | RFM scoring, cohort analysis, window functions |
| **Power BI Desktop** | Multi-page interactive dashboard |
| **DAX** | Segmentation measures, time intelligence, ranking |
| **Power Query** | Data cleaning and transformation |

---

## 📐 RFM Methodology

**RFM Score** is calculated for each customer across 3 dimensions:

| Dimension | Definition | Scoring |
|---|---|---|
| **Recency (R)** | Days since last purchase | 1 (oldest) → 5 (most recent) |
| **Frequency (F)** | Number of purchases | 1 (least) → 5 (most) |
| **Monetary (M)** | Total spend value | 1 (lowest) → 5 (highest) |

**Customer Segments:**

| Segment | RFM Pattern | Strategy |
|---|---|---|
| 🏆 Champions | R5, F5, M5 | Reward & upsell |
| 💛 Loyal Customers | R4-5, F3-5 | Loyalty program |
| ⚠️ At Risk | R2-3, F3-5 | Win-back campaigns |
| 😴 Lost | R1-2, F1-2 | Reactivation or drop |
| 🌱 New Customers | R5, F1 | Onboarding nurture |

---

## 📊 Key SQL Snippet — RFM Calculation

```sql
WITH rfm_base AS (
    SELECT
        CustomerID,
        DATEDIFF(CURDATE(), MAX(OrderDate))   AS Recency,
        COUNT(DISTINCT OrderID)                AS Frequency,
        SUM(OrderValue)                        AS Monetary
    FROM orders
    GROUP BY CustomerID
),
rfm_scored AS (
    SELECT *,
        NTILE(5) OVER (ORDER BY Recency DESC)    AS R_Score,
        NTILE(5) OVER (ORDER BY Frequency ASC)   AS F_Score,
        NTILE(5) OVER (ORDER BY Monetary ASC)    AS M_Score
    FROM rfm_base
)
SELECT *,
    CONCAT(R_Score, F_Score, M_Score) AS RFM_Segment
FROM rfm_scored;
```

---

## 📊 Key DAX Measures

```dax
-- RFM Segment Label
Customer Segment =
SWITCH(
    TRUE(),
    [R_Score] >= 4 && [F_Score] >= 4, "Champion",
    [R_Score] >= 3 && [F_Score] >= 3, "Loyal",
    [R_Score] <= 2 && [F_Score] >= 3, "At Risk",
    [R_Score] <= 2 && [F_Score] <= 2, "Lost",
    "New Customer"
)

-- Revenue from Champions
Champion Revenue =
CALCULATE(
    SUM(FactOrders[OrderValue]),
    Customers[Segment] = "Champion"
)
```

---

## 💡 Key Insights Uncovered

1. **Top 18% of customers** (Champions + Loyals) generate **72% of total revenue** — classic Pareto pattern confirmed
2. **At-Risk segment** (284 customers) represents ₹8.4 L in revenue at churn risk — targeted re-engagement could recover 30–40%
3. **Average order frequency drops 60%** after 90 days of inactivity — ideal trigger point for automated win-back campaigns
4. **New customers** have a 34% repeat purchase rate within 60 days — onboarding experience is the key leverage point
5. **Weekend purchases** are 22% higher in value than weekday orders — timing promotions to weekends can boost AOV

---

## 🚀 How to Run This Project

1. Clone this repository:
   ```bash
   git clone https://github.com/maddy9978/customer-behavior-analysis.git
   ```
2. Run SQL scripts in `/sql/` folder in order (01 → 04)
3. Export `rfm_scores.csv` from your SQL output into `/data/processed/`
4. Open `powerbi/Customer_Behavior_Dashboard.pbix` in Power BI Desktop
5. Update data source path if needed: **Transform Data → Data Source Settings**

---

## 📬 Contact

**Mahadev** | mohitpandey535@gmail.com | [LinkedIn](https://linkedin.com/in/YOUR_LINKEDIN)
