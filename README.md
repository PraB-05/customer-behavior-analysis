# 🛍️ Customer Shopping Behavior Analysis

> End-to-end analysis of 3,900 retail customer purchases using **Python, PostgreSQL and Power BI** to uncover spending patterns, customer segments, product preferences and subscription behavior.

---

## 📌 Table of Contents
1. [Project Overview](#-project-overview)
2. [Business Questions](#-business-questions)
3. [Dataset](#-dataset)
4. [Tech Stack](#-tech-stack)
5. [Workflow](#-workflow)
6. [SQL Analysis & Results](#-sql-analysis--results)
7. [Power BI Dashboard](#-power-bi-dashboard)
8. [Key Insights](#-key-insights)
9. [Business Recommendations](#-business-recommendations)
10. [Author](#-author)

---

## 📖 Project Overview

A retail business wants to understand **who its customers are, what they buy, and what drives their spending**. This project cleans and engineers features from the raw dataset in Python, loads it into PostgreSQL to answer 10 business questions with SQL, and presents the findings in an interactive Power BI dashboard.

## ❓ Business Questions

- Which gender and age groups contribute the most revenue?
- Do subscribers spend more than non-subscribers?
- Which products are top-rated, most purchased, and most discount-dependent?
- Does shipping type affect purchase value?
- How are customers distributed across New / Returning / Loyal segments?
- Are repeat buyers more likely to subscribe?

## 🗂️ Dataset

| Property | Detail |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Missing values | 37 in `Review Rating` |

**Feature groups**
- **Demographics:** Customer ID, Age, Gender, Location, Subscription Status
- **Purchase details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
- **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method

## 🧰 Tech Stack

| Layer | Tools |
|---|---|
| Data cleaning & feature engineering | Python, pandas |
| Database & analysis | PostgreSQL (SQL) |
| Visualization | Power BI |

## 🔄 Workflow

1. **Data loading** – imported the dataset with pandas.
2. **Initial exploration** – `df.info()` and `.describe()` to check structure and summary statistics.
3. **Missing data handling** – imputed `Review Rating` nulls with the **median rating of each product category**.
4. **Column standardization** – renamed all columns to `snake_case`.
5. **Feature engineering**
   - `age_group` – binned customer ages into groups.
   - `purchase_frequency_days` – converted purchase frequency text into number of days.
6. **Consistency check** – found `discount_applied` and `promo_code_used` to be redundant and dropped `promo_code_used`.
7. **Database integration** – loaded the cleaned DataFrame into PostgreSQL.
8. **SQL analysis** – answered 10 business questions.
9. **Dashboard** – built an interactive Power BI report.

## 🧮 SQL Analysis & Results

| # | Analysis | Result |
|---|---|---|
| 1 | Revenue by gender | Male **$157,890** vs Female **$75,191** |
| 2 | High-spending discount users | **839** customers used a discount yet spent above the average purchase amount |
| 3 | Top 5 products by rating | Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78) |
| 4 | Shipping type comparison | Express **$60.48** vs Standard **$58.46** average purchase |
| 5 | Subscribers vs non-subscribers | 1,053 subscribers: avg **$59.49**, revenue $62,645 · 2,847 non-subscribers: avg **$59.87**, revenue $170,436 |
| 6 | Discount-dependent products | Hat (50.00%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%) |
| 7 | Customer segmentation | Loyal **3,116** · Returning **701** · New **83** |
| 8 | Top 3 products per category | Accessories: Jewelry, Sunglasses, Belt · Clothing: Blouse, Pants, Shirt · Footwear: Sandals, Shoes, Sneakers · Outerwear: Jacket, Coat, … |
| 9 | Repeat buyers (>5 purchases) & subscription | Non-subscribers: 2,518 · Subscribers: 958 |
| 10 | Revenue by age group | Young Adult $62,143 · Middle-aged $59,197 · Adult $55,978 · Senior $55,763 |

## 📊 Power BI Dashboard

An interactive **Customer Behavior Dashboard** with slicers for subscription status, gender, category and shipping type.

**KPIs:** 3.9K customers · $59.76 average purchase amount · 3.75 average review rating

**Visuals:** subscription split (27% Yes / 73% No), revenue and sales by category, revenue and sales by age group.

<!-- Add your dashboard screenshot below -->
<!-- ![Dashboard](images/dashboard.png) -->

## 💡 Key Insights

- **Revenue is driven by volume, not spend per customer.** Males account for ~68% of customers and ~68% of revenue; average spend per customer is nearly identical (~$59.5 male vs ~$60.3 female).
- **Subscribers don't spend more.** Average spend is ~$59.49 for subscribers vs ~$59.87 for non-subscribers; only 27% of customers subscribe, which is the real opportunity.
- **Clothing is the largest revenue category**, followed by Accessories, Footwear and Outerwear.
- **Young Adults are the top revenue age group**, but the gap between age groups is small (~11% between highest and lowest).
- **~43% of purchases use a discount**; the most discount-dependent products sit at 47–50%.
- **~80% of customers fall in the "Loyal" segment**, suggesting a highly engaged base (or a segment threshold that is too generous).
- **Express shipping users spend slightly more** ($60.48 vs $58.46).

## ✅ Business Recommendations

- **Boost subscriptions** – promote exclusive subscriber benefits to grow the 27% base.
- **Loyalty programs** – reward repeat buyers and retain the Loyal segment.
- **Review discount policy** – balance sales uplift against margin, especially on highly discounted products.
- **Product positioning** – feature top-rated and best-selling products in campaigns.
- **Targeted marketing** – focus on high-revenue age groups and express-shipping users.

<img width="500" height="303" alt="image" src="https://github.com/user-attachments/assets/5afe9aa1-e028-4cde-ac59-222bf1b8086e" />

## 👤 Author

**PraB-05** · [GitHub](https://github.com/PraB-05)

---
⭐ If you found this project useful, consider giving it a star!
