# 🌍 Global Supply Chain Intelligence Dashboard (Power BI)

## Project Overview
This project transforms a complex, high-dimensional dataset (**DataCo Smart Supply Chain**) into a strategic executive dashboard. The goal was to build a robust data architecture capable of tracking global logistics performance, identifying financial risks, and diagnosing operational bottlenecks.

## Key Business Problems Addressed
1. **Logistics Performance:** Why is the overall late delivery rate as high as 57.3%?
2. **Financial Growth:** How is the Year-over-Year (YoY) revenue trending across different markets?
3. **Product Profitability:** Which specific products contribute the most to the bottom line despite shipping challenges?

## Tech Stack & Engineering Process
### 1. Data Engineering (ETL)
* **Tool:** Power Query (M-Code).
* **Challenge:** Encountered "Decimal Misinterpretation" due to regional locale settings (resulting in trillion-dollar errors).
* **Solution:** Performed **Change Type with Locale (English-US)** to ensure 100% data integrity for financial columns.
* **Feature Engineering:** Created `IsLate` logic to categorize shipping performance.

### 2. Data Modeling (Star Schema)
* Optimized performance by transforming a flat table (50+ columns) into a **Star Schema**.
* **Tables:** 1 Fact Table (`Fact_Orders`) and 3 Dimension Tables (`Dim_Product`, `Dim_Customer`, `Dim_Date`).
* Result: A lightweight, scalable model with efficient one-to-many relationships.

### 3. Advanced Analytics (DAX)
* Engineered custom measures for deep-dive analysis:
  * **Time Intelligence:** `YoY Revenue Growth %` and `Revenue Last Year`.
  * **Ranking:** `Profit Rank` using `RANKX` for dynamic top-performing product identification.
  * **KPIs:** Accurate `Late Delivery Rate` calculation using `DIVIDE` and `AVERAGE` logic.

## Strategic Insights
* **Logistics Red Flag:** Shipping mode hits a **57% late delivery rate**. Analysis suggests unrealistic internal scheduling (1-day target vs 2+ days actual) rather than just courier failure.
* **Market Leader:** **LATAM** is the primary driver of revenue, but also shows high shipping risks.
* **Profitability:** Top 5 products contribute significantly to the $3.9M total profit, despite the high volatility in shipping times.

## Dashboard Preview
![Executive Dashboard](assets/dashboard_final.png)

---
*Note: Dataset provided by DataCo for Big Data Analysis purposes.*
