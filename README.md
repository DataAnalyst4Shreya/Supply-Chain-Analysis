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

<img width="1280" height="720" alt="data_model_diagram" src="https://github.com/user-attachments/assets/a1df4a3b-8b7b-4c5b-86ac-0cac82a69267" />


# Methodology:

Developed SQL queries to extract, clean, and transform raw subscription data, enabling structured analysis of the payment funnel.

Built a funnel tracking dashboard in Hex to visualize subscription counts across payment stages.

Mapped the end-to-end subscription payment funnel using Lucidchart to define user flow and key conversion stages.


## Exploratory Data Analysis (EDA)

Conducted initial data exploration using SQL to understand the structure and quality of the subscription dataset. This included checking for missing values, duplicates, and inconsistencies in the subscription dataset. Queried subscription IDs across both successful (‘happy path’) and failed (‘error path’) journeys to reconstruct end-to-end user flows and understand payment behavior. Performed high-level analysis to uncover initial trends and establish a baseline understanding of user engagement and payment performance.

## Product Funnel Analysis

Defined the key stages of the payment funnel, from checkout initiation to successful subscription payment. Used SQL techniques, including Common Table Expressions (CTEs) and aggregate functions, to calculate conversion rates at each stage. CASE statements were applied to categorize users based on their progress through the funnel. Drop-off rates were measured to identify critical friction points, and further segmentation was performed to analyze root causes such as payment errors and user behavior. Computed conversion rates and workflow conversion rates to develop a comprehensive understanding of user flow and payment performance across the funnel.

## Data Visualization

Developed visualizations to effectively communicate insights and highlight key findings. Bar charts were used to compare subscriptions with and without payment errors, while funnel visualizations illustrated conversion rates across each stage of the payment process. Built line charts to analyze trends in subscription flow across funnel stages over time, identifying patterns in user progression and drop-off behavior. Dashboards were created in Hex Data Science Notebook to present insights in a clear, actionable format for business stakeholders.


# Skills & Tools Used:

**SQL:** CTEs, JOINs, CASE statements, aggregate functions, and subqueries for data extraction, transformation, and funnel analysis

**Data Wrangling & Cleaning:** Processed raw subscription data by handling missing values, duplicates, and inconsistencies to ensure data quality

**Data Modeling:** Designed data flow and structured subscription funnel stages using Lucidchart

**Data Visualization:** Built bar and line charts to analyze trends, funnel progression, and user behavior patterns

**Data Analysis Notebook:** Performed exploratory analysis and dashboarding using Hex

**Data Warehouse:** Queried and analyzed structured datasets stored in Snowflake


# Results & Business Recommendation:

   
