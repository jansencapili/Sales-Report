# 📊 Global Sales Performance Dashboard

An interactive **Power BI Sales Analytics Dashboard** designed to monitor revenue, order activity, customer performance, inventory levels, and sales target attainment across regions, product categories, and time.

The project combines sales, inventory, order processing, sales targets, and marketing campaign data into a single analytical model to provide a broader view of business performance.

---

## 📌 Project Overview

Sales teams often need to look at multiple sources to understand whether revenue is performing as expected.

This dashboard brings key business metrics into one interactive Power BI report, allowing users to explore:

- 💰 Revenue performance
- 🛒 Order activity
- 👥 Customer activity
- 🎯 Sales target attainment
- 📦 Inventory levels
- 🌎 Regional performance
- 📢 Campaign and promotion data

The report is designed for **sales managers, business analysts, and operations teams** who need a consolidated view of sales performance.

---

# 🎯 Business Objective

The main objective of this project is to create a centralized sales performance report that helps answer questions such as:

- Are sales on track against the target?
- Which regions are generating the most revenue?
- Which product categories contribute the most sales?
- Are inventory levels aligned with sales demand?
- Which regions or categories may require further investigation?
- Can campaign and promotion data be connected to sales performance?

Instead of analyzing these areas separately, the dashboard brings them together into one interactive report.

---

# 🛠️ Technology Stack

| Tool / Technology | Purpose |
|-------------------|---------|
| **Power BI Desktop** | Dashboard development and data visualization |
| **Power Query** | Data cleaning, transformation, and preparation |
| **DAX** | Measures, KPIs, calculations, and business logic |
| **Data Modeling** | Connecting fact and dimension tables |
| **Row-Level Security (RLS)** | Restricting regional data access by user |
| **Power BI Template (.pbit)** | Reusable report development format |
| **PNG** | Dashboard and data model previews |

---

# 🏗️ Data Model

The report uses a **star-schema-style data model** with multiple fact tables connected to shared dimensions.

### Fact Tables

- `fact_sales`
- `fact_inventory`
- `fact_order_process`
- `fact_campaign_spend`
- `fact_promotion_coverage`
- `fact_sales_targets`

### Dimension Tables

- `dim_customer`
- `dim_product`
- `dim_geo`
- `dim_date`
- `dim_campaign`
- `dim_order_flags`

A dedicated `_measures` table is also used to organize DAX measures and keep the model easier to maintain.

---

## 🔗 Data Model Overview

The central `fact_sales` table contains line-level sales transactions and connects with supporting dimensions and business-process fact tables.

```text
                         ┌───────────────┐
                         │  dim_customer │
                         └───────┬───────┘
                                 │
                                 │
┌────────────┐           ┌───────▼───────┐           ┌─────────────┐
│  dim_date  │──────────▶│   fact_sales  │◀──────────│ dim_product │
└────────────┘           └───────┬───────┘           └─────────────┘
                                 │
                    ┌────────────┼────────────┐
                    │            │            │
                    ▼            ▼            ▼
             fact_inventory  sales_targets  dim_geo
                    │
                    │
                    ▼
             Inventory Analysis

       Marketing & Promotion Data
                    │
          ┌─────────┴──────────┐
          ▼                    ▼
 fact_campaign_spend   fact_promotion_coverage
          │                    │
          └─────────┬──────────┘
                    ▼
            Campaign Analysis
