# Analysis – KPI Engineering & Analytical Framework

**1. Objective of the Analysis:**

This document explains the underlying logic, structure, and derivation of the key performance indicators (KPIs) used in the supply chain and manufacturing dashboard.

Unlike the README, which focuses on insights and business outcomes, this section focuses on how metrics are constructed, how they interact, and what they represent at a system level.


**2. Analytical Scope:**

The analysis evaluates semiconductor manufacturing performance across:

+ Technology nodes
+ Product categories
+ Time periods

The core objective is to understand system behavior across:

+ Demand vs Supply alignment
+ Production efficiency
+ Capacity utilization
+ Execution accuracy
+ Structural imbalances (inventory, shortfall, buffer gaps)

  
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

Demand represents the forecasted requirement across products and technology nodes.

+ Aggregated at: Node + Time period
+ Source: Forecasting dataset
+ Purpose: Baseline requirement for supply planning


### 4.2 Supply

Supply represents actual production output after operational constraints and yield effects.

+ Aggregated from production output data
+ Adjusted for yield losses
+ Represents realized deliverable output

  
### 4.3 Demand–Supply Gap

This metric identifies structural imbalance between demand and supply.

+ Formula:
Demand – Supply
+ Interpretation:
    + Positive → Under-supply (unmet demand)
    + Negative → Over-supply (excess production)


### 4.4 Yield (Weighted)

Yield measures production efficiency and quality of output.

+ Formula:
Good Output / Total Input
+ Weighted by production volume to avoid distortion from low-volume nodes
+ Ensures fair comparison across heterogeneous manufacturing scales


### 4.5 Capacity Utilization

Capacity utilization measures how effectively available production capacity is used.

+ Formula:
Actual Production / Available Capacity
+ Compared against planned capacity to assess operational efficiency


### 4.6 Execution Efficiency

Execution efficiency evaluates alignment between planning and execution.

+ Formula:
Actual Output / Planned Output
+ Highlights deviations between production planning and real execution


## 5. Derived Analytical Layers

These KPIs are constructed by combining foundational metrics to provide deeper operational insights.


## 5.1 Weighted Utilization

Weighted utilization adjusts raw utilization by production contribution across nodes.

+ Purpose: Prevent distortion from low-volume nodes
+ Logic: Utilization weighted by node-level production share
+ Approach: Aggregation using weighted contribution across nodes


### 5.2 Total Production

Represents aggregated actual output across all nodes.

+ Simple SUM of production output
+ Used as a base metric for multiple derived KPIs


### 5.3 Planned vs Actual Output (Variance)

Measures deviation between planned and actual production.

+ Formula:
Actual Output – Planned Output
+ Used to evaluate execution accuracy


### 5.4 Inventory Position

Represents accumulated surplus over time when supply exceeds demand.

+ Logic: Running cumulative (Supply – Demand)
+ Helps identify structural overproduction patterns


### 5.5 Shortfall Metric

Captures unmet demand conditions.

+ Condition-based metric:
   + If Demand > Supply → Shortfall = Demand – Supply
   + Else → 0
+ Used to identify risk of demand non-fulfillment


## 6. Analytical Design Considerations

Several design principles were applied to ensure robustness and comparability:

+ Node-level aggregation was used to capture structural differences across technology maturity levels
+ Weighted measures were introduced to reduce bias from volume imbalance
+ Time-based grouping was used to smooth short-term volatility
+ Derived KPIs were built on standardized base measures for consistency


## 7. KPI Dependency Structure

The KPIs are interdependent and form a hierarchical system:

+ Yield → influences effective Supply
+ Supply + Demand → defines Gap
+ Gap → drives Inventory and Shortfall behavior
+ Capacity → influences Utilization and Execution Efficiency

This structure ensures that operational inefficiencies can be traced back to root drivers.


## 8. Analytical Constraints

The analysis is subject to the following limitations:

+ External market dynamics are not explicitly modeled
+ Capacity is treated as fixed within analysis periods
+ Forecast demand is assumed as reference baseline
+ Yield is treated as deterministic rather than probabilistic


## 9. Summary of Analytical Framework

This analysis establishes a structured KPI framework for evaluating semiconductor manufacturing and supply chain performance.

It enables interpretation of:

+ Structural supply-demand imbalance
+ Production efficiency and execution gaps
+ Capacity utilization inefficiencies
+ Inventory build-up and shortfall risks

The framework provides a consistent foundation for operational monitoring and decision support.
