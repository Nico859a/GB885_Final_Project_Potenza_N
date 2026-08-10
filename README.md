# Rush Sportswear Analysis — Final Project

Exploratory analysis evaluating sales performance, product demand, retailer metrics, and regional trends for **Rush Sportswear**.

---

## Project Overview

This project analyzes three primary business datasets (Products, Retailers, and Sales) to answer key executive questions regarding revenue drivers, product category performance, regional purchasing behaviors, and sales channels.

### Key Business Questions Addressed:
1. **Product Performance:** Which product lines generated the highest total sales and profit margins?
2. **Gender-Specific Markets:** Which states led sales for men's and women's product lines in 2020 and 2021?
3. **Retailer Analysis:** Which retail partners purchased the highest volume of units across fiscal years?
4. **Channel & Regional Trends:** How do sales methods (In-store, Online, Outlet) and regional performance break down year-over-year?

---

## Datasets

The analysis merges three data tables via unique primary/foreign keys (`PRODUCT_ID`, `RETAILER_ID`):
* `TABLE_PRODUCTS_885.csv`: Product metadata, categories, and identifiers.
* `TABLE_RETAILER_885.csv`: Retailer details, geographic regions, states, and cities.
* `TABLE_SALES_885.csv`: Transactional records, invoice dates, units sold, price per unit, operating margins, and sales methods.

---

## Pipeline Steps

1. **Data Acquisition:** Loaded source CSV files directly from GitHub.
2. **Inspection & Cleaning:** 
   * Converted invoice dates to datetime objects and stripped redundant date columns.
   * Handled missing and non-standard numeric entries in units sold and price columns.
   * Fixed categorical typos (e.g., standardizing sales channel naming).
   * Cleaned anomalous IDs and applied Windsorization (clipped at 5th/95th percentiles) to manage extreme outliers in numerical metrics.
3. **Feature Engineering:** Created calculated fields for `TOTAL_SALES` (`UNITS_SOLD * PRICE_PER_UNIT`) and `PROFIT` (`TOTAL_SALES * OPERATING_MARGIN`).
4. **Exploratory Analysis & Visualization:** Evaluated top-performing states, monthly seasonal trends, sales channel breakdown via pivot tables and visualizations..

---

## How to open

You can run this notebook interactively in your browser using Google Colab or by opening the `.ipynb` file directly in your local Jupyter notebook.
