# Class Project

## Project Overview

This project provides a comprehensive data analysis of **[briefly describe the dataset, e.g., sales orders/ecommerce data]** to evaluate financial performance and logistical efficiency across various product categories and geographic regions. The analysis focuses on identifying key drivers of high/low profit margins and pinpointing areas for operational improvement.

## Key Findings & Recommendations

### Financial Performance (Profit Margin Drivers)

* **Top Categories:** Electronics, Home, and Sports are the top categories based on total profit margin.
* **Problem Category:** Grocery is the only category exhibiting a negative profit margin and requires urgent review.
* **Shipping Cost Analysis:** A statistical test confirmed a significant difference ($p < 0.05$) in average shipping cost between low-margin ($\leq 10\%$ of Total Amount) and high-margin orders.
    * **Cost Drivers:** For low-margin orders, high shipping cost is primarily predicted by order `Quantity` ($\beta \approx 0.70$) and `Price`. `Region` and `Delivery Time` are not statistically significant cost factors.
    * **Recommendation:** Negotiate new carrier contracts focusing on **volume-based discounts**. The current flat-rate structure should be optimized to reduce the impact of high-quantity orders through better packaging consolidation.
* **Regional Impact:** Geographic region has a low overall impact on revenue and financial key performance indicators (KPIs).

### Logistical Efficiency (Delivery)

* **Efficiency Failure:** The correlation between shipping cost and delivery time is near-zero ($r \approx 0.008$). This indicates a fundamental failure: the company is **not paying for faster service**, necessitating an urgent carrier performance audit.
* **Delivery Inconsistency:** The Central and West regions show the highest variability ($\sigma$) in delivery times, signaling the greatest risk of poor customer experience in these areas. Targeted logistical overhaul is required for these regions.

## 💻 Programming Logic

The analysis was performed using Python and the Pandas library, including the following steps:

1.  **Data Preparation:** Calculated `order_cost` (Price $\times$ Quantity + Cost) and `revenue` (Price $\times$ Quantity - (1 - Discount)) columns.
2.  **Category Grouping:** Grouped data by `category` to calculate total `profit_margin`, `revenue`, and `total_costs`.
3.  **Regional Grouping:** Grouped data by `region` to analyze performance across locations.
4.  **Statistical Testing:** Used a statistical test (T-test) to compare the mean shipping cost of low-margin orders ($5.20) against high-margin orders ($6.68). The resulting P-value ($0.0000$) indicated a statistically significant difference.
5.  **Visualization:** Plotted key financial metrics and delivery data using bar charts for visual analysis.

## Files

* `Analysis.ipynb`: The main Jupyter Notebook containing the complete data cleaning, analysis, visualizations, and conclusions.
* `README.md`: This file.

## Setup and Dependencies

To run this project locally, you will need:

* Python (3.x recommended)
* Jupyter Notebook or JupyterLab
* Standard data science libraries (e.g., Pandas, NumPy, Matplotlib, SciPy)
