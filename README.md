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

<img width="387" height="199" alt="image" src="https://github.com/user-attachments/assets/dbc487db-205b-4486-8401-6e568ca150f8" />


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Planning Accuracy Trend Over Time</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/hammer.js/2.0.8/hammer.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/chartjs-plugin-zoom/2.0.1/chartjs-plugin-zoom.min.js"></script>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;800&family=DM+Mono:wght@300;400&display=swap');

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0b0f1a;
    --surface: #111827;
    --border: #1e2d40;
    --accent: #38bdf8;
    --accent2: #f472b6;
    --text: #e2e8f0;
    --muted: #64748b;
    --grid: rgba(255,255,255,0.04);
    --high: #f87171;
    --low: #34d399;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 2rem;
  }

  .wrapper {
    width: 100%;
    max-width: 960px;
  }

  header {
    margin-bottom: 2rem;
  }

  .eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.5rem;
  }

  h1 {
    font-size: clamp(1.4rem, 3vw, 2.2rem);
    font-weight: 800;
    letter-spacing: -0.02em;
    line-height: 1.1;
  }

  h1 span { color: var(--accent); }

  .stats-row {
    display: flex;
    gap: 1.5rem;
    margin-top: 1.2rem;
    flex-wrap: wrap;
  }

  .stat {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 0.75rem 1.2rem;
    display: flex;
    flex-direction: column;
    gap: 0.2rem;
  }

  .stat-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
  }

  .stat-value {
    font-size: 1.25rem;
    font-weight: 800;
    letter-spacing: -0.02em;
  }

  .stat-value.high { color: var(--high); }
  .stat-value.low { color: var(--low); }
  .stat-value.avg { color: var(--accent); }

  .chart-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 1.5rem 1.5rem 1rem;
    position: relative;
    overflow: hidden;
  }

  .chart-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
  }

  .chart-container {
    position: relative;
    height: 380px;
  }

  .controls {
    display: flex;
    gap: 0.5rem;
    justify-content: flex-end;
    margin-top: 1rem;
    flex-wrap: wrap;
  }

  button {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    background: transparent;
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 0.4rem 0.9rem;
    border-radius: 6px;
    cursor: pointer;
    transition: all 0.15s;
  }

  button:hover, button.active {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(56,189,248,0.07);
  }

  .hint {
    font-family: 'DM Mono', monospace;
    font-size: 0.62rem;
    color: var(--muted);
    margin-top: 0.8rem;
    text-align: center;
    letter-spacing: 0.05em;
  }
</style>
</head>
<body>
<div class="wrapper">
  <header>
    <div class="eyebrow">● Execution Analytics</div>
    <h1>Planning Accuracy <span>Trend</span> Over Time</h1>
    <div class="stats-row">
      <div class="stat">
        <span class="stat-label">Peak</span>
        <span class="stat-value high" id="stat-max">—</span>
      </div>
      <div class="stat">
        <span class="stat-label">Floor</span>
        <span class="stat-value low" id="stat-min">—</span>
      </div>
      <div class="stat">
        <span class="stat-label">Average</span>
        <span class="stat-value avg" id="stat-avg">—</span>
      </div>
      <div class="stat">
        <span class="stat-label">Data Points</span>
        <span class="stat-value" id="stat-count" style="color:var(--text)">—</span>
      </div>
    </div>
  </header>

  <div class="chart-card">
    <div class="chart-container">
      <canvas id="chart"></canvas>
    </div>
    <div class="controls">
      <button onclick="resetZoom()">Reset Zoom</button>
      <button onclick="toggleMA()" id="ma-btn">+ 7-Day MA</button>
      <button onclick="toggleFill()" id="fill-btn">Toggle Fill</button>
    </div>
    <div class="hint">🖱 Scroll to zoom · Drag to pan · Hover for values</div>
  </div>
</div>

<script>
// ── DATA ── digitized from chart image (Feb–Jun 2025)
const rawData = [
  {x:'2025-02-01',y:184},{x:'2025-02-04',y:325},{x:'2025-02-07',y:240},{x:'2025-02-10',y:295},
  {x:'2025-02-13',y:180},{x:'2025-02-16',y:310},{x:'2025-02-19',y:200},{x:'2025-02-22',y:155},
  {x:'2025-02-25',y:280},{x:'2025-02-28',y:200},{x:'2025-03-03',y:141},{x:'2025-03-06',y:269},
  {x:'2025-03-09',y:215},{x:'2025-03-12',y:337},{x:'2025-03-15',y:170},{x:'2025-03-18',y:155},
  {x:'2025-03-21',y:245},{x:'2025-03-24',y:290},{x:'2025-03-27',y:160},{x:'2025-03-30',y:200},
  {x:'2025-04-02',y:341},{x:'2025-04-05',y:265},{x:'2025-04-08',y:190},{x:'2025-04-11',y:275},
  {x:'2025-04-14',y:155},{x:'2025-04-17',y:230},{x:'2025-04-20',y:180},{x:'2025-04-23',y:310},
  {x:'2025-04-26',y:195},{x:'2025-04-29',y:255},{x:'2025-05-02',y:170},{x:'2025-05-05',y:235},
  {x:'2025-05-08',y:290},{x:'2025-05-11',y:155},{x:'2025-05-14',y:215},{x:'2025-05-17',y:180},
  {x:'2025-05-20',y:305},{x:'2025-05-23',y:160},{x:'2025-05-26',y:240},{x:'2025-05-29',y:195},
  {x:'2025-06-01',y:305},{x:'2025-06-04',y:185},{x:'2025-06-07',y:139},{x:'2025-06-10',y:320},
  {x:'2025-06-13',y:255},{x:'2025-06-16',y:180},{x:'2025-06-19',y:335},{x:'2025-06-22',y:210},
  {x:'2025-06-25',y:158},{x:'2025-06-28',y:280}
];

const labels = rawData.map(d => d.x);
const values = rawData.map(d => d.y);

// Moving average helper
function movingAvg(data, window) {
  return data.map((_, i) => {
    const start = Math.max(0, i - Math.floor(window/2));
    const slice = data.slice(start, start + window);
    return Math.round(slice.reduce((a,b)=>a+b,0)/slice.length);
  });
}

// Stats
const max = Math.max(...values), min = Math.min(...values);
const avg = Math.round(values.reduce((a,b)=>a+b,0)/values.length);
document.getElementById('stat-max').textContent = max + '%';
document.getElementById('stat-min').textContent = min + '%';
document.getElementById('stat-avg').textContent = avg + '%';
document.getElementById('stat-count').textContent = values.length;

// Chart
const ctx = document.getElementById('chart').getContext('2d');
let fillEnabled = true, maEnabled = false;

const gradient = ctx.createLinearGradient(0, 0, 0, 380);
gradient.addColorStop(0, 'rgba(56,189,248,0.3)');
gradient.addColorStop(1, 'rgba(56,189,248,0.0)');

const chart = new Chart(ctx, {
  type: 'line',
  data: {
    labels,
    datasets: [
      {
        label: 'Execution Efficiency (%)',
        data: values,
        borderColor: '#38bdf8',
        borderWidth: 1.5,
        pointRadius: 3,
        pointHoverRadius: 6,
        pointBackgroundColor: '#38bdf8',
        pointBorderColor: '#0b0f1a',
        pointBorderWidth: 1.5,
        fill: true,
        backgroundColor: gradient,
        tension: 0.3,
        order: 1
      },
      {
        label: '7-Day Moving Avg',
        data: movingAvg(values, 7),
        borderColor: '#f472b6',
        borderWidth: 2,
        borderDash: [6,3],
        pointRadius: 0,
        pointHoverRadius: 4,
        fill: false,
        tension: 0.4,
        hidden: true,
        order: 0
      }
    ]
  },
  options: {
    responsive: true,
    maintainAspectRatio: false,
    interaction: { mode: 'index', intersect: false },
    plugins: {
      legend: {
        display: true,
        labels: {
          color: '#94a3b8',
          font: { family: 'DM Mono', size: 11 },
          boxWidth: 24,
          padding: 16
        }
      },
      tooltip: {
        backgroundColor: '#1e293b',
        borderColor: '#334155',
        borderWidth: 1,
        titleColor: '#38bdf8',
        bodyColor: '#e2e8f0',
        titleFont: { family: 'Syne', size: 12, weight: '600' },
        bodyFont: { family: 'DM Mono', size: 11 },
        padding: 12,
        callbacks: {
          title: items => {
            const d = new Date(items[0].label);
            return d.toLocaleDateString('en-US', { month: 'short', day: 'numeric', year: 'numeric' });
          },
          label: item => ` ${item.dataset.label}: ${item.parsed.y}%`
        }
      },
      zoom: {
        pan: { enabled: true, mode: 'x' },
        zoom: {
          wheel: { enabled: true },
          pinch: { enabled: true },
          mode: 'x'
        }
      }
    },
    scales: {
      x: {
        ticks: {
          color: '#475569',
          font: { family: 'DM Mono', size: 10 },
          maxRotation: 0,
          maxTicksLimit: 8,
          callback(val, i) {
            const d = new Date(labels[i]);
            return d.toLocaleDateString('en-US', { month: 'short', day: 'numeric' });
          }
        },
        grid: { color: 'rgba(255,255,255,0.04)' },
        border: { color: '#1e2d40' }
      },
      y: {
        min: 100,
        max: 380,
        ticks: {
          color: '#475569',
          font: { family: 'DM Mono', size: 10 },
          callback: v => v + '%'
        },
        grid: { color: 'rgba(255,255,255,0.04)' },
        border: { color: '#1e2d40' }
      }
    }
  }
});

function resetZoom() { chart.resetZoom(); }

function toggleMA() {
  maEnabled = !maEnabled;
  chart.data.datasets[1].hidden = !maEnabled;
  chart.update();
  const btn = document.getElementById('ma-btn');
  btn.textContent = maEnabled ? '− 7-Day MA' : '+ 7-Day MA';
  btn.classList.toggle('active', maEnabled);
}

function toggleFill() {
  fillEnabled = !fillEnabled;
  chart.data.datasets[0].backgroundColor = fillEnabled ? gradient : 'transparent';
  chart.update();
  document.getElementById('fill-btn').classList.toggle('active', !fillEnabled);
}
</script>
</body>
</html>
