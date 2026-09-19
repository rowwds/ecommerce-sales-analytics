# 🛒 Global E-Commerce Sales & Profitability Analysis

An end-to-end data analytics project evaluating sales performance, profitability drivers, fulfillment efficiency, and sub-category dynamics for a global e-commerce enterprise.

---

## 📌 Project Overview
* **Objective:** Analyze order-level transactional data to identify high-revenue vs. loss-making product sub-categories, evaluate shipping delay impacts, and optimize overall profit margins.
* **Data Source:** Global Superstore Sales Dataset (~10,000 order records)
* **Tech Stack:** 
  * **Data Cleaning & Feature Engineering:** Microsoft Excel (Custom Date formatting, text normalization, structured tables, calculated fields, and Pivot Table validation)
  * **Database & Querying:** MySQL Workbench (Relational schema modeling, multi-table joins, window functions, and business aggregations) — *In Progress*
  * **Visualization:** Tableau Public (Interactive executive dashboard) — *Upcoming*
  * **Documentation:** GitHub

---

## ❓ Core Analytical Questions

1. **Sub-Category Profitability Divergence:** Which product sub-categories generate high sales revenue but operate at a net financial loss (e.g., **Tables** losing **($17,725.48)**), and which ones produce the highest profit margins (e.g., **Labels** at **44.42%**)?
2. **Category Performance Comparison:** How do overall sales revenue and profit margins compare across the three primary product categories (**Technology**, **Office Supplies**, and **Furniture**)?
3. **Fulfillment & Shipping Efficiency:** How does shipping delay duration (`Shipping_Delay_Days`) affect order volume across different fulfillment priority tiers (`Express`, `Standard`, `Delayed`)?

---

## 💡 Key Analytical Insights (Excel Baseline Phase)

* **Revenue Leader:** **Technology** generates the highest total revenue at **$836,154.03** with a strong **17.40%** overall profit margin.
* **Primary Loss Driver:** **Tables** represents the largest financial drag, losing **($17,725.48)** on **$206,965.53** in sales (**-8.56% margin**), followed by Bookcases (-$3,472.56).
* **Top Profitability Margin:** **Labels** (**44.42%**) and **Paper** (**43.39%**) yield the highest net return per dollar sold.

---

## 🛠️ Data Engineering & Feature Logic (Excel)

1. **`Shipping_Delay_Days`**: Calculated lead time between `Order Date` and `Ship Date`:
   `=[@Ship Date] - [@Order Date]`
2. **`Profit_Margin_%`**: Computed row-level profitability with zero-division protection:
   `=IFERROR([@Profit] / [@Sales], 0)`
3. **`Order_Priority_Flag`**: Categorized delivery efficiency using multi-condition evaluation:
   `=IFS([@Shipping_Delay_Days] <= 2, "Express", [@Shipping_Delay_Days] <= 5, "Standard", TRUE, "Delayed")`
4. **Calculated Field (`Overall_Profit_Margin`)**: Defined custom aggregate Pivot Table metric to compute true group-level margins:
   `= Profit / Sales`

---

## 🗺️ Project Roadmap
* [x] **Day 1:** Project scoping, target question definition, and repository setup.
* [x] **Day 2:** Excel data hygiene, feature engineering (`Shipping_Delay_Days`, `Order_Priority_Flag`), and Pivot Table validation.
* [ ] **Day 3:** MySQL relational schema modeling, CSV data ingestion, and business intelligence SQL querying.
* [ ] **Day 4:** Executive Tableau dashboard development, interactive filter publishing, and final portfolio documentation.
