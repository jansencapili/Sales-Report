# Sales-Report
Sales Report: Global Sales Performance Dashboard

An interactive Power BI report built to track revenue performance, order volume, customer activity, and inventory levels across regions, product categories, and time — with drill-down support for sales targets and campaign effectiveness.

Short Description / Purpose

The Sales Report Dashboard is a Power BI report designed to help sales and operations teams monitor revenue, orders, and target attainment across regions and product categories, while also connecting that performance to inventory levels, order fulfillment, and marketing campaign activity. It's built for sales managers, revenue analysts, and operations teams who need a single view spanning sales, inventory, and campaign data.

Tech Stack

The dashboard was built using the following tools and technologies:

📊 Power BI Desktop – Main data visualization platform used for report creation.

📂 Power Query – Data transformation and cleaning layer for reshaping and preparing the data.

🧠 DAX (Data Analysis Expressions) – Used for calculated measures (housed in a dedicated _measures table), KPIs, and conditional logic.

📝 Data Modeling – A star-schema-style model connecting fact tables (fact_sales, fact_inventory, fact_order_process, fact_campaign_spend, fact_promotion_coverage, fact_sales_targets) to shared dimension tables (dim_customer, dim_product, dim_geo, dim_date, dim_campaign, dim_order_flags), enabling cross-filtering across sales, inventory, and marketing.

🔒 Row-Level Security – A security table mapping user_email to region, restricting each user's view to their own region.

📁 File Format – .pbit (Power BI template) for development and .png for data model and dashboard previews.
Data Source

The model is built around a central fact_sales table (line-level sales transactions with order dates, discounts, and line totals) joined to:

dim_customer – customer details including region, segment, credit limit, and payment terms

dim_product – product hierarchy (category, subcategory, brand, supplier, unit price)

dim_geo – city/region geography

dim_date – calendar table (Date, Month, Year) driving time-based analysis

dim_campaign / fact_campaign_spend / fact_promotion_coverage – marketing campaign budgets, spend, clicks, impressions, and which products each campaign covers

fact_inventory – inventory levels by product and date

fact_order_process – order lifecycle timestamps (order, invoice, delivery, order-to-pay duration)

fact_sales_targets – target revenue by period, used to calculate attainment

dim_order_flags – order/channel flags and priority tagging

Features / Highlights

Business Problem Sales and operations stakeholders need to know, at a glance, whether revenue is on pace against targets — and why — without stitching together separate sales, inventory, and campaign reports. Questions like "which regions are underperforming their targets?" or "is a revenue dip tied to low inventory or under-invested campaigns?" are hard to answer from raw transactional data alone.

Goal of the Dashboard To deliver a single interactive report that:

Tracks revenue, orders, active customers, and target attainment in real time

Lets users slice performance by year and region

Connects sales trends to product category performance and inventory levels

Supports fast identification of underperforming regions or categories


Walkthrough of Key Visuals

Key KPIs (Top Left)

Revenue: 527K

Total Orders: 80

Active Customers: 47

Target Sales %: 95.41%

Year & Region Filter Panel Slicers for Year (2025, 2026) and Region (Asia Pacific, Europe, Latin America, Middle East) let users filter every visual on the page simultaneously.

Total Revenue by Category (Bar Chart) Ranks product categories — Electronics, Apparel, Home, Sports, Beauty, Industrial — by revenue generated, highlighting which categories drive the most sales.

Total Inventory by Category (Bar Chart) Shows current inventory levels by category, allowing quick comparison against revenue performance to spot potential stock-driven sales constraints.

Sum of Line Total by Month (Area Chart) Tracks revenue trend across the calendar year, surfacing seasonal peaks and dips in sales activity.

Year/Region Summary Table A detailed breakdown of Revenue, Total Orders, and Target Sales % by Year and Region, with grand totals — the go-to view for identifying which regions are hitting or missing targets.

Business Impact & Insights

Target Tracking: Sales leadership can immediately see attainment against target (95.41% overall) and drill into which regions are lagging.

Inventory-Aware Planning: Comparing revenue by category against inventory by category helps flag categories at risk of stockouts or overstock.

Regional Strategy: Region-level filtering supports territory-specific planning and resourcing decisions.

Campaign ROI (via data model): Linked campaign spend and promotion coverage data enables future analysis of which campaigns are driving revenue by product.


Screenshots / Demos

Sales Report Dashboard
![Dashboard_Preview](https://github.com/jansencapili/Sales-Report/blob/main/Snapshot_of_the_dashboard.png)
