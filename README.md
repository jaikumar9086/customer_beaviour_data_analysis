# Customer Shopping Behavior Analysis

An end-to-end data analytics project: Python for cleaning and EDA, PostgreSQL for business queries, Power BI for an interactive dashboard, plus a written report and a presentation built with Gamma.

---

## Overview

This project analyzes **3,900 retail transactions** to understand how customers spend, which groups bring in the most revenue, which products sell best, and how subscriptions and discounts affect buying behavior.

**Goal:** turn raw transaction data into clear insights a business can act on.

**Key questions answered**
- Who spends more: male or female customers?
- Do subscribers spend more than non-subscribers?
- Which products are rated highest and which depend most on discounts?
- Which age groups and categories drive the most revenue?
- How many customers are New, Returning or Loyal?

---

## Dataset

| Detail | Info |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Missing values | 37 in `Review Rating` |
| Source | *Add your source link here (e.g. Kaggle)* |

**Column groups**
- **Customer:** age, gender, location, subscription status
- **Purchase:** item purchased, category, purchase amount (USD), season, size, color
- **Behavior:** discount applied, promo code used, previous purchases, purchase frequency, review rating, shipping type, payment method

---

## Tools

| Purpose | Tool |
|---|---|
| Data cleaning and EDA | Python (`pandas`) |
| Database and queries | PostgreSQL (SQL) |
| Dashboard | Power BI |
| Report | PDF / Word |
| Presentation | Gamma |

---

## Steps

1. **Load the data** into a pandas DataFrame.
2. **Explore** the structure with `df.info()` and `df.describe()`.
3. **Clean the data**
   - Filled missing `Review Rating` values with the median rating of each product category.
   - Renamed all columns to `snake_case`.
4. **Feature engineering**
   - Created `age_group` by binning customer ages.
   - Created `purchase_frequency_days` from the purchase frequency column.
5. **Check for redundancy:** `discount_applied` and `promo_code_used` were duplicates, so `promo_code_used` was dropped.
6. **Load into PostgreSQL** directly from Python.
7. **Run 10 business queries** in SQL (listed below).
8. **Build the Power BI dashboard** from the cleaned data.
9. **Write the report** and **create the presentation** in Gamma.

**SQL questions covered**
1. Revenue by gender
2. High-spending customers who used discounts
3. Top 5 products by average rating
4. Standard vs. Express shipping spend
5. Subscribers vs. non-subscribers
6. Most discount-dependent products
7. Customer segmentation (New / Returning / Loyal)
8. Top 3 products in each category
9. Repeat buyers and subscription status
10. Revenue by age group

---

## Dashboard

An interactive Power BI dashboard with filters for **subscription status, gender, category and shipping type**.

**Includes**
- KPI cards: number of customers, average purchase amount, average review rating
- Customers by subscription status (donut chart)
- Revenue and sales by category
- Revenue and sales by age

![Customer Behavior Dashboard](images/dashboard.png)

> Save your dashboard screenshot as `images/dashboard.png` so it shows here.

---

## Results

| Metric | Finding |
|---|---|
| Customers | 3.9K |
| Average purchase amount | $59.76 |
| Average review rating | 3.75 |
| Revenue by gender | Male $157,890 vs. Female $75,191 |
| Subscribers | 1,053 customers, avg spend $59.49 |
| Non-subscribers | 2,847 customers, avg spend $59.87 |
| Shipping | Express avg $60.48 vs. Standard avg $58.46 |
| Top-rated items | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| Most discount-reliant items | Hat (50.00%), Sneakers (49.66%), Coat (49.07%) |
| Customer segments | Loyal 3,116 / Returning 701 / New 83 |
| Highest-revenue age group | Young Adult ($62,143) |

**Recommendations**
- Promote exclusive subscriber benefits to grow subscriptions.
- Reward repeat buyers with a loyalty program.
- Review discount policy to balance sales and margins.
- Feature top-rated and best-selling products in campaigns.
- Target high-revenue age groups and express-shipping users.

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

**2. Install Python libraries**
```bash
pip install pandas numpy sqlalchemy psycopg2-binary jupyter
```

**3. Run the Python notebook**
Open the notebook and run all cells to clean the data and load it into PostgreSQL.
```bash
jupyter notebook
```
Update the database connection (username, password, database name) in the notebook before running.

**4. Run the SQL queries**
Open `sql/queries.sql` in pgAdmin (or any SQL client) and run the queries on the loaded table.
*MySQL and SQL Server also work with small syntax changes.*

**5. Open the dashboard**
Open `dashboard/customer_behaviour_dashboard.pbix` in Power BI Desktop.

---

## Project Structure

```
├── data/                 # raw and cleaned dataset
├── notebook/             # Python cleaning and EDA
├── sql/                  # SQL queries
├── dashboard/            # Power BI file (.pbix)
├── images/               # dashboard screenshot
├── report/               # project report (PDF)
└── README.md
```

---

## Author

**Jai**
New Delhi, India
LinkedIn: *add link* | Email: jaisingh1352001@gmail.com
