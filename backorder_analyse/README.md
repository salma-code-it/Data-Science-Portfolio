# Backorder Prediction System

## 🔗 Dataset
This project uses the **Backorder Prediction Dataset** from Kaggle.  
You can access the dataset here:  
[Kaggle - Backorder Prediction Dataset](https://www.kaggle.com/datasets/ztrimus/backorder-dataset)

> **📁 Setup Instructions:**  
> After downloading the `.zip` file, extract and copy the **two CSV files** into the `raw_csv/`.
---

## 🧩 The Problem

At your company, you face a common and costly challenge: **product backorders**.

A backorder occurs when a customer orders a product that is temporarily out of stock. This leads to:

- **Lost Revenue** – missed sales opportunities.
- **Unhappy Customers** – delayed deliveries harm customer trust.
- **Increased Costs** – expedited shipping and overtime expenses.
- **Wasted Resources** – your team spends time managing exceptions instead of planning.
- **Inefficient Inventory** – holding excess stock for slow movers while running out of fast sellers.

**In short, being unprepared for demand spikes or supplier delays hurts your bottom line and your brand reputation.**

---

## The Solution: Predictive System

We developed a **machine learning system** that predicts which products are likely to go on backorder before it happens.

It analyzes historical data to detect risk patterns and gives you a **risk score** for every product.

### How It Works:

1. **Data Analysis** –  
   We examined **1.6 million product records** and **23 features**, including:
   - Current inventory levels (`national_inv`)
   - Supplier lead times (`lead_time`)
   - Historical sales (`sales_1_month`, `sales_9_month`)
   - Demand forecasts (`forecast_3_month`, `forecast_9_month`)
   - Supplier performance (`perf_6_month_avg`, `perf_12_month_avg`)
   - And more...

2. **Feature Engineering** –  
   We created powerful new indicators like:
   - `supply_gap_3m` – supply vs. forecast demand
   - `inventory_coverage_months` – how long inventory will last
   - `below_min_bank` – whether inventory is below the safety stock

3. **Model Training** –  
   We used a **Random Forest** model, which gave the best balance of accuracy and reliability, achieving:
   - **95% ROC-AUC**
   - **77% recall** – catching most real backorders
   - **0.16 F1-score** – balancing precision and recall (due to severe data imbalance)

---

## Risk-Based Reporting

Instead of simple Yes/No predictions, we provide a **risk score and action plan**:

| Risk Level      | Probability (%) | Recommended Action                              |
|----------------|----------------|-------------------------------------------------|
| Very Low       | 0 – 10         | No action needed                                |
| Low            | 10 – 30        | Standard monitoring                             |
| Medium         | 30 – 50        | Review inventory levels                         |
| High           | 50 – 70        | Contact supplier, check lead times              |
| Very High      | 70 – 85        | Expedite replenishment order                    |
| Critical       | 85 – 100       | **IMMEDIATE ACTION – Risk of stockout!**    |

> *This report allows your team to prioritize and act proactively.*

---

## Key Benefits

### For Your Team:
- ✅ **Proactive replenishment** – order before stock runs out.
- ✅ **Optimized inventory** – reduce overstock and stockouts.
- ✅ **Lower costs** – fewer emergency orders and expedited shipping.
- ✅ **Data-driven decisions** – focus on high-risk items first.

### For Your Customers:
- ✅ **Faster delivery** – products are in stock when needed.
- ✅ **Reliable service** – become a more dependable partner.

---

## Next Steps

This system can be integrated into your existing workflow.  
Supply chain planners can use the reports to:

- Identify at-risk products early
- Prioritize replenishment orders
- Monitor supplier performance trends
- Improve service levels and reduce costs

> *Proactive planning leads to better customer satisfaction and healthier margins.*