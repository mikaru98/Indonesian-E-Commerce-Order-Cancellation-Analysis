# Analysis of E-Commerce Order Cancellations in Indonesia 2023–2025

## Repository Outline

```text
1. description.md          - Documentation and description of this project
2. Data Analysis.ipynb     - Python notebook containing the complete data analysis
3. all_months_clean_2.csv  - Cleaned dataset ready to use
```

## Problem Background

E-commerce platforms in Indonesia face the challenge of a high order cancellation rate, which reached **13.57%** during the period from December 2023 to November 2025. This high cancellation rate directly impacts revenue loss, inefficient use of logistics resources, and declining trust from both sellers and buyers toward the platform.

This analysis aims to identify the main factors behind order cancellations, including cancellation reasons, payment methods, and shipping options, in order to provide appropriate recommendations to reduce the cancellation rate to **12.5% or lower within the next year**.

## Project Output

* **Python Notebook** — Complete descriptive and inferential statistical analysis with 4 data visualizations
* **Tableau Dashboard** — Interactive dashboard displaying data visualizations and statistical analysis results

## Data

| Description       | Details                                                                                                                                                  |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Source            | [Kaggle — Indonesia E-Commerce Sales and Shipping 2023–2025](https://www.kaggle.com/datasets/bakitacos/indonesia-e-commerce-sales-and-shipping-20232025) |
| Number of Rows    | 208,484 transactions                                                                                                                                     |
| Number of Columns | 18 columns                                                                                                                                               |
| Period            | December 2023 – November 2025                                                                                                                            |
| Missing Values    | 18,018 null values in the `Cancellation Reason` column, handled through imputation                                                                       |
| Data Types        | 9 numerical columns (`int64`) and 9 categorical columns (`object`)                                                                                       |

**Main columns analyzed:**

* `Order Status` — final order status, either Cancelled or Completed
* `Cancellation Reason` — cancellation reason provided by the buyer
* `Payment Method` — payment method used
* `Shipping Option` — shipping service selected
* `Estimated Shipping Cost` — estimated shipping fee
* `Order Created Time` — timestamp of when the order was created

## Method

### Data Cleaning

* Converted the `Order Created Time` column into datetime format
* Imputed null values in the `Cancellation Reason` column:

  * Orders with `Completed` status → filled with `"Not Cancelled"`
  * Orders with `Cancelled` status and no reason → filled with `"Unknown"`
* Dropped the irrelevant `source_file` column
* Saved the cleaned dataset as `all_months_clean_2.csv`

### Analysis

1. **Cancellation Reason Frequency** — Top 10 reasons for cancelled orders
2. **Cancellation Percentage by Payment Method** — Identifying payment methods with the highest cancellation rates
3. **Cancellation Percentage by Shipping Option** — Top 10 shipping options with the highest cancellation rates
4. **Monthly Cancellation Trend** — Cancellation patterns across 24 months, from December 2023 to November 2025
5. **Descriptive Statistics** — Distribution analysis of shipping costs for cancelled orders, including mean, median, mode, standard deviation, and skewness
6. **Inferential Statistics** — Mann-Whitney U Test to examine the difference in shipping costs between cancelled and completed orders

## Stacks

| Category             | Tools / Library         |
| -------------------- | ----------------------- |
| Programming Language | Python 3                |
| Data Manipulation    | `pandas`                |
| Visualization        | `matplotlib`, `seaborn` |
| Dashboard            | Tableau Public          |
| Environment          | Jupyter Notebook        |

## Reference

* Dataset: [Indonesia E-Commerce Sales and Shipping 2023–2025 — Kaggle](https://www.kaggle.com/datasets/bakitacos/indonesia-e-commerce-sales-and-shipping-20232025)
* Tableau Dashboard: [Tableau Dashboard](https://public.tableau.com/views/Book1_17726417772740/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

**Created by:** Michael Richard L
