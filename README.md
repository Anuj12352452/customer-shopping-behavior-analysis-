# 📊 Customer Shopping Behavior Analysis

A complete, beginner-friendly, end-to-end data analytics portfolio project using **Python**, **SQL (PostgreSQL)**, and **Power BI**.

---

## 🧠 Business Problem

A retail company wants to understand its customers' shopping behavior to improve sales, engagement, and long-term loyalty. Management has noticed changes in purchasing patterns across demographics, product categories, and sales channels.

**Core business question:**
> *"How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?"*

---

## 🗂️ Project Structure

```
customer-behavior-analysis/
│
├── 📄 README.md                              ← You are here
├── 📄 LICENSE.txt
│
├── 📁 data/
│   ├── customer_shopping_behavior.csv        ← Raw dataset (3,900 rows)
│   └── customer_shopping_cleaned.csv         ← Output of Python cleaning step
│
├── 📁 python/
│   └── Customer_Shopping_Behavior_Analysis.py  ← Full data cleaning script
│
├── 📁 sql/
│   └── customer_behavior_sql_queries.sql     ← 10 business questions + bonus query
│
├── 📁 powerbi/
│   └── customer_behavior_dashboard.pbix      ← Interactive Power BI dashboard
│
└── 📁 report/
    └── Customer_Shopping_Behavior_Report.docx ← Full written report
```

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python (pandas, matplotlib, seaborn) | Data cleaning, feature engineering, EDA |
| PostgreSQL + pgAdmin | Database storage and SQL analysis |
| Power BI Desktop | Interactive dashboard and visualizations |
| SQLAlchemy + psycopg2 | Python → PostgreSQL connection |

---

## 📦 Dataset Overview

| Property | Value |
|----------|-------|
| Source | [Kaggle – Consumer Behavior and Shopping Habits](https://www.kaggle.com/) |
| Rows | 3,900 transactions |
| Columns | 18 features |
| Missing Data | 37 values in `Review Rating` |

**Key columns:**

- **Demographics:** Age, Gender, Location, Subscription Status  
- **Purchase Details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color  
- **Behavior:** Discount Applied, Previous Purchases, Frequency of Purchases, Shipping Type, Review Rating, Payment Method  

---

## 🚀 How to Run This Project

### Step 1 — Python: Data Cleaning

**Requirements:**
```bash
pip install pandas matplotlib seaborn sqlalchemy psycopg2-binary
```

**Run the script:**
```bash
python python/Customer_Shopping_Behavior_Analysis.py
```

This will:
- Load and explore the raw CSV
- Rename columns to snake_case
- Fill 37 missing `review_rating` values using category median
- Drop the redundant `promo_code_used` column
- Create two new columns: `age_group` and `purchase_frequency_days`
- Save the cleaned data to `data/customer_shopping_cleaned.csv`
- Generate `eda_charts.png` with 4 exploratory charts
- (Optional) Load data into PostgreSQL — see Section 11 in the script

---

### Step 2 — SQL: Business Analysis

1. Install [PostgreSQL](https://www.postgresql.org/download/) and [pgAdmin](https://www.pgadmin.org/)
2. Create a database called `customer_db`
3. Load the data by uncommenting Section 11 in the Python script and running it
4. Open `sql/customer_behavior_sql_queries.sql` in pgAdmin
5. Run each query one at a time and review the results

---

### Step 3 — Power BI: Dashboard

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
2. Open Power BI → **Get Data** → **PostgreSQL database**
3. Enter: Server = `localhost`, Database = `customer_db`
4. Select the `customer` table → **Load**
5. Open `powerbi/customer_behavior_dashboard.pbix`

**Dashboard visuals included:**
- 3 KPI cards: Total Customers · Average Purchase Amount · Average Review Rating
- Donut chart: Subscription Status (27% Yes / 73% No)
- Bar chart: Revenue by Category
- Bar chart: Revenue by Age Group
- Bar chart: Sales Volume by Category and Age Group
- Slicers: Gender · Category · Subscription Status · Shipping Type

---

### Step 4 — Report

Open `report/Customer_Shopping_Behavior_Report.docx` — it contains:
- Full project summary
- All 10 SQL findings with result tables
- 5 business recommendations with justification
- Dashboard screenshots

---

## 📈 Key Findings

| # | Finding |
|---|---------|
| 1 | Male customers generate **2× more revenue** ($157,890 vs $75,191) |
| 2 | **80% of customers are Loyal** (3,116 out of 3,900) |
| 3 | Only **27% subscribe** despite nearly identical average spend |
| 4 | **Hat, Sneakers, Coat** are discounted ~50% of the time — margin risk |
| 5 | **Young Adults (18–25)** generate the most revenue at $62,143 |
| 6 | Express shipping users spend **$2 more** per order than Standard |
| 7 | Even among repeat buyers (>5 purchases), **72% don't subscribe** |
| 8 | **Clothing** dominates revenue across all categories |

---

## ✅ Business Recommendations

1. **Grow Subscriptions** — Only 27% subscribe despite equal spending. Launch exclusive subscriber benefits (early access, free shipping) to boost sign-ups, especially targeting the 2,518 repeat buyers who don't yet subscribe.

2. **Reward Loyal Customers** — 80% of customers are Loyal. A points-based loyalty program with milestone rewards would strengthen retention and prevent churn to competitors.

3. **Review Discount Policy** — Hat, Sneakers, Coat and Sweater are discounted ~49–50% of the time. A/B test removing discounts on these items — many customers may buy at full price, significantly improving margins.

4. **Target Young Adults** — 18–25 year olds generate the highest total revenue ($62,143). Invest in social media, influencer partnerships and digital advertising aimed at this demographic.

5. **Upsell Express Shipping** — Express users spend $2 more per order on average. Promote express shipping at checkout with messaging like "Get it faster for just $X more" to increase average order value.

---

## 📊 Dashboard Preview

> *(Add a screenshot of your Power BI dashboard here after building it)*
> 
> To add: Take a screenshot of your dashboard → save as `dashboard_preview.png` → update this line:
> 
> `![Dashboard Preview](dashboard_preview.png)`

---

## 💡 What I Learned

- How to clean real-world messy data using **pandas**
- How to write **CTEs and Window Functions** in SQL (ROW_NUMBER, PARTITION BY)
- How to build an **interactive Power BI dashboard** connected to a live database
- How to translate data findings into **actionable business recommendations**

---

## 📜 License

MIT — see `LICENSE.txt`. Free to fork, star, and use in your own portfolio.

---

## 👤 Author

Anuj thakkar 
