# Retail Sales Performance Dashboard

## Overview
This project analyzes retail sales performance to identify key drivers of revenue and profitability. I transformed raw sales data into meaningful business insights, focusing on customer segments, regional performance, and the critical impact of discounts on profit.

The goal was to move beyond simple charts and provide a tool for identifying financial risks and growth opportunities.

---

## Dashboard Preview
![Dashboard Screenshot](Retailsalesdashboard.png) 
*(Note: Upload your screenshot to the repository and replace the name above)*

---

## Tools Used
- **SQL:** Data exploration and business logic validation.
- **Power BI:** Data visualization, DAX measures, and interactive reporting.
- **Excel:** Initial data inspection and cleaning.

---

## Business Questions Answered
1. Which customer segment generates the most profit?
2. Which products have the lowest sales performance?
3. **Which products generate negative profit?** (Analyzed using conditional formatting).
4. How do discounts impact profitability? (Correlation analysis via Scatter Chart).
5. Which region generates the highest profit?

---

##  Key Insights (Executive Summary)
* **Profitability Warning:** Through **conditional formatting (red highlights)**, I identified that **Tables** and **Bookcases** are the main drivers of negative profit, despite having significant sales volume.
* **Discount Correlation:** The analysis shows that aggressive discounting (above 20%) consistently leads to losses, particularly in the Furniture category.
* **Top Performer:** The **Consumer segment** remains the primary source of income, while the **West region** is the most efficient in terms of net profit.

---

## SQL Analysis
Before building the dashboard, I used SQL to explore the dataset and validate the business logic.

```sql
-- 1. Profit by Region
SELECT Region, SUM(Profit) AS Total_Profit
FROM sales
GROUP BY Region
ORDER BY Total_Profit DESC;

-- 2. Profit by Customer Segment
SELECT Segment, SUM(Profit) AS Total_Profit
FROM sales
GROUP BY Segment
ORDER BY Total_Profit DESC;

-- 3. Identifying Sub-Categories with Negative Profit (Financial Risks)
SELECT Sub_Category, SUM(Profit) AS Total_Profit
FROM sales
GROUP BY Sub_Category
HAVING SUM(Profit) < 0
ORDER BY Total_Profit ASC;
