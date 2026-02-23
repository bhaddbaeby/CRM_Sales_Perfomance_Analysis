CRM Sales Perfomance Analysis | SQL + Python + Power BI + Google Colab
-----------------------------------------------------------------------
## Project Overview 
This project analyzes CRM sales data to identify revenue trends, conversion performance, and sales bottlenecks.

The objective is to transform raw CRM data into actionable business insights through data cleaning, exploratory analysis, KPI modeling, and interactive dashboard development.

This project simulates a real-world Business Intelligence case where management needs visibility into sales performance and win rate decline.

## Project Architecture
- SQL – Data extraction, filtering, joins, and aggregations
- Python – Data cleaning and exploratory data analysis (EDA)
- Power BI – Interactive dashboard development
- DAX – KPI calculations and revenue impact metrics

## Business Problem
Management observed:
- Declining revenue in the last quarter
- Inconsistent win rates across regions
- Lack of visibility into deal stage bottlenecks
- No centralized dashboard for performance monitoring
The company requires a structured analysis and executive dashboard to support data-driven decision-making.

## Business Objectives
- Monitor Total Revenue and Sales Performance
- Measure Win Rate and Conversion Trends
- Analyze Sales Agent performance
- Identify Product contribution to revenue
- Evaluate Deal Stage distribution
- Provide actionable business recommendations

## Tech Stack
- SQL
- Data querying & aggregation
- Python (Pandas, Matplotlib, Seaborn) 
– Data preprocessing & EDA
- Power BI
- Dashboard development
- DAX 

## Dataset Description
The dataset simulates CRM export data containing:
- opportunity_id
- sales_agent
- deal_stage
- close_date
- revenue
- product
- avg_deal_size
- 10+

## Project Methodology
1️⃣ Requirement Gathering
- Stakeholder discussion (Sales & Management)
- KPI definition
- Dashboard structure planning
- Business Requirement Documentation (BRD)

2️⃣ Data Cleaning & Validation
Performed using SQL & Python:
- Removed duplicate opportunity records
- Handled missing values
- Standardized date format
- Validated revenue totals
- Checked deal stage consistency

3️⃣ Exploratory Data Analysis (EDA)
Key analysis performed:
- Monthly revenue trend
- Product revenue comparison
- Deal stage distribution
- Sales leaderboard performance
- Win rate vs total revenue correlation

4️⃣ Data Modeling
Implemented Star Schema in Power BI:
- Dimension Tables: Date, Product, Sales Agent, Deal Stage
- Created DAX Measures:
  * Total Revenue = SUM(df_master[revenue])
  * Won Deals = 
CALCULATE(
    COUNT(df_master[opportunity_id]),
    df_master[deal_stage] = "Won"
)
  * Win Rate = DIVIDE([Won Deals], [Total Opportunities])
  * Total Opportunities = COUNT(df_master[opportunity_id])
  * Lost Deals = 
CALCULATE(
    COUNTROWS(df_master),
    df_master[deal_stage] = "Lost"
)
  * Avg Sales Cycle = AVERAGE(df_master[sales_price])
  * Avg Deal Size = 
DIVIDE([Total Revenue], [Won Deals])

## Dashboard Features
🔹 Executive KPI Overview
- Total Revenue: 1.33M
- Won Deals: 3,509
- Win Rate: 57.36%
- Total Opportunities: 6,117
- Avg Sales Cycle: 1.89

🔹 Sales Leaderboard
- Revenue per Sales Agent
- Avg Deal Size
- Avg Sales Cycle
- Win Rate ranking

🔹 Revenue Analysis
- Revenue by Product
- Revenue by Month

🔹 Deal Stage Analysis
- Won
- Lost
- Engaging
- Prospecting

🔹 Sales Performance Scatter Plot
- Win Rate vs Total Revenue
- Identify high-performing & underperforming agents

## Key Insight
- Overall Win Rate stands at 57.36%
- Significant drop-off observed in Engaging stage
- Top 5 sales agents contribute disproportionately to total revenue
- Certain products drive higher revenue but have lower win rates
- High revenue does not always correlate with high win rate


## Business  Recommendations
✔ Improve conversion strategy at Engaging stage
✔ Implement targeted coaching for low win-rate agents
✔ Focus on high-margin product bundles
✔ Monitor performance monthly via dashboard
✔ Introduce incentive structure based on win rate & revenue balance

## Skills Demonstrated
- Data Cleaning & Transformation
- SQL Aggregations & Joins
- Exploratory Data Analysis (EDA)
- Data Visualization & Storytelling
- KPI Design with DAX
- Business Insight Generation
- Outcome
- Business Analysis
- DAX


## Dashboard preview
![CRM_Sales_Perffomance_Analysis](assets/Dashboard_CRM.png)

