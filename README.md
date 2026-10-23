# Customer Shopping Behavior Analysis

An end-to-end data analytics project: clean and explore retail customer data in **Python**, analyze it with **SQL (PostgreSQL)**, and present the results in a **Power BI dashboard**, a written report and a presentation.

![Python](https://img.shields.io/badge/Python-Pandas%20%7C%20NumPy-blue)
![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811)

---

## Project Overview

**Goal:** understand how customers shop and what drives spending, so a retail business can make better marketing and sales decisions.

**Questions answered**
- How much revenue do male and female customers generate?
- Do discounts, subscriptions or shipping type change how much customers spend?
- Which products are rated highest and bought most in each category?
- How are customers split into new, returning and loyal, and which age groups bring the most revenue?

---

## Dataset

| Item | Details |
|---|---|
| Rows / columns | 3,900 customers / 18 columns |
| Customer fields | Age, gender, location, subscription status, previous purchases |
| Purchase fields | Item, category, season, purchase amount (USD), discount, shipping type, payment method |
| Behavior fields | Review rating, frequency of purchases |
| Missing data | 37 missing review ratings (0.9%) |

File: `data/customer_shopping_behavior_dataset.csv`

---

## Workflow

1. **Load and explore (Python):** inspect the data with Pandas (`info`, `describe`, `isnull`).
2. **Clean the data:**
   - Filled missing review ratings with the median rating of each category.
   - Converted column names to snake_case.
   - Dropped `promo_code_used` after confirming it was identical to `discount_applied`.
3. **Feature engineering:**
   - `age_group`: four quartile-based groups (Young Adult, Adult, Middle-aged, Senior).
   - `purchase_frequency_days`: purchase frequency converted to number of days.
4. **SQL analysis (PostgreSQL):** loaded the cleaned data into a `customer` table and answered 10 business questions using aggregations, subqueries, CTEs and window functions.
5. **Dashboard (Power BI):** connected to PostgreSQL and built an interactive dashboard of key metrics.
6. **Report and presentation:** summarized the findings in a written report and a slide deck made with Gamma.

---

## Key Results

- **Total revenue:** $233,081, with an average purchase of **$59.76**.
- **Gender:** male customers generate 68% of revenue ($157,890), mainly because they are 68% of customers. Spend per purchase is almost the same for men and women.
- **Subscriptions:** subscribers do **not** spend more than non-subscribers ($59.49 vs $59.87 per purchase).
- **Discounts:** 43% of purchases used a discount, and half of those customers still spent above the average.
- **Categories:** Clothing is the largest category with 45% of revenue. Outerwear is the smallest with 8%.
- **Customer loyalty:** about 80% of customers are "loyal" (more than 10 previous purchases).
- **Age groups:** Young Adults (18 to 31) contribute the most revenue (26.7%).
- **Shipping:** Express shipping buyers spend about $2 more per purchase than Standard.

**Recommendations:** focus on growing the customer base rather than raising prices, add real benefits to the subscription, target women as an under-served segment, and review discounts on products that already have high discount rates.

---

## Project Structure

```
customer-shopping-behavior-analysis/
|-- data/
|   |-- customer_shopping_behavior_dataset.csv   # raw dataset
|   `-- customer_clean.csv                       # cleaned data (exported from the notebook)
|-- notebooks/
|   `-- customer_shopping_behavior.ipynb         # cleaning, EDA, feature engineering
|-- sql/
|   `-- customer_shopping_behavior_sql_queries.sql   # 10 analysis queries
|-- dashboard/
|   |-- customer_behavior_dashboard.pbix         # Power BI dashboard
|   `-- dashboard_preview.png                    # screenshot of the dashboard
|-- reports/
|   |-- project_report.pdf                       # written report
|   `-- presentation.pdf                         # slide deck (made with Gamma)
`-- README.md
```

---

## How to Run

### Requirements
- Python 3.9+ with Jupyter Notebook or Google Colab
- PostgreSQL and pgAdmin
- Power BI Desktop (Windows)

### Steps

**1. Clone the repository**
```bash
git clone https://github.com/SnehaRamakrishnan/Customer_Behavior_Analysis.git
cd Customer_Behavior_Analysis
```

**2. Run the notebook**
```bash
pip install pandas numpy
```
Open `notebooks/customer_shopping_behavior.ipynb` in Jupyter or Colab and run all cells. The last cell saves the cleaned data as `customer_clean.csv`.

**3. Load the data into PostgreSQL**

In pgAdmin, create a database named `customer_behavior`. Then do either of the following:

- **Option A (same machine as PostgreSQL):** run the connection cell in the notebook. Replace the placeholder with your own password and do not commit it to GitHub.
  ```python
  from sqlalchemy import create_engine
  engine = create_engine("postgresql+psycopg2://postgres:<your_password>@localhost:5432/customer_behavior")
  df.to_sql("customer", engine, if_exists="replace", index=False)
  ```
- **Option B (notebook runs in the cloud, for example Colab):** create the `customer` table in pgAdmin, then right-click the table, choose **Import/Export Data**, select `customer_clean.csv` and turn **Header = Yes**.

**4. Run the SQL queries**

Open the pgAdmin **Query Tool** on `customer_behavior`, open `sql/customer_shopping_behavior_sql_queries.sql`, and run the queries one at a time.

**5. Open the dashboard**

Open `dashboard/customer_behavior_dashboard.pbix` in Power BI Desktop. If it asks for a connection, choose **Home > Transform data > Data source settings**, enter `localhost` as the server and `customer_behavior` as the database, and sign in with your PostgreSQL username and password.

---

## Note on Other Databases

The queries were written and tested on **PostgreSQL**. Most of them also work in MySQL and SQL Server. The main change is `review_rating::numeric` (PostgreSQL syntax), which becomes `CAST(review_rating AS DECIMAL(3,1))` in other databases.

---

## Tools Used

Python (Pandas, NumPy), Jupyter / Google Colab, PostgreSQL, pgAdmin, SQL, Power BI, Gamma, GitHub

---

## Author

**Sneha K** | MCA (AI specialization) | Aspiring Data Analyst

[LinkedIn](https://linkedin.com/in/sneha-k-225131335/) | [GitHub](https://github.com/SnehaRamakrishnan) | snehakallangattil@gmail.com
