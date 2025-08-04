## Exercise 4: Demand Unconstraining for Products and Services

## Overview

This exercise demonstrates demand unconstraining methods—essential analytics for businesses with limited inventory or capacity. By reconstructing true (and often hidden) demand from observed, potentially censored sales or booking data, the analysis enables managers to avoid underestimating true market potential, thereby improving fulfillment, forecasting, and revenue optimization for both physical products and service bookings.

## Business Objective

To guide better operations and revenue planning, this analysis answers:
- **How do we estimate true customer demand when inventory, capacity, or sales policies prevent us from observing all sales/booking requests (i.e., demand censoring)?**
- **What methods best reconstruct hidden demand, and how should they be used for data-driven decision-making across products and services?**

Organizations risk leaving money on the table if they fail to account for lost or censored demand. By applying quantitative unconstraining methods, businesses can reveal their real market size, align inventory or capacity decisions more closely to customer needs, and optimize their future operations.

## Datasets

- **grocery_data.xlsx:** Hourly sales data of a perishable product (Pain de Boulogne) with observed daily censored sales once inventory ran out, further demand was not directly captured.

## Methods & Analysis

### Part I: Physical Products with Limited Inventory

**Goal:** Estimate true total daily demand for bread sales when inventory limits result in censored/underreported sales.

- **Double Exponential Smoothing (DES):**
  - Applied DES to each day's observed cumulative hourly sales curve, using burn-in for early hours.
  - Tested multiple (alpha, beta) pairs to minimize smoothing error and completed the censored curves by forecast, yielding estimated final sales for each day as if inventory had been unlimited.

- **Averaging Method:**
  - Reconstructed unconstrained arrival rates by averaging observed hourly sales across non-censored days.
  - Used these “average hour” benchmarks to fill in censored hours for partially completed sales days, projecting what sales would have been without a stockout.

- **Result:** Both methods appended new columns estimating unconstrained (full potential) demand for each day, in addition to the raw observed totals.

### Part II: Service Products with Limited Capacity

**Goal:** Unconstrain hotel booking demand (for Hyatt Atlanta Downtown) where limited room inventory means bookings above a certain threshold are not directly observed.

- **Proportional Method:**
  - Reformatted booking data to identify where censoring occurred.
  - Calculated ratio of actual observed bookings-to-total cumulative demand up until censoring, using these ratios to project the true total bookings that would have occurred in the absence of room constraints.
  - Updated the dataset with unconstrained booking estimates for all booking curves.

## Key Results

- **DES and Averaging Methods (Products):**
  - Both approaches provide a defensible estimate of what true sales would have been each day if there were unlimited inventory. The DES method traces demand curves based on smoothed trends, while the Averaging method leverages peer day patterns.
  - **Interpretation:** These numbers reveal real customer interest, supporting better forecasting, ordering, and supply allocation—so businesses stop understocking and missing sales when demand is strong.

- **Proportional Method (Services):**
  - Estimates bookings lost due to room constraints, allowing the hotel to more realistically forecast demand, set prices, and plan for future busy dates.
  - **Interpretation:** The results show “hidden” demand—potential bookings missed due to capacity limits. Accurately estimating these helps optimize both pricing and resource allocation.

- **Why do methods differ?** Each method makes different assumptions about customer behavior after censoring (smooth continuation, average pattern, or proportional projection). Variation in approach yields slightly different demand estimates, but all are superior to using raw, censored data alone.

## Business Impact & Interpretation

- **True Demand Visibility:** These methods reveal what businesses cannot see in their raw sales records, enabling more confident and profitable operations, purchasing, and marketing.
- **Preventing Under-ordering:** By accounting for censored demand, businesses can stock, staff, or allocate capacity more in line with actual market needs, protecting reputation and revenue.
- **Revenue Optimization:** Accurate unconstraining is a cornerstone of modern retail and service analytics, unlocking better pricing, forecasting, and growth strategies.

## How to Run / Reproduce

1. Open `BA875-Ex-4-Demand-Unconstraining.ipynb`.
2. Ensure `grocery_data.xlsx` and any relevant booking datasets are present.
3. Run notebook cells in order for a walkthrough, including data prep, method comparison, calculation of unconstrained estimates, and interpretation.

### Requirements

- Python 3.x  
- Libraries: pandas, numpy, statsmodels (for smoothing)

## Learning & Takeaways

- Mastered unconstraining algorithms for both products and services with limited capacity or inventory.
- Learned how to compare, interpret, and explain analytical differences between unconstraining techniques.
- Developed cross-industry skills directly applicable to real-world supply chain, revenue management, and inventory planning settings.

## Project Details

- **Completed:** April 2024
- **Course:** Operations and Supply Chain Analytics (BA 875), Boston University MSBA

*By converting censored sales and bookings into actionable, unconstrained demand insights, this exercise empowers organizations to serve customer needs more fully and unlock untapped business growth.*
