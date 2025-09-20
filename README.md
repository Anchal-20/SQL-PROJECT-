📌 Project Overview

This project builds a SQL-based Data Warehouse using Medallion architecture to analyze sales and customer data. It demonstrates end-to-end ETL pipelines, star schema design, and KPI reporting for business insights.

🎯 Business Problem

Companies often struggle to get a single source of truth for sales and customer data. This project solves that by:

Consolidating data from multiple sources (ERP, CRM).

Cleaning, transforming, and modeling the data.

Enabling business users to query KPIs (sales trends, customer behavior, product performance).

🛠️ Tech Stack

Database: SQL Server

ETL: SQL Scripts (CTEs, Stored Procedures, Views)

Modeling: Star Schema (Fact + Dimension tables)

Visualization: Power BI / Excel

🗂️ Project Architecture
Raw Data → Bronze Layer → Silver Layer → Gold Layer → BI Dashboards


Bronze: Raw data ingestion (ERP, CRM).

Silver: Cleaned & transformed data.

Gold: Aggregated, analysis-ready fact/dimension tables.

(Add a simple diagram here with arrows — you can use draw.io or Lucidchart.)

📑 Data Model

Fact_Sales: sales_id, product_id, customer_id, region_id, date, quantity, revenue

Dim_Product: product_id, product_name, category

Dim_Customer: customer_id, name, segment

Dim_Region: region_id, region_name

Dim_Date: date_id, day, month, year

🔍 Key Business Questions Answered

Which regions generated the highest sales revenue?

What are the top-selling product categories?

How has customer demand trended month-over-month?

Which customers contribute most to revenue (Pareto/80-20)?

What are seasonal sales patterns and forecasting insights?

📈 Dashboards

Sales Performance Dashboard (Power BI/Excel): Revenue by region, product, and month.

Customer Analysis Dashboard: Customer segmentation, CLV trends.
(Add screenshots here)

🚀 How to Run

Clone the repo.

Import datasets into SQL Server/PostgreSQL.

Run the ETL scripts (etl/ folder).

Query the reporting tables using SQL scripts (queries/ folder).

Open Power BI/Excel dashboards (dashboards/ folder).

✅ Sample Query
-- Top 5 customers by revenue
SELECT c.customer_name, SUM(f.revenue) AS total_revenue
FROM Fact_Sales f
JOIN Dim_Customer c ON f.customer_id = c.customer_id
GROUP BY c.customer_name
ORDER BY total_revenue DESC
LIMIT 5;

📊 Insights & Recommendations

North region contributes 40% of revenue → allocate more resources for regional marketing.

Festive months show 25% sales spike → plan inventory & promotions accordingly.

Category A products underperforming → evaluate pricing or bundling strategy.

🏆 Key Learnings

Designed and implemented star schema for reporting.

Improved SQL query performance with indexes & CTEs.

Gained hands-on experience in ETL pipelines and KPI analysis.
