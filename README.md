ASOS Product Analytics: Inventory Optimization & Lost Revenue (Phantom Revenue) Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]([YOUR_GOOGLE_COLAB_LINK_HERE]https://colab.research.google.com/drive/1Iztdftc7pRuwGKvdOL_4waT7HRiaQBZp?usp=sharing)

## 📌 Project Overview
This project performs a comprehensive data analysis using a product dataset from the global fashion platform **ASOS**. The primary objective is to identify inefficiencies in supply chain management and stock availability by calculating **"Phantom Revenue"** (potential revenue lost due to out-of-stock sizes) and segmenting brands through a strategic price vs. stockout rate matrix.

The insights generated allow stakeholders to immediately identify high-value brands that are losing market traction due to inventory issues and pinpoint exactly where stock renegotiations are needed.

## 🛠️ Tech Stack & Tools
* **Python** as the primary programming language.
* **Pandas** for data manipulation, cleaning, and string parsing (brand extraction from descriptions).
* **Matplotlib & Seaborn** for data visualization and building the strategic matrix.
* **Google Colab** as the cloud-based development environment.

## 📊 Methodology & Data Pipeline

### 1. Data Cleaning & Transformation
* **Type Conversion:** Formatted price data into numeric types and dropped missing or corrupted records.
* **Feature Engineering (Brand Extraction):** Processed unstructured text in the product description column using custom string-splitting logic to isolate and normalize brand names (`New Look`, `River Island`, `Miss Selfridge`, `Topshop`, etc.).
* **Statistical Filtering:** Excluded long-tail brands with fewer than 5 listed products to eliminate averages bias.

### 2. Stockout & Phantom Revenue Algorithm
Designed a custom data parsing function to evaluate per-product availability through the `size` array column:
* **Stockout Rate:** Calculated by dividing the number of out-of-stock variants by the total sizes offered per product.
* **Lost Revenue:** Computed by multiplying the product price by the specific out-of-stock count, exposing the direct financial leak for each item.

### 3. Brand Strategy Matrix (Visualization)
Generated a quadrant scatter plot mapping **Average Price** against **Stockout Rate**, utilizing marker sizes to represent cumulative lost revenue. 

The matrix applies critical thresholds (Price > $40 and Stockout Rate > 40%) to segment data into four actionable quadrants, instantly highlighting "critical underperformers" (expensive brands with high demand but poor stock fulfillment).

## 📈 Key Insights & Conclusions
* **Automated Priority Flagging:** The pipeline successfully isolates premium-tier brands exceeding a 40% stockout rate, allowing the procurement team to focus efforts where the financial risk is highest.
* **Financial Impact Quantification:** By translating stockouts into "Lost Revenue" metrics instead of just abstract percentages, the business can prioritize inventory reordering based on true monetary value at risk.

## 🚀 How to Run
1. Click the **Open in Colab** badge at the top of this file to view the notebook directly in your browser.
2. Ensure you upload the `products_asos.csv` dataset into the Colab runtime environment.
3. Execute the notebook cells sequentially to replicate the data engineering pipeline and visualizations.
