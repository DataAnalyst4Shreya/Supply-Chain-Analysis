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

<img width="1280" height="720" alt="data_model_diagram" src="https://github.com/user-attachments/assets/5bc990e2-8beb-482b-a687-3fd8e122c38a" />


# Methodology:

Developed SQL queries in Microsoft SQL Server Management Studio (SSMS) to extract, clean, and transform raw supply chain datasets, enabling structured analysis of the supply chain operations.

Created new measures by writing DAX Measures in Power BI.

Built differnt types of visualizations like line chart, matrix, clustered bar charts, KPI Card, Clustered Column Charts, and Table in Power BI to visualize various supply chain metrics.

Created semiconductor supply chain - entity relationship diagram using Claude (LLM) and PowerPoint Tools.


## Exploratory Data Analysis

Conducted exploratory data analysis using SQL to evaluate the structure, consistency, and overall quality of the semiconductor supply chain dataset. This involved validating row counts across tables, examining column structures, and analyzing product mix through frequency distribution of product types. Additionally, queries were performed to assess manufacturing output ranges, throughput patterns, and product portfolio composition in order to understand category-wise distribution, workload concentration, and operational trends within semiconductor manufacturing and supply chain operations.

## Data Cleaning

Performed comprehensive data cleaning and validation using SQL to improve the reliability and integrity of the semiconductor supply chain dataset. Removed records containing NULL values, duplicate production entries using the ROW_NUMBER() window function, and records violating business rules such as invalid production, yield, inventory, and capacity utilization values. Applied SQL transformations to replace NULL numeric fields with 0 for accurate aggregation and analysis, standardized product type formatting, and retained only production records with valid product references through JOIN operations. Additionally, filtered out orders with invalid dates or quantities and consolidated the cleaned production data into a structured dataset optimized for downstream manufacturing and supply chain analysis.

## Analytical Approach

+ Performed structured exploratory data analysis to understand relationships between demand, supply, production, and inventory across semiconductor operations.

+ Built derived metrics using SQL such as demand-supply gap, execution efficiency, utilization rate, and inventory buffer levels to enable performance evaluation at a granular operational level.

+ Used aggregation and window functions to analyze trends across product categories, technology nodes, and time periods to identify inconsistencies and structural inefficiencies.

+ Conducted comparative analysis across multiple manufacturing dimensions to detect imbalances such as over-supply conditions, negative buffer gaps, and under-utilized capacity.

+ Developed DAX measures in Power BI to compute core demand and supply chain KPIs including Fulfillment KPI, Demand, Supply, Weighted Yield, execution efficiency, utilization vs plan, safety stock, demand-supply gap, and buffer gap, enabling standardized tracking of operational performance across the value chain.

+ Built additional DAX-based manufacturing performance KPIs such as weighted utilization, total production, planned output, planned capacity, inventory levels, and production shortfall to evaluate execution efficiency, capacity alignment, and deviations between planned and actual output.

+ Transformed raw operational data into KPI-driven datasets to support visualization and deeper business interpretation in Power BI dashboards.

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

<img width="1435" height="736" alt="gemini_plan accuracry trend" src="https://github.com/user-attachments/assets/18184997-4b11-40eb-9e19-0a20b0917d8e" />



- This visualization tracks execution efficiency against plan over time with respect to year 2025, highlighting how closely actual performance aligns with planned expectations.

- The line chart shows high volatility across months and days, indicating inconsistent execution performance, which is a concern from a planning and operational stability perspective.

- Execution efficiency exceeds 100% from February 2025 to June 2025, suggesting sustained over-execution relative to plan, which may point to under-forecasting or reactive production adjustments.

- The frequent spikes and dips indicate instability in planning accuracy and suggest that the forecasting model is not reliably capturing real-world production dynamics or demand variability.


**2. Fab Utilization By Plan (%):** 


<img width="1276" height="816" alt="gemini_fab_utilization_vs_plan" src="https://github.com/user-attachments/assets/db8a0a03-68e9-4b2c-8bbe-591cfde49532" />


- The clustered bar chart compares actual utilization against planned capacity across different fabs, highlighting significant operational imbalances.
  
- Fabs 2, 5, and 6 are operating below 100% utilization vs plan, indicating underutilization of available capacity and potential inefficiencies in production allocation or demand fulfillment.

- In contrast, Fabs 1, 3, 4, 7, and 8 are operating above 100% utilization, suggesting overloading beyond planned capacity, which may increase the risk of bottlenecks, quality issues, and equipment strain.

- Overall, the analysis reveals a clear capacity misalignment across fabs, with some underutilized while others are overburdened, indicating the need for better production load balancing and capacity planning alignment.


**3. Demand vs Fulfillment By Product:** 


<img width="1322" height="800" alt="gemini_demand vs fulfillment by product" src="https://github.com/user-attachments/assets/6e4fa7ad-c633-4dee-8bec-c54935fe6a9c" />


- The visualization presents a clustered column chart comparing demand versus fulfillment across different products, providing insights into how effectively production aligns with customer demand.

- For the majority of products, the company is successfully meeting demand with sufficient production output, reflecting strong overall manufacturing and supply chain performance.

- However, for Product IDs 18, 4, 9, 39, and 34, demand exceeds fulfillment, indicating supply shortages and an inability to produce enough units to satisfy market demand.

- The analysis highlights that although most products are adequately fulfilled, these five under-supplied product variants could still create notable supply chain pressure, potentially leading to missed sales opportunities, customer dissatisfaction, and revenue decline.


**4. Yield Performance By Product:** 



- The clustered bar chart highlights the yield percentage across all products, providing insight into the overall production quality and manufacturing efficiency of the company.

- None of the products achieved a yield rate above 95%, indicating that the manufacturing process is operating below optimal efficiency. Lower yield percentages can increase production defects, rework, and manufacturing costs while placing additional pressure on the supply chain.

- Most products recorded yield percentages within the range of 86.14% to 94.67%, reflecting inconsistent production performance. This may lead to material wastage, higher operational expenses, longer production cycles, and inefficient resource utilization.

- Product ID 21 recorded the lowest yield percentage at 84.91%, making it a critical area of concern. Such a low yield level may significantly affect production efficiency, inventory planning, supply reliability, and overall business profitability.

- Overall, the chart indicates that yield performance across products remains below the desired benchmark, highlighting the need for process optimization, quality control improvements, and better manufacturing efficiency to reduce waste, improve operational stability, and support long-term business sustainability.


**5. Yield Performance By Product:** 











**6. End-to-end Supply Chain Performance Matrix:** 

<img width="266" height="314" alt="supply chain overall" src="https://github.com/user-attachments/assets/2b5a743c-eee4-4f74-968f-6e1b2ea45519" />


- The matrix provides a comprehensive view of end-to-end supply chain performance by highlighting demand-supply gaps and inventory buffer gaps for each product.
  
- For the majority of products, demand exceeds supply, indicating production shortfalls and supply chain inefficiencies that may adversely affect operational performance and profitability.

- Product IDs 16 and 7 show a negative buffer gap, meaning inventory levels have fallen below the defined safety stock threshold, creating a high risk of stockouts and potential revenue loss.

- Overall, the analysis reveals a significant imbalance between demand, supply, and inventory positioning, reflecting weaknesses in supply chain synchronization that can negatively impact revenue, service levels, and business credibility.











**Business Recommendations:**

- Strengthen forecasting accuracy by leveraging historical trends, real-time demand signals, seasonality patterns, and market variables to improve planning precision and maintain execution efficiency closer to targeted levels.

- Improve fab utilization balancing by dynamically reallocating production loads across fabs based on capacity availability, historical utilization trends, and changing demand conditions to reduce both underutilization and overloading risks.

- Align production planning with real-time demand requirements to optimize manufacturing throughput, minimize fulfillment gaps, and improve overall supply chain responsiveness and revenue generation.

- Maintain optimal safety stock levels across all products through continuous monitoring of inventory movement, demand variability, and lead times to reduce stockout risks and ensure uninterrupted order fulfillment.

- Reduce excess inventory and carrying costs by implementing demand-driven inventory planning that accounts for supply chain constraints, lead-time fluctuations, and product-level consumption patterns.

- Enhance operational decision-making through a data-driven supply chain framework that integrates forecasting, inventory, production, and fulfillment insights to improve efficiency, reduce waste, and maximize profitability.

- Reduce dependency on external foundries by maximizing internal fab utilization through real-time KPI-driven production monitoring and dynamic capacity allocation across manufacturing facilities.

- Implement a more agile manufacturing strategy that continuously adjusts production plans based on utilization trends, demand fluctuations, and operational performance to improve yield rates, enhance efficiency, and maximize profitability.

- Develop a balanced sourcing strategy by diversifying external foundry partnerships to reduce supply chain risk and improve business continuity during demand surges or disruptions.

- Implement predictive maintenance and downtime monitoring across fabs to reduce production interruptions and improve effective capacity utilization.


# Next Steps:

- Implement real-time KPI dashboards to continuously monitor utilization, execution efficiency, inventory health, and fulfillment performance across fabs and products.

- Develop scenario-based capacity planning models to better respond to sudden demand fluctuations, supply disruptions, and changing market conditions.

- Introduce predictive analytics and advanced forecasting models to improve demand planning accuracy and reduce execution variability.

- Establish automated alert systems for stockout risks, excess inventory levels, and major demand-supply imbalances to enable faster corrective actions.

- Improve collaboration between procurement, manufacturing, inventory, and logistics teams to strengthen end-to-end supply chain synchronization.

- Prioritize production capacity for high-demand and high-margin products during periods of constrained manufacturing capacity.

- Continuously evaluate product-level profitability, inventory movement, and utilization trends to support more strategic operational planning.

- Enhance supply chain resilience by incorporating supplier risk analysis, lead-time variability tracking, and contingency planning mechanisms.

- Perform ongoing root-cause analysis of utilization imbalances, fulfillment gaps, and execution inefficiencies to drive continuous process improvement.

- Explore AI-driven optimization techniques for production scheduling, inventory planning, and demand forecasting to improve long-term operational efficiency and scalability.
