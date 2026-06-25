# Indonesian E-Commerce Order Cancellation Analysis 2023–2025

## Repository Outline

```
1. description.md         - Documentation and description of this project
2. Data Analysis.ipynb  - Python notebook containing the complete data analysis
3. all_months_clean_2.csv    - Cleaned dataset (ready to use)

```

## Problem Background

Indonesian e-commerce platforms face a challenge with a high order cancellation rate of **13.57%** during the period December 2023 – November 2025. This high cancellation rate directly impacts revenue loss, wasted logistics resources, and declining trust from both sellers and buyers on the platform.

This analysis aims to identify the key factors driving order cancellations — ranging from cancellation reasons, payment methods, to shipping options — in order to provide actionable recommendations to reduce the cancellation rate to **12.5% or lower within the next 1 year**.

## Project Output

- **Python Notebook** — Complete descriptive & inferential statistical analysis with 4 data visualizations
- **Tableau Dashboard** — Interactive dashboard displaying data visualizations and statistical analysis results

## Data

| Description | Detail |
|---|---|
| Source | [Kaggle — Indonesia E-Commerce Sales and Shipping 2023–2025](https://www.kaggle.com/datasets/bakitacos/indonesia-e-commerce-sales-and-shipping-20232025) |
| Number of Rows | 208,484 transactions |
| Number of Columns | 18 columns |
| Period | December 2023 – November 2025 |
| Missing Values | 18,018 null values in the `Cancellation Reason` column (handled via imputation) |
| Data Types | 9 numeric columns (int64), 9 categorical columns (object) |

**Key columns analyzed:**
- `Order Status` — final status of the order (Cancelled / Completed)
- `Cancellation Reason` — cancellation reason filled in by the buyer
- `Payment Method` — payment method used
- `Shipping Option` — shipping service selected
- `Estimated Shipping Cost` — estimated shipping fee
- `Order Created Time` — timestamp of order creation

## Method

### Data Cleaning
- Convert the `Order Created Time` column to datetime format
- Impute null values in `Cancellation Reason`:
  - Orders with status `Completed` → filled with `"Not Cancelled"`
  - Orders with status `Cancelled` without a reason → filled with `"Unknown"`
- Drop the irrelevant `source_file` column
- Output saved to `all_months_clean_2.csv`

### Analysis
1. **Cancellation Reason Frequency** — Top 10 reasons orders were cancelled
2. **Cancellation Rate by Payment Method** — Identify payment methods with the highest cancellation rates
3. **Cancellation Rate by Shipping Option** — Top 10 shipping options with the highest cancellation rates
4. **Monthly Cancellation Trend** — Cancellation patterns over 24 months (Dec 2023 – Nov 2025)
5. **Descriptive Statistics** — Distribution analysis of shipping costs for cancelled orders (mean, median, mode, std, skewness)
6. **Inferential Statistics** — Mann-Whitney U Test to examine differences in shipping costs between cancelled and completed orders

## Stacks

| Category | Tools / Library |
|---|---|
| Programming Language | Python 3 |
| Data Manipulation | `pandas` |
| Visualization | `matplotlib`, `seaborn` |
| Dashboard | Tableau Public |
| Environment | Jupyter Notebook |

## Reference

- Dataset: [Indonesia E-Commerce Sales and Shipping 2023–2025 — Kaggle](https://www.kaggle.com/datasets/bakitacos/indonesia-e-commerce-sales-and-shipping-20232025)
- Tableau Dashboard: [Tableau Dashboard](https://public.tableau.com/views/Book1_17726417772740/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

**Created by:** Michael Richard L 
