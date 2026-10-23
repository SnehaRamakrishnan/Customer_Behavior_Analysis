# Customer Shopping Behavior Analysis

## Project Overview

This project analyzes customer shopping behavior to identify purchasing patterns, customer segments, product preferences, and discount trends. It follows an end-to-end data analytics workflow using Python, SQL, and Power BI to transform raw data into meaningful business insights.

The goal is to understand customer behavior and provide data-driven insights that can support business decisions related to sales, customer retention, and marketing strategies.

## Objectives

- Load and explore the dataset using Python.
- Perform Exploratory Data Analysis (EDA) to understand data patterns.
- Clean and prepare the dataset for analysis.
- Use SQL to answer business questions and identify trends.
- Build an interactive Power BI dashboard.
- Create a business insights report and presentation.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data analysis and preprocessing |
| Pandas, NumPy | Data manipulation and cleaning |
| Matplotlib, Seaborn | Data visualization and EDA |
| PostgreSQL / MySQL / SQL Server | Data storage and SQL analysis |
| SQL | Business queries, aggregations, and customer analysis |
| Power BI | Interactive dashboard development |
| Gamma | Presentation creation |

*Use the database technology you actually implemented in the project.*

## Dataset

The project uses customer shopping behavior data containing information such as:

- Customer demographics
- Product categories and items purchased
- Purchase amounts and discounts
- Payment methods and shipping preferences
- Customer subscription status
- Previous purchases and purchase frequency
- Customer review ratings

## Project Workflow

### 1. Data Loading and Exploration
- Imported the dataset into Python using Pandas.
- Reviewed the dataset structure, dimensions, column names, and data types.
- Examined summary statistics and potential data quality issues.

### 2. Exploratory Data Analysis (EDA)
- Analyzed customer demographics and purchasing patterns.
- Explored product category and item-level trends.
- Examined purchase amounts, discounts, and review ratings.
- Used visualizations to identify patterns and relationships.

### 3. Data Cleaning and Preparation
- Identified and handled missing values.
- Checked data types and corrected inconsistencies.
- Standardized column names and prepared fields for analysis.
- Created additional analytical features where appropriate.
- Exported the cleaned dataset for database analysis.

### 4. SQL Analysis
- Loaded the prepared dataset into a relational database.
- Used SQL queries to answer business questions.
- Applied filtering, grouping, aggregate functions, CTEs, and window functions where relevant.
- Analyzed customer segments, popular products, discount rates, and purchasing trends.

### 5. Power BI Dashboard
- Connected Power BI to the analyzed dataset.
- Created KPI cards, charts, and interactive filters.
- Presented key customer, product, and purchasing metrics in a clear visual format.

### 6. Business Report and Presentation
- Summarized key findings from the Python and SQL analysis.
- Prepared a report highlighting insights and potential business recommendations.
- Created a presentation using Gamma to communicate the project and its findings.

## Key Business Questions

- Which product categories and items are most frequently purchased?
- How do purchasing patterns vary across customer groups?
- What percentage of purchases involve discounts?
- How do subscription status and purchase frequency relate to customer behavior?
- Which customer segments could benefit from targeted marketing?
- What insights can support customer retention and sales improvement?

## Results and Insights

The project provides a structured view of customer purchasing behavior through exploratory analysis, SQL-based business queries, and an interactive Power BI dashboard.

The final findings are used to identify product trends, understand customer segments, evaluate discount patterns, and develop potential business recommendations.

*Add your verified numerical findings and screenshots here after completing the analysis and dashboard.*

## Project Structure

```text
## Project Structure

```text
Customer-Shopping-Behavior-Analysis/
│
├── data/
│   └── customer_shopping_behavior.csv
│
├── notebooks/
│   └── customer_shopping_behavior_analysis.ipynb
│
├── sql/
│   └── customer_behavior_analysis.sql
│
├── powerbi/
│   └── customer_behavior_dashboard.pbix
│
├── reports/
│   └── customer_behavior_analysis_report.pdf
│
├── presentation/
│   └── customer_behavior_presentation.pdf
│
└── README.md
```


*The folder names and filenames above are suggested. Adjust them to match your actual repository.*

## How to Run the Project

### Prerequisites
- Python 3.x
- Jupyter Notebook or Google Colab
- Required Python libraries: Pandas, NumPy, Matplotlib, and Seaborn
- PostgreSQL, MySQL, or SQL Server
- Power BI Desktop

### Steps

1. **Clone the repository**
   ```bash
   git clone <your-repository-url>
   cd Customer-Shopping-Behavior-Analysis
   ```

2. **Install Python libraries**
   ```bash
   pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2-binary
   ```
   Install the appropriate database driver for your chosen SQL database.

3. **Run the notebook**
   Open the notebook in Jupyter or Google Colab and execute the cells in order to load, explore, and clean the dataset.

4. **Load the cleaned data into the database**
   Create the target database and table, configure the connection securely, and import the cleaned dataset.

5. **Execute SQL queries**
   Open the SQL script in your database client and run the queries to reproduce the business analysis.

6. **Open the Power BI dashboard**
   Open the `.pbix` file in Power BI Desktop. If necessary, update the data source connection to your local database.

7. **Review the report and presentation**
   Open the generated report and presentation to review the findings and recommendations.

## Business Value

This project demonstrates how data analytics can turn raw customer data into actionable business insights. It showcases practical skills in data preparation, SQL querying, visualization, dashboard development, and business communication.

## Author

**Sneha K**

Aspiring Data Analyst | Python | SQL | Power BI | Excel
