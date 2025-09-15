# sql-data-analytics-project
A comprehensive collection of SQL scripts for data exploration, analytics, and reporting. These scripts cover various analyses such as database exploration, measures and metrics, time-based trends, cumulative analytics, segmentation, and more.
This repository contains SQL queries designed to help data analysts and BI professionals quickly explore, segment, and analyze data within a relational database. Each script focuses on a specific analytical theme and demonstrates best practices for SQL queries.

## 🧭 Contents
- `exploration/` — schema discovery, table profiling, data quality checks  
- `metrics/` — KPIs, ratios, aggregations, moving averages  
- `time_series/` — daily/weekly/monthly trends, seasonality, period-over-period (WoW/MoM/YoY)  
- `cumulative/` — running totals, cumulative KPIs, cohort accumulation  
- `segmentation/` — customer/product segmentation, RFM, ABC analysis  
- `utilities/` — date dimensions, string utils, window function patterns

## 🛠️ How to Use
1. Point scripts to your database/schema (edit `USE <db_name>;` / `SET search_path` as needed).
2. Run individual scripts by topic (e.g., `time_series/rolling_7d_avg.sql`).
3. Adapt placeholders like `<table_name>`, `<date_column>`, `<key_column>`.

## 🧪 Example Snippets
```sql
-- Rolling 7-day average
SELECT
  dt,
  metric,
  AVG(metric) OVER (ORDER BY dt ROWS BETWEEN 6 PRECEDING AND CURRENT ROW) AS metric_7d_avg
FROM my_table;
   
