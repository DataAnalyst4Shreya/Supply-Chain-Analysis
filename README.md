# Executive Summary:

This project analyzes the supply chain operations of a global semiconductor manufacturer, focusing on manufacturing execution, inventory performance, fulfillment efficiency, and demand-supply alignment to identify operational bottlenecks and improve supply chain visibility. Using SQL-based analytics and Power BI dashboards, the analysis uncovers key operational constraints and highlights opportunities to optimize supply chain performance through data-driven insights.

Leveraged SQL and Power BI dashboards to evaluate end-to-end supply chain performance across utilization rate, execution efficiency, fulfillment performance, inventory health and risk, production efficiency, inventory trends, and demand-supply gaps. Applied SQL window functions and CASE statements to analyze chronological inventory fluctuations, enabling identification of stock movement patterns and product-level risk insights. Utilized Common Table Expressions (CTEs) to independently aggregate sales, production, and inventory metrics, improving query structure and calculation accuracy. Further optimized demand-supply gap analysis using LEFT JOINs to prevent join fan-out, ensuring precise calculations and complete product-level visibility across datasets.

The analysis revealed that it is important to optimize key manufacturing and supply chain processes by continuously monitoring KPIs in real time to better align demand and supply and maximize operational efficiency and profitability.

Based on these insights, targeted recommendations are proposed to address manufacturing inefficiencies and improve overall supply chain performance.

1) Implement dynamic capacity rebalancing across fabrication sites by redistributing production workloads from overutilized fabs (>1) to underutilized fabs (<1) to maximize overall asset efficiency and reduce idle capacity.

2) Improve production planning accuracy by refining forecasting models and incorporating historical execution variance, enabling better alignment between planned output and actual production to reduce over-execution and under-execution across fabs.

3) Enhance Fulfillment KPI performance by implementing demand-driven production planning, optimizing fab capacity utilization, and strengthening supply chain coordination to consistently meet customer demand and reduce delivery shortfalls.

4) Deploy dynamic safety stock and replenishment optimization for products with negative buffer gaps (i.e product 7 and product 16) by aligning inventory thresholds with real-time demand variability, lead times, and supply constraints to reduce stockout risk and improve inventory health.

5) Optimize inventory buffer levels and adopt demand-driven inventory planning to reduce excess stock holding while maintaining adequate safety stock coverage. This can improve working capital efficiency, lower carrying costs, and reduce the risk of inventory obsolescence without increasing stockout risk.

6) Deploy an enterprise-wide yield optimization initiative focused on root-cause analysis of recurring defects, real-time process intelligence, and proactive quality controls to reduce large-scale production losses, recover hidden manufacturing capacity, and strengthen supply chain resilience and profitability.

7) Prioritize yield optimization initiatives alongside capacity management to convert existing high utilization levels into greater usable output, focusing on defect pattern identification, defect reduction, and real-time process controls to unlock hidden manufacturing capacity and reduce supply chain pressure.

8) Rebalance capacity allocation across technology nodes by aligning supply planning with real-time demand signals and end-market adoption trends to reduce structural over-supply in technology nodes (7nm, 10nm and 14nm) and improve overall asset utilization.

9) Address the persistent negative demand-supply gap (over-supply condition) by realigning production plans with actual demand signals, scaling down output for consistently negative-gap products, and shifting capacity toward higher-demand areas to reduce inventory accumulation, safeguard margins, and improve overall operational efficiency.


# Business Problem:

For this semiconductor company, optimizing manufacturing and supply chain operations is essential to achieving operational efficiency and maximizing profitability. However, persistent constraints across both manufacturing and supply chain functions are creating structural bottlenecks, leading to negative demand–supply gaps, which in turn are adversely impacting yield performance and increasing overall operational costs. This issue has been identified by the Supply Chain Planning and Operations team, who have engaged the Data Analytics team to analyze the root drivers and develop actionable recommendations to resolve these challenges.

The objective of this analysis is to identify gaps and shortfalls across the supply chain and manufacturing operations, and to uncover the underlying drivers by examining key stages of the end-to-end process. This includes improving demand forecasting accuracy, strengthening alignment between supply and actual demand, and identifying bottlenecks across manufacturing nodes. The analysis also focuses on enhancing inventory health through better buffer management, improving fulfillment rate stability, and optimizing capacity utilization across production stages and technology nodes. In addition, it aims to reduce operational inefficiencies, improve yield performance, and enhance overall decision-making speed through more reliable operational visibility. The insights generated will support targeted, data-driven improvements across manufacturing and supply chain functions, ultimately reducing costs and maximizing profitability.

<img width="1280" height="720" alt="data_model_diagram" src="https://github.com/user-attachments/assets/5829f80a-e607-4918-bc84-e93b24f8d984" />


<img width="1280" height="720" alt="relationship_summary" src="https://github.com/user-attachments/assets/da320a1e-24be-4a34-8068-3e0af3bbebf7" />


# Methodology:

Developed SQL queries in Microsoft SQL Server Management Studio (SSMS) to extract, clean, and transform raw supply chain datasets, enabling structured analysis of the supply chain operations.

Created new measures by writing DAX Measures in Power BI.

Built differnt types of visualizations like line chart, matrix, clustered bar charts, KPI Card, Clustered Column Charts, and Table in Power BI to visualize various supply chain metrics.

Created semiconductor supply chain - entity relationship diagram using Claude (LLM) and PowerPoint Tools.


## Exploratory Data Analysis

Conducted exploratory data analysis using SQL to evaluate the structure, consistency, and overall quality of the semiconductor supply chain dataset. This involved validating row counts across tables, examining column structures, and analyzing product mix through frequency distribution of product types. Additionally, queries were performed to assess manufacturing output ranges, throughput patterns, and product portfolio composition in order to understand category-wise distribution, workload concentration, and operational trends within semiconductor manufacturing and supply chain operations.

## Data Cleaning

Performed comprehensive data cleaning and validation using SQL to improve the reliability and integrity of the semiconductor supply chain dataset. Removed records containing NULL values, duplicate production entries using the ROW_NUMBER() window function, and records violating business rules such as invalid production, yield, inventory, and capacity utilization values. Applied SQL transformations to replace NULL numeric fields with 0 for accurate aggregation and analysis, standardized product type formatting, and retained only production records with valid product references through JOIN operations. Additionally, filtered out orders with invalid dates or quantities and consolidated the cleaned production data into a structured dataset optimized for downstream manufacturing and supply chain analysis.

## Analysis

Utilized Common Table Expressions (CTEs), aggregate functions, and SQL calculations to independently measure manufacturing utilization rate and execution efficiency across semiconductor operations. Implemented CASE statements to handle NULL values and ensure accurate, error-free KPI calculations. Applied scalar value multiplication and type conversion techniques to generate precise decimal-based performance metrics. Additionally, leveraged LEFT JOIN operations while calculating daily efficiency to capture planned production days with zero or missing output, enabling more comprehensive operational performance analysis and gap identification. 

## Data Visualization

Developed comprehensive supply chain and manufacturing visualizations to provide an end-to-end view of operational performance within the semiconductor company. Designed line charts to track planning accuracy trends over time and monitor inventory movement against safety stock levels. Utilized clustered column and bar charts to analyze fab utilization versus planned capacity, technology node demand-supply imbalances, and yield performance across products. Created KPI cards to highlight operational fulfillment performance and designed detailed tables to evaluate product-level buffer gaps and inventory risks. Additionally, built an end-to-end supply chain matrix to deliver deeper insights into critical operational metrics, including demand-supply gaps and buffer gaps across product categories.


# Skills & Tools Used:

**SQL:** Utilized CTEs, window functions, JOINs, CASE statements, ISNULL functions, WHERE clauses, aggregate functions, and decimal-based calculations to perform data extraction, transformation, cleaning, and advanced supply chain analysis.

**Power BI:** Developed DAX measures and interactive dashboards to perform in-depth semiconductor supply chain and manufacturing analysis, enabling KPI tracking, operational monitoring, and data-driven storytelling.

**Data Wrangling & Cleaning:** Cleaned and transformed raw supply chain data by handling missing values, duplicates, inconsistent records, and invalid business-rule entries to ensure data accuracy and analytical reliability.

**Data Modeling:** Designed and refined a semiconductor supply chain entity-relationship model (ERD) using AI-assisted prompt engineering with Claude, and further structured the data model within Power Point tool for reporting and analysis.

**Data Visualization:** Built interactive visualizations including matrices, tables, KPI cards, clustered bar charts, clustered column charts, and line charts to analyze demand-supply alignment, inventory trends, fulfillment performance, yield metrics, and capacity utilization.

**SQL Server Management Studio (SSMS) Version 2022:** Performed exploratory data analysis, query optimization, and supply chain KPI analysis using SQL Server Management Studio (SSMS) Version 2022.

**Data Source:** Leveraged AI-assisted prompt engineering using ChatGPT to generate a synthetic semiconductor supply chain dataset for analytical modeling, visualization, and business problem-solving.

**Data Type:** Synthetic Dataset.


# Results & Business Recommendation:

**1. Planning Accuracy Trend Over Time (2025):**


   
