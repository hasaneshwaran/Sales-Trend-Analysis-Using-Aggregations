# Task 6: Sales Trend Analysis

## Objective

The objective of this task was to analyze monthly revenue, order volume, and product-wise sales using the `online_sales` dataset. This analysis helps identify sales trends, top performing months, and products with the highest revenue contribution.

## Dataset

- **Name**: online_sales
- **File**: Sales_sample.csv
- **Columns**:
  - order_id
  - order_date
  - amount
  - product_id

## Tools Used

- SQLite
- DB Browser for SQLite

## Steps Performed

1. Created a new SQLite database named `Task6_Sales_Report.db`.
2. Imported the `Sales_sample.csv` dataset into a table named `online_sales` using DB Browser for SQLite.
3. Verified the imported data to ensure correct columns and data types.
4. Ran SQL queries to:
   - Extract month and year from order_date.
   - Calculate monthly revenue.
   - Identify top 3 months by total revenue.
   - Calculate product-wise total orders and total revenue.
5. Exported query results for submission and reporting.

## SQL Queries and Results

### 1. Monthly Revenue

**Query:**

```sql
SELECT
  strftime('%Y-%m', "order_date") AS month,
  SUM("amount") AS revenue
FROM online_sales
GROUP BY month
ORDER BY month;
