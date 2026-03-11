# Retail Sales Performance Dashboard

## Overview
This project analyzes retail sales performance to identify key drivers of revenue and profitability.  
The analysis explores customer segments, regional performance, product categories, and the impact of discounts on profit.

The goal of this project is to transform raw sales data into meaningful business insights through data analysis and visualization.

---

## Tools Used

- SQL – Data exploration and business queries
- Power BI – Data visualization and dashboard creation
- Excel – Initial data inspection and data cleaning

---

## Dataset

The dataset contains retail sales transactions including the following fields:

- Order Date
- Region
- Customer Segment
- Category
- Sub-Category
- Sales
- Quantity
- Discount
- Profit

These variables allow analysis of sales performance, profitability, and pricing strategies.

---

## Business Questions

The project focuses on answering the following business questions:

1. Which customer segment generates the most profit?
2. Which products have the lowest sales performance?
3. Which products generate negative profit?
4. How do discounts impact profitability?
5. Which region generates the highest profit?

---

## SQL Analysis

SQL queries were used to explore the dataset and identify patterns before building the dashboard.

Example queries:

```sql
-- Profit by Region
SELECT Region, SUM(Profit) AS Total_Profit
FROM sales
GROUP BY Region
ORDER BY Total_Profit DESC;

-- Profit by Customer Segment
SELECT Segment, SUM(Profit) AS Total_Profit
FROM sales
GROUP BY Segment
ORDER BY Total_Profit DESC;

-- Sub-Categories with Negative Profit
SELECT Sub_Category, SUM(Profit) AS Total_Profit
FROM sales
GROUP BY Sub_Category
HAVING SUM(Profit) < 0;
