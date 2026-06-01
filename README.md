# Coffee Shop Sales Analysis ☕📊

An end-to-end data analytics project focused on analyzing transactional sales from a coffee shop with multiple store locations (Astoria, Lower Manhattan, Hell's Kitchen). The goal is to ingest, clean, and transform raw transactional data, build robust statistical aggregations using Pivot Tables, and present an interactive, dynamic Executive Dashboard in Microsoft Excel to uncover optimization opportunities for revenue, footfall, and operational hours.

---

## 🖼️ Dashboard Preview

![Coffee Shop Sales Dashboard](<dashboard/Coffee shop sales Dashboard.png>)

---

## 📌 Project Objectives & Business Problems
The core objective is to convert granular transactional logs into operational insights to improve sales performance and resource planning. Key business questions answered include:
* **Sales & Footfall Profiles:** How do total revenue, transaction volumes (footfall), and average order values fluctuate monthly and across different store locations?
* **Temporal Dynamics:** What are the peak sales hours and days of the week? When do busiest periods occur, and how should staffing adapt?
* **Product Performance Analysis:** Which product categories (Coffee, Tea, Bakery, etc.) and specific items drive the majority of the revenue and order volume?
* **Sizing Demographics:** How does sales distribution vary based on product size configurations (Large, Regular, Small)?

---

## 🛠️ Data Pipeline & Process Steps

### 1. Data Ingestion & ETL Transformation (Power Query)
* **Ingestion:** Granular transaction files were imported directly via Power Query to handle structural transformation efficiently.
* **Feature Engineering & Formatting:** 
  * Extracted structural temporal fields including `Month Name`, `Day Name`, `Hour`, and `Day of Week` using Power Query's date/time transformations to establish time-series analysis capabilities.
  * Extracted product sizing parameters from item detail strings to populate a clean, uniform `Size` field (**Large**, **Regular**, **Small**, and **Not defined**).
  * Generated explicit calculated columns for `Total Bill` (`transaction_qty` × `unit_price`) to ensure consistent transactional valuations.

### 2. Analytical Modeling & Data Aggregations (Pivot Tables)
* Engineered specialized structural multi-axis Pivot Tables to compute:
  * Total footfall metrics (count of unique transaction IDs).
  * Total units sold (`Sum of transaction_qty`) distributed across daily operational hours and weekdays.
  * Financial yield segments broken down by `Product Category`, `Product Type`, and individual `Product Details`.
  * Store performance profiling across different strategic locations.

### 3. Dynamic Interactive Dashboard Construction
* Consolidated the isolated pivot visualizations into a cohesive, user-friendly interactive interface.
* **Interactive Slicers:** Deployed localized slicers linked across multiple data grids allowing interactive filtering based on **Month Name** and **Day Name** parameters.
* **High-Impact Data Visualization:** Structured conditional metrics with clean KPI cards tracking high-level targets (Sales, Footfall, Average Order Value).

---

## 📈 Key Insights & Dashboard Discoveries

Based on the aggregated pivot models extracted from the dataset:
* **Top Financial Engines:** The **Coffee** category is the dominant revenue generator, contributing over **$269,952**, followed by **Bakery** at **$82,315** and **Drinking Chocolate** at **$72,416**.
* **Product Size Distribution:** Consumer demand favors standard size configurations, with the **Regular (RG)** and **Large (LG)** options driving the majority of transactional volume compared to Small (SM).
* **Store Footfall Parity:** Sales distributions are uniformly strong across the physical brick-and-mortar locations:
  * **Hell's Kitchen:** Leads marginally with **$50,735** in the evaluated target snapshot.
  * **Astoria:** Formidably matching close behind at **$50,599**.
  * **Lower Manhattan:** Steady output at **$47,782**.
* **Hourly Peak Load:** Operational bottlenecks or peak service windows consistently ramp up during the morning window starting from **7:00 AM to 10:00 AM**, with absolute peak volume registering between **8:00 AM and 9:00 AM**.

---

## 💻 Tech Stack & Tools Used
* **Microsoft Excel:** Core framework used for layout design, cell formulas, formatting, and building the terminal UI presentation layer.
* **Power Query Editor:** Utilized for data cleaning, text mining size dimensions, parsing raw timestamps into analytical parameters, and schema matching.
* **Excel Pivot Architecture:** Deployed for high-throughput aggregation, grouping matrices, and feeding layout chart widgets.

---

## 📂 Repository Structure

The repository is structured into organized directories for clean file tracking:

```filesystem
├── dashboard/
│   └── Coffee shop sales Dashboard.png   # Main export preview image of the final UI layout
├── data/
│   ├── Coffee Shop Sales raw.xlsx         # Unprocessed historical transactional records 
│   └── Coffee shop sales.xlsx            # Primary analytics workbook with Power Query steps & Pivot grids
└── README.md                             # Project documentation and summary
