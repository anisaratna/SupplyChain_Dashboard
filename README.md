# 🌍 Global Supply Chain Intelligence Dashboard (Power BI)

## Project Overview
This project transforms a complex, high-dimensional dataset (**DataCo Smart Supply Chain**) into a strategic executive dashboard. The goal was to build a robust data architecture capable of tracking global logistics performance, identifying financial risks, and diagnosing operational bottlenecks in a multinational environment.

## Key Business Problems Addressed
1. **Logistics Performance:** Investigating the root causes of the high overall late delivery rate (57.5%).
2. **Financial Growth:** Analyzing Year-over-Year (YoY) revenue trends (current growth at +47.61%).
3. **Product Profitability:** Identifying top-performing products contributing to the $1.3M total profit.

## Tech Stack & Engineering Process

### 1. Data Engineering (ETL) & Quality Assurance
I performed extensive data cleaning and transformation using **Power Query (M-Code)**. 

*   **The "Trillion Dollar" Challenge:** Encountered a critical data integrity issue where regional locale settings misinterpreted decimals, resulting in trillion-dollar errors.
*   **The Solution:** Implemented an iterative **"Change Type with Locale"** process (English-US) across multiple financial columns to ensure 100% precision.
*   **Audit:** Monitored Column Quality and Value Distribution to ensure zero errors in the final dataset.

| Data Cleaning Logic (Applied Steps) | Data Quality Audit (Sales Column) |
|---|---|
| ![Applied Steps](assets/applied_steps.png) | ![Data Quality](assets/data_quality.png) |
| *Figure 1: Systematic ETL steps including locale calibration and custom logic.* | *Figure 2: 100% Data Validity achieved post-cleaning.* |

### 2. Data Modeling (Star Schema)
To optimize performance and scalability, I transformed the raw flat table (50+ columns) into a structured **Star Schema**. 

*   **Architecture:** 1 Fact Table (`Fact_Orders`) connected to 3 Dimension Tables (`Dim_Product`, `Dim_Customer`, `Dim_Date`) via one-to-many relationships.
*   **Result:** A highly responsive model that minimizes memory usage and maximizes query speed.

![Star Schema Model](assets/star_schema.png)
*Figure 3: Professional Star Schema architecture for enterprise-level reporting.*

### 3. Advanced Analytics (DAX)
Engineered custom business measures using **DAX** to drive insights:
*   **Time Intelligence:** `YoY Revenue Growth %` and `Revenue Last Year` using `SAMEPERIODLASTYEAR`.
*   **Ranking:** Dynamic `Profit Rank` using `RANKX` to isolate the Top 5 most profitable products.
*   **KPIs:** Accurate `Late Delivery Rate` using optimized `AVERAGE` and `DIVIDE` logic.

## Executive Dashboard Preview
The final result is an interactive, multi-perspective dashboard designed for high-level decision-makers.

![Executive Dashboard](assets/dashboard_final.png)
*Figure 4: Final Dashboard showing $12.0M Revenue and critical logistics KPIs.*

## Strategic Insights & Findings
*   **Logistics Alert:** Identified that **First Class** and **Second Class** shipping modes suffer from disproportionately high delay rates. The data suggests that internal scheduling targets (1-day goals) are unrealistic compared to actual warehouse processing times.
*   **Market Leader:** **Europe** and **LATAM** are the primary revenue drivers, contributing significantly to the $12.0M top-line.
*   **Performance:** Despite the high late delivery rate (57.5%), the company maintains a strong **47.61% YoY growth**, indicating high market demand but strained operations.

---
*Note: Dataset provided by DataCo for Supply Chain Big Data Analysis purposes.*
