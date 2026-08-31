# pizza-sales-sql-practice-project
# Pizza Sales Data Analytics & SQL Validation Project

## Overview

This end-to-end data analytics project focuses on evaluating transactional pizza sales data (48,000+ records) to extract operational insights and validate business metrics. The project prioritizes an **SQL-first workflow**, where MS SQL Server serves as the primary engine for querying, metric calculation, and baseline data validation before building an interactive Power BI reporting layer.

---

## Architecture & Workflow

```
Raw CSV Data ──> MS SQL Server (T-SQL Validation) ──> Power Query (Cleaning) ──> Power BI (DAX Modeling & Dashboard)

```

1. **Database Setup & Extraction (MS SQL Server):**
* Imported raw data into `Pizza DB` and verified schema types.
* Wrote T-SQL scripts leveraging aggregate functions, date intelligence (`DATENAME`, `DATEPART`), subqueries, and window functions to compute core KPIs.


2. **Two-Way Data Validation:**
* Used SQL outputs as the benchmark to cross-verify all downstream calculations in Power BI, ensuring zero discrepancies.


3. **Data Transformation & Modeling (Power Query & DAX):**
* Handled categorical size cleaning (`S` $\rightarrow$ `Regular`, `M` $\rightarrow$ `Medium`, `L` $\rightarrow$ `Large`, `XL` $\rightarrow$ `X-Large`).
* Created custom sorting columns for day and month sequences.
* Engineered explicit DAX measures matching SQL calculations.


4. **Interactive Dashboard Design (Power BI):**
* **Home View:** Executive KPI multi-row cards, daily/monthly order trends, and category/size share donuts.
* **Performance View:** Top 5 and Bottom 5 pizza analysis filtered across Revenue, Quantity, and Order Volume.



---

## Key Metrics & Validated Insights

| Metric | SQL Benchmark | Power BI DAX |
| --- | --- | --- |
| **Total Revenue** | $817,860.00 | $817.86K |
| **Total Orders** | 21,350 | 21,350 |
| **Total Pizzas Sold** | 49,574 | 49,574 |
| **Average Order Value** | $38.31 | $38.31 |
| **Avg Pizzas / Order** | 2.32 | 2.32 |

* **Peak Volume:** Orders concentrate heavily on **Fridays and Saturdays**, with **July and January** leading annual sales volume.
* **Top Revenue Driver:** The **Classic Category** accounts for maximum sales, with **Large** pizzas contributing nearly **46%** of total revenue.

---

## Tech Stack

* **Database:** MS SQL Server (T-SQL)
* **BI & Modeling:** Microsoft Power BI Desktop, DAX, Power Query
* **Dataset:** 48,000+ transactional records (1-year period)
