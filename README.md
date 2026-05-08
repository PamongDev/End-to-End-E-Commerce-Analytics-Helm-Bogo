# End-to-End E-Commerce Analytics – Helm Bogo

## 📌 Project Overview
This repository contains an end-to-end data engineering and business intelligence project tailored for an e-commerce operation (UMKM Helm Bogo). The project spans from architectural database design to the deployment of interactive, enterprise-grade analytical dashboards. The primary objective is to provide actionable insights into sales profitability, operational return costs (revenue leakage), and procurement efficiency.

## 🛠️ Tech Stack & Tools
- **Data Engineering / SQL:** Relational database design, logical schema architecture, and complex data joins.
- **Business Intelligence / Tableau:** Advanced visualization techniques (Butterfly Charts, Treemaps, Dual-Axis M2M Trends, Donut Charts), Calculated Fields, and Context Filtering.

## 🗄️ Data Architecture & Modeling
To accurately simulate a real-world e-commerce ecosystem, a robust **15-table relational database** was designed.
- **Fact Tables:** - `fact_sales`: Records transactional sales data.
  - `fact_return`: Tracks items sent back by customers, linked via `order_id` and `product_id`.
  - `fact_purchase`: Monitors procurement and restock transactions.
- **Dimension Tables:** Includes `dim_products`, `dim_stores`, `dim_dates`, `dim_suppliers`, etc.
- **Data Relationships:** Utilized strict `LEFT JOIN` methodologies (using functions like `ZN()` for null handling) to combine sales and return data without losing successful transaction records, ensuring 100% precision in Return Rate calculations.

---

## 📊 Dashboard Modules & Key Scenarios

### 1️⃣ Profitability & Margin Analysis
Designed to track top-line revenue and bottom-line health, adjusting for a fixed-markup business rule (28.57% flat margin).
- **KPIs:** Gross Profit, Net Profit, Gross Margin %.
- **Key Visualizations:**
  - **Treemap:** *Margin by Category* to visually highlight the dominance of specific product lines (e.g., Helm Bogo vs. Accessories).
  - **Horizontal Bar Charts:** *Top 10* and *Bottom 10 Products* sorted by Gross Profit to instantly identify cash cows and underperformers.
  - **Trend Lines:** *Gross Profit Over Time* for historical performance tracking.

### 2️⃣ Return Analysis & After-Sales Performance
Focuses on tracking operational bottlenecks and the financial impact of returned goods.
- **KPIs:** Return Rate %, Total Refund Amount, Sunk Cost Loss.
- **Key Visualizations:**
  - **Butterfly Chart:** A head-to-head comparison of *Restockable* vs. *Non-Restockable* (Sunk Cost) return items broken down by category.
  - **Donut Chart:** *Return Reason* proportion (e.g., Shipping Damage vs. Wrong Size) integrated directly with data labels for a clean UI.
  - **M2M Dual Axis Trend:** A combined view of Return Rate % (Line) and Sunk Cost Volume (Bar) over time.
  - **Top 10 Most Returned Products:** Highlights the specific SKUs causing the most financial leakage.

### 3️⃣ Procurement & Purchase Analysis
Evaluates supply chain efficiency and capital expenditure on inventory.
- **KPIs:** Total Purchase Cost, Total PO Count (Distinct), Average PO Value.
- **Key Visualizations:**
  - **Area Chart:** *Purchase Trend* to visualize the volume of capital outflow over time.
  - **Supplier Performance Matrix:** Cost vs. Lead Time analysis to evaluate supplier reliability.
  - **PO Status Distribution:** Monitoring Pending vs. Completed purchase orders.

---

## 💡 Actionable Business Insights
1. **Sunk Cost Mitigation:** By isolating "Non-Restockable" items via the Butterfly chart, the business can identify specific accessory categories frequently damaged during shipping and renegotiate logistics protocols.
2. **Pricing Strategy Evaluation:** Transforming the limitation of a flat 28.57% margin into an analytical advantage by drilling down into absolute Gross Profit, revealing which specific products drive true volume.
3. **Inventory Optimization:** Utilizing the Top 10 Most Returned Products list to strategically discontinue or overhaul quality control for problematic SKUs.

---

## 👨‍💻 Author
**Muhamad Fahmi Ammar** *Data Enthusiast | Business Intelligence | System Analysis*
