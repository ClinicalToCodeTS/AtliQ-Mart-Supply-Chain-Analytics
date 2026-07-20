# 📦 Atliq Mart FMCG Supply Chain Analytics Dashboard
---
## 🎯 Short Description & Purpose
This interactive Power BI dashboard provides executive management with a 360-degree diagnostic view of supply chain service levels for **Atliq Mart**, a growing FMCG manufacturer in Gujarat, India. Built to investigate a sudden wave of unexplained annual contract non-renewals prior to a planned multi-city expansion, the dashboard tracks daily delivery SLAs—**On-Time (OT%)**, **In-Full (IF%)**, and **On-Time In-Full (OTIF%)**—against customer-specific target benchmarks to identify operational bottlenecks and protect key enterprise accounts.
---
## 🛠️ Tech Stack
* **Data Staging & Validation:** Microsoft Excel (`.xlsx`)
* **Business Intelligence Tool:** Power BI Desktop
* **Data Transformation & ETL:** Power Query (Data cleaning)
* **Data Modeling:** Star Schema with a double-fact table layout (`fact_orders_aggregate` & `fact_order_lines`)
* **Calculations & Advanced Logic:** DAX (Data Analysis Expressions) for volume-weighted target aggregation (`SUMX` + `SUMMARIZE`) 
* **UI/UX Design:** Custom page-navigation action buttons, interactive slicers, red conditional formatting, and neutral corporate KPI card styling
---
## 📊 Data Source
* **Origin:** Operational transactional datasets provided by Atliq Mart (Codebasics Supply Chain Challenge C2).
* **Dataset Scale:** 
  * `fact_orders_aggregate` (31,729 unique order records).
  * `fact_order_lines` (57,096 line-item records across 1.34 Cr total ordered quantity).
  * 4 Dimension Tables (`dim_customers` [35 rows], `dim_products` [18 SKUs], `dim_date` [183 days], `dim_targets_orders` [35 customer target records]).
---
## ✨ Features & Highlights
### 1️⃣ Business Problem
Atliq Mart operates across Surat, Ahmedabad, and Vadodara, with plans to expand into Tier-1 metro cities within two years. However, executive leadership discovered a critical issue: **key enterprise customers were unexpectedly refusing to renew their annual contracts.** Management did not know the underlying causes behind these non-renewals and was reluctant to invest capital in expanding to new cities until this customer retention mystery was solved.
### 2️⃣ Dashboard Goal
* Determine whether delivery service issues were driving contract cancellations.
* Monitor daily **OT%**, **IF%**, and **OTIF%** metrics against customer target SLAs.
* Uncover specific fulfillment and logistics bottlenecks across cities, customers, and product categories.
* Provide actionable operational recommendations to restore service levels and secure contract renewals.
### 3️⃣ Key Visuals & Charts Used
* **Executive KPI Cards with Sparklines:** Displays high-level actuals vs. weighted targets for OTIF% (29.02%), OT% (59.03%), IF% (52.78%), LIFR% (65.96%), and VOFR% (96.59%).
* **Performance Matrix Table:** Displays `Tot. orders`, `OTIF%`, `OTIF Tgt%`, `OT%`, `OT Tgt%`, `IF%`, and `IF Tgt%` by City and Customer, featuring red conditional formatting for below-target performance and subtotal roll-ups.
* **OTIF and Target by City (Combo Line & Column Chart):** Compares actual city OTIF% (columns) against mathematically accurate volume-weighted city targets (orange line).
* **Top 5 Customers by Delay % (Table with Heatmap):** Pinpoints the highest-risk accounts experiencing severe delivery delay rates (>70%).
* **Delayed % by Product Category (Donut Chart):** Breaks down delay incidents across Dairy (30.38%), Beverages (29.81%), and Food (29.16%).
* **Monthly Delay Trend (Line Chart):** Tracks monthly delay counts to identify seasonal or operational spikes (peaking at 2,248 delayed orders).
* **Dynamic Top-Performer Cards (Detailed Insights):** Displays top-selling SKU (**AM Milk 250** | 1.28M volume), highest-order city (**Vadodara** | 5M volume), and best OTIF customer (**Propel Mart** | 40.92% OTIF) using `REMOVEFILTERS()` DAX logic.
### 4️⃣ Business Impact & Key Insights
* **The Root Cause Solved:** Delivery failure was proven to be the primary driver of contract cancellations, revealing a massive **36.08% OTIF deficit** (29.02% actual vs. 65.10% weighted target).
* **The LIFR vs. VOFR Fulfillment Paradox:** Volume Fill Rate (**96.59%**) is high while Line Fill Rate (**65.96%**) is severely low. This proves Atliq Mart does not suffer from stockouts; rather, warehouses are making **line-item picking errors** (partial shipments), dropping order-level In-Full (IF%) to **52.78%**.
* **Delay Lateness Severity:** Out of 31,729 total orders, **13,000 orders were delayed (40.97% delay rate)**. While overall average delay is **0.42 days**, delayed shipments average **1.69 days late (~40 hours)**, causing severe retail shelf stockouts.
* **High-Risk Accounts Flagged:** Churn risk is heavily concentrated in three major accounts experiencing >70% delay rates: **Acclaimed Stores** (Surat: 6.93% OTIF), **Lotus Mart** (Ahmedabad: 7.97% OTIF), and **Coolblue** (Vadodara: 7.14% OTIF).
* **Strategic Roadmap:** Recommended implementing barcode/RFID scanner WMS picking to eliminate the 34.04% line error rate, restructuring 3PL carrier contracts with delay penalties, and allocating priority safety stock for top SKU AM Milk 250.
### 5️⃣ Date Range & Dashboard Screenshots
* **Date Period Analyzed:** **March 2022 – August 2022** (5 Months / 183 Calendar Days)
#### 📷 Visual Demonstration:
##### Cover Page Landing Portal
![Home Page](Home%20Page.png)
##### Performance Overview Page
![Performance Overview](Performance%20Overview.png)
##### Detailed Insights Page
![Detailed Insights](Detailed%20Insights.png)
##### Delay Analysis Page
![Delay Analysis](Delay%20Analysis.png)# AtliQ-Mart-Supply-Chain-Analytics
