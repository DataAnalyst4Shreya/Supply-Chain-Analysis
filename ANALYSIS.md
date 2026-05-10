# Analysis – KPI Engineering & Analytical Framework

**1. Objective of the Analysis:**

This document explains the underlying logic, structure, and derivation of the key performance indicators (KPIs) used in the supply chain and manufacturing dashboard.

Unlike the README, which focuses on insights and business outcomes, this section focuses on how metrics are constructed, how they interact, and what they represent at a system level.


**2. Analytical Scope:**

The analysis evaluates semiconductor manufacturing performance across:

+ Technology nodes
+ Product IDs
+ Inventory
+ Yield Percent
+ Time periods

The core objective is to understand system behavior across:

+ Demand vs Supply alignment
+ Production Efficiency
+ Utilization Percentage
+ Execution Accuracy
+ Structural Imbalances (inventory, shortfall, buffer gaps)

  
**3. Data Foundation (High-Level Overview):**

The dataset is structured at a granular level and processed using SQL transformations and Power BI modeling.

Key preparation steps include:

+ Standardization of product and node identifiers
+ Aggregation of transactional data into analytical grains
+ Joining demand forecasts with production outputs
+ Ensuring consistency across time-based dimensions

The final model supports KPI generation at node, product, and time hierarchy levels.


**4. KPI Construction Methodology:**

This section defines how core metrics are derived from base data.


### 4.1 Demand:

Demand is calculated by summing quantity ordered from orders table.

+ Aggregate function: SUM function
+ Source: orders table
+ Purpose: To know the total demand


### 4.2 Supply

Supply is calculated by summing quantity produced from productions table.

+ Aggregated function: SUM function
+ Source: productions table
+ Purpose: To know the total supply

  
### 4.3 Demand–Supply Gap

This metric identifies structural imbalance between demand and supply.

+ Formula:
Demand – Supply
+ Interpretation:
    + Positive → Under-supply (unmet demand)
    + Negative → Over-supply (excess production)


### 4.4 Weighted Yield

Weighted Yield measure helps in identifying overall production quality and manufacturing efficiency by considering the impact of production volume on yield performance.

+ Formula:
∑(Quantity Produced × Yield %) Divided By ∑(Quantity Produced) 
	​
+ Interpretation:
    + Higher value → Better production quality and manufacturing efficiency
    + Lower value → Higher defects, wastage, or production inefficiencies


### 4.5 Utilization Percentage

Utilization percentage examines how effectively actual production is aligned with planned capacity.

+ Formula:
Actual Production / Planned Capacity
+ Compared against planned capacity to assess operational efficiency

+ Interpretation:
    + Higher value → Better capacity utilization and efficient use of manufacturing resources
    + Lower value → Underutilized capacity, indicating idle resources or production inefficiencies


### 4.6 Execution Efficiency

Execution efficiency evaluates alignment between planning and execution.

+ Formula:
Actual Output / Planned Output
+ Highlights deviations between production planning and real execution

+ Interpretation:
    + Higher value → Strong alignment between planned and actual production, indicating effective execution
    + Lower value → Planning-execution mismatch, highlighting delays, disruptions, or inaccurate forecasting


### 5.3 Safety Stock

+ Logic:
Safety stock helps in identifying the buffer inventory maintained to prevent stockouts during demand fluctuations or supply delays.

+ Assumption:
 + Due to the absence of lead time variability and demand deviation data, minimum inventory level was used as a proxy for safety stock.
 + Assumed that the lowest stock level maintained in the dataset represents the minimum buffer inventory required to avoid stockouts.
 + The safety stock calculation in this project is intended for analytical interpretation rather than operational inventory planning precision.
 + This assumption helps evaluate inventory risk, supply continuity, and stock availability trends within the supply chain.

+ Interpretation:
    + Higher value → Better protection against supply chain disruptions
    + Lower/Negative value → Increased risk of stock shortages and fulfillment delays


### 5.4 Buffer Gap

+ Logic:
Buffer gap helps in identifying the difference between current stock level and required safety stock level.

+ Formula:
Stock Level - Safety Stock

+ Interpretation:
    + Positive → Sufficient inventory buffer available
    + Negative → Risk of stockouts and insufficient safety inventory


### 5.5 Shortfall

Captures unmet demand conditions.

+ Condition-based metric:
   + If Demand > Supply → Shortfall = Demand – Supply
   + Else → 0
+ Used to identify risk of demand non-fulfillment

+ Interpretation:

    + Higher value → Greater unmet demand, indicating supply shortages and potential lost sales
    + Zero value → No demand-supply mismatch, meaning demand is fully fulfilled
    + Persistent shortfall → Signals structural capacity or supply chain constraints that need corrective action


## 5.6. Fulfillment Rate

+ Logic:
Measures how effectively customer demand is being met by comparing fulfilled quantity against total ordered quantity.

+ Formula:
Fulfillment Rate = ∑(Quantity Fulfilled) Divided By ∑(Quantity Ordered)

+ Interpretation:
    + Higher value → Strong order fulfillment performance and better customer satisfaction
    + Lower value → Unmet demand, fulfillment delays, or supply constraints


## 6. Analytical Constraints

+ Logic:
The analysis is subject to the following limitations:

+ External market dynamics are not explicitly modeled
+ Capacity is treated as fixed within analysis periods
+ Forecast demand is assumed as reference baseline
+ Yield is treated as deterministic rather than probabilistic


# Conclusion

This analysis establishes a structured KPI framework for evaluating semiconductor manufacturing and supply chain performance.

It enables interpretation of:

+ Structural supply-demand imbalance
+ Production efficiency and execution gaps
+ Capacity utilization inefficiencies
+ Inventory build-up and shortfall risks

The framework provides a consistent foundation for operational monitoring and decision support.
