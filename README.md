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

8) 
   
   
