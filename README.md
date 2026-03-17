# SuperStore
# SuperStore Customer & Sales Analysis

## Table of Contents
- [Project Background](#project-background)
- [Data Structure & ERD](#data-structure--erd)
- [Executive Summary](#executive-summary)
- [Insights Deep-Dive](#insights-deep-dive)
  - [Cohort Analysis](#cohort-analysis)
  - [RFM Analysis](#rfm-analysis)
  - [Store & Product Rank](#store--product-rank)
- [Recommendations](#recommendations)
- [Assumptions & Caveats](#assumptions--caveats)

---

## Project Background

SuperStore is a multi-location retailer chain operating across several physical stores in the US, offering a wide range consumer goods. Founded with a focus on accessible retail, the company serves a diverse customer base and competes primarily on product variety, store availability, and customer loyalty.

Despite having access to transactional data, SuperStore's management team had historically relied on isolated spreadsheets to track performance. This project represents an end-to-end analysis of SuperStore's order data from **2014 to 2017**, answering the core business questions: 
- **How quickly do new customers disengage?**
- **Which customers are most valuable, and which are at risk of churning?**
- **Which stores and products drive the most revenue?**

Insights and recommendations are provided across three key areas:

- **Cohort Analysis:** Evaluation of customer retention patterns over time, grouped by the month of first purchase.
- **RFM Analysis:** Segmentation of customers by Recency, Frequency, and Monetary value to identify Champions, Loyal Customers, At-Risk groups, and Lost customers.
- **Store & Product Rank:** Assessment of which store locations and product categories drive the most revenue and order volume.

The Excel workbook containing all analyses and visualizations can be downloaded **[here](#)** *(replace with your file link)*.

---

## Data Structure & ERD

SuperStore's database consists of four tables with a total of approximately **10.000 records** spanning 2014–2017.

| Table | Description |
|---|---|
| `orders.csv` | All purchase orders placed across store locations within the analysis period |
| `customers.csv` | Customer profiles across all stores in the network |
| `products.csv` | Attributes of products sold across stores (category, name, price) |
| `location.csv` | Store location data where purchases were made |

![SuperStore ERD](images/superstore_erd.png)

---

## Executive Summary

Between 2014 and 2017, SuperStore processed approximately **10.000 orders** across its store network. The RFM segmentation revealed that SuperStore has great growth potential with 40% of their customers being classified as Potential Loyalist. Cohort retention data shows that first-month drop-off is steep across all acquisition cohorts, with only a fraction of customers returning. On the product side, **Technology products** consistently leads in both revenue and profit, while the **Furniture** category has a very low profit margin.

```
![Executive Summary Dashboard](images/exec_summary.png)
```

---

## Insights Deep-Dive

### Cohort Analysis

- **Retention drops sharply after the first month.** Across all acquisition cohorts from 2014–2017, average Month 1 retention sits at approximately **6%**. This pattern is consistent regardless of the cohort's acquisition period. Revealing that the store is not leveraging seasonal purchases mainly in December during the holiday season.
- A closer look to the Cohort data also reveals that SuperStore has not been able to consistenly acquire new clients resulting in over 90% of the sales of 2017 being made by recurring clients.  

![Cohort Retention Heatmap](images/cohort_heatmap_2014.png)

![Cohort Retention Heatmap](images/cohort_recurring.png)

---

### RFM Analysis

RFM scores were calculated by ranking each customer on three dimensions: **Recency** (days since last purchase), **Frequency** (total number of orders), and **Monetary Value** (total spend). Customers were then grouped into segments based on combined score thresholds. The reference used to determine the segments can be found here: https://www.putler.com/rfm-analysis/.

| Customer Segment | Description | Actionable Tip |
|---|---|---|
| **Champions** | Bought recently, buy often, and spend the most | Reward them. Great candidates for early product launches and brand promotion |
| **Loyal Customers** | Spend consistently and respond well to promotions | Upsell higher-value products. Ask for reviews. Keep them engaged |
| **Potential Loyalists** | Recent customers who bought more than once and spent a decent amount | Offer a loyalty program or membership. Recommend complementary products |
| **Recent Customers** | Bought most recently but not frequently | Provide onboarding support and start building the relationship early |
| **Promising** | Recent shoppers who haven't spent much yet | Build brand awareness and offer free trials or introductory deals |
| **Needing Attention** | Above-average R, F, and M values but haven't purchased very recently | Use limited-time offers. Reactivate with recommendations based on past purchases |
| **About To Sleep** | Below-average recency, frequency, and monetary values — at risk of going cold | Share valuable content, recommend popular products, and reconnect with discounts |
| **At Risk** | Spent big and bought often, but haven't returned in a long time | Send personalized re-engagement emails. Offer renewals and helpful resources |
| **Can't Lose Them** | Made the largest purchases frequently, but haven't returned in a long time | Win back with renewals or new products. Don't let them go to competitors |
| **Hibernating** | Last purchase was long ago, low spend, and low order count | Offer relevant products and special discounts. Recreate brand value |
| **Lost** | Lowest scores across recency, frequency, and monetary value | Attempt a reach-out campaign. If no response, deprioritize to save resources |

Key findings:

- **Loyal Customers account for approximately 47% of total revenue** despite representing only 27% of the customer base. This segment is the primary revenue engine and warrant proactive retention efforts.
- **Potential Loyalist segment contains 40% of all customers**, this represents a great opportunity for the store to increase their revenue if they are able to turn them into loyal customers.
- **8% of customers fall into the Can't Lose Them segment**, being the third revenue stream representing over 10%. 
- **Recent customers represent only 2% of all customers** - there is clar potential to increase the number of new customers.


![RFM Segmentation Chart](images/rfm_segments.png)

![RFM Segmentation Chart](images/rfm_segments_revenue.png)

---

### Store & Product Rank

- **Store [X] leads in total revenue**, generating **$[X]** over the analysis period — approximately **[X%] above** the network average. This store also has the highest average order value (AOV) at **$[X]**.
- **Store [X] underperforms significantly in both order count and revenue**, despite being located in a [comparable / higher-traffic] area. This suggests possible operational or assortment issues worth investigating.
- **[Top Product Category]** is the highest-grossing category, contributing **[X%] of total revenue**. Within this category, **[Top Product]** alone accounts for **[X%]** of category sales.
- **[Lowest Category]** generates the fewest orders and lowest revenue per order, raising questions about shelf space allocation and whether the category is aligned with local customer demand.
- Among the top 10 products by revenue, **[X] products appear in the top-performing stores' order data consistently**, suggesting a correlation between store performance and product mix rather than foot traffic alone.

*(Insert store rank table and product revenue bar chart here)*

```
![Store & Product Rank](images/store_product_rank.png)
```

---

## Recommendations

### Customer Retention (Marketing & CRM Team)
- **Launch a targeted re-engagement campaign for the At-Risk segment.** Given their historical spend, even recovering [X%] of this group could represent $[X] in recaptured revenue. Personalized discount offers or "we miss you" messaging tied to their most purchased category are the recommended starting point.
- **Invest in converting Potential Loyalists.** This segment already exhibits positive purchase behavior. A loyalty incentive — such as a points multiplier or a threshold discount on their next order — could accelerate their progression to the Loyal Customer tier.
- **Protect Champions with exclusive benefits.** This group is small but disproportionately valuable. Early access to new products, a VIP tier, or dedicated service touchpoints can reduce the risk of losing them to competitors.

### Store Operations (Regional Management Team)
- **Investigate the underperforming stores** identified in the Store Rank analysis. A qualitative review of their product assortment, staffing, and local demographics relative to top-performing locations may reveal correctable gaps.
- **Replicate the product mix of top-performing stores** where feasible. The correlation between high-revenue stores and specific product categories suggests that assortment strategy, not just location, is driving performance differences.

### Product & Merchandising (Category Management Team)
- **Review the lowest-performing product categories** for potential reallocation of shelf space. If a category consistently underperforms across multiple stores, demand may not justify its current footprint.
- **Double down on the top product category** by ensuring consistent availability and exploring adjacent upsell opportunities (e.g., bundling frequently co-purchased items).

---

## Assumptions & Caveats

- **Cohort assignment is based on first order date.** Customers are assigned to the cohort of their earliest recorded purchase. If historical data is incomplete (e.g., purchases prior to 2014 exist but are not captured), some customers may be misclassified as new when they are in fact returning.
- **RFM thresholds are relative, not absolute.** Segment boundaries were defined using quantile-based scoring within this dataset. Scores are not comparable to external benchmarks or other datasets.
- **"Monetary" in RFM reflects total revenue, not profit.** Gross margin data was not available; high-spend customers may not necessarily be the most profitable if they purchase lower-margin products.
- **Location data assumed to be accurate.** No geographic validation was performed on the `location.csv` file. Store-level analysis assumes each order is correctly attributed to its store of origin.
- **The dataset ends in 2017.** Any trends observed — particularly in cohort retention or store performance — may not reflect current business conditions. This analysis is intended as a historical diagnostic, not a real-time operational tool.
- **Duplicate records, if any, were removed prior to analysis.** *(Update this note based on what you actually found during data cleaning.)*
