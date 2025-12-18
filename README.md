# AdventureWorks-Sales-Customer-Analytics-Power-BI

📌 Project Overview

This project is an end-to-end Power BI analytics solution built on the AdventureWorks dataset to analyze sales performance, profitability, customer behavior, returns, and pricing impact across time, geography, products, and customer segments.

The report demonstrates strong Power Query transformation, a star-schema data model, advanced DAX measures, and business-focused dashboards suitable for real-world decision making.

🎯 Business Objectives

Track Revenue, Profit, Orders, and Returns

Monitor growth vs targets

Identify top & underperforming products

Analyze customer segments and lifetime value

Understand drivers behind returns, pricing, and customer behavior

🗂️ Data Model

Fact Tables

Sales

Returns

Dimension Tables

Calendar Lookup

Customer Lookup

Product Lookup

Territory / Geography

A star schema was implemented to optimize performance and simplify DAX calculations.

🔄 Power Query Transformations

Data type standardization

Date hierarchy creation

Derived columns (Year, Month, Weekday, Weekend flag)

Price adjustments via parameter table

Data cleansing (null handling, formatting)

📊 Dashboards & Metrics
🟢 Dashboard 1: Executive Sales Overview

![Executive Sales Dashboard](Screenshots/Executive_Sales_Overview.jpg)


(Page 1)

Key KPIs

Total Revenue: $24.9M

Total Profit: $10.5M

Total Orders: 25.2K

Return Rate: 2.2%

Core Visuals

Revenue trend (monthly)

Orders by category

Top 10 products (Orders, Revenue, Return %)

Monthly KPIs with MoM comparison

Business Insights

Revenue shows a clear upward trend from 2020–2022

Accessories generate the highest order volume

Certain products show higher return percentages, indicating quality or expectation gaps

🌍 Dashboard 2: Geographic Performance

(Page 2)

Metrics

Revenue by country

Orders by region (Europe, North America, Pacific)

Insights

United States and Australia are top contributors

Europe shows balanced but lower overall contribution

Useful for regional sales strategy & expansion decisions

🎯 Dashboard 3: Target vs Actual & Price Impact

(Page 3)

Metrics

Monthly Orders vs Target

Monthly Revenue vs Target

Monthly Profit vs Target

Adjusted Profit (Price adjustment simulation)

Advanced Features

What-If parameter for price adjustment

Dynamic metric selector (Orders, Revenue, Profit, Returns, Return %)

Insights

Price increases significantly impact profitability

Targets are met more consistently for revenue than profit

Demonstrates scenario analysis using DAX

👥 Dashboard 4: Customer Analytics

(Page 4)

Metrics

Unique Customers: 17.4K

Revenue per Customer: $1,431

Orders by income & occupation

Top 100 customers by revenue

Insights

Skilled Manual & Professional segments drive most revenue

Small group of customers contribute disproportionately (Pareto effect)

Useful for loyalty & retention strategies

🧺 Dashboard 5 & 6: Product & Category Analysis

(Pages 5–6)

Metrics

Orders by category, subcategory, product

Product-level drilldowns

Insights

Accessories dominate volume

Clothing has more fragmented demand

Enables inventory & merchandising optimization

🧠 Dashboard 7: Key Influencers

(Page 7)

Analysis

What drives HomeOwner status

What drives Average Retail Price

Insights

Married customers with higher income are more likely homeowners

Product cost is the strongest driver of retail price

Shows AI-powered insights using Power BI Key Influencers

🧠 DAX Measures Used (Key Examples)
Core Metrics
Total Revenue = SUM(Sales[Revenue])
Total Profit = SUM(Sales[Profit])
Total Orders = COUNT(Sales[OrderNumber])
Total Returns = SUM(Returns[Quantity])

Time Intelligence
Previous Month Revenue =
CALCULATE(
    [Total Revenue],
    PREVIOUSMONTH('Calendar Lookup'[Date])
)

Rolling Metrics
10-day Rolling Revenue =
CALCULATE(
    [Total Revenue],
    DATESINPERIOD(
        'Calendar Lookup'[Date],
        MAX('Calendar Lookup'[Date]),
        -10,
        DAY
    )
)

Targets & Gap Analysis
Revenue Target Gap =
[Total Revenue] - [Revenue Target]

Customer Metrics
Revenue per Customer =
DIVIDE([Total Revenue], [Total Customers])

Return Metrics
Return Rate =
DIVIDE([Total Returns], [Total Orders])

🛠️ Tools & Skills Demonstrated

Power BI Desktop

Power Query (ETL)

DAX (Time Intelligence, What-If, Rolling Metrics)

Data Modeling (Star Schema)

Business Analytics & Storytelling
