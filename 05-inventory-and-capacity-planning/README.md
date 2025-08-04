## Exercise 5: Inventory & Capacity Planning Using Simulation

## Overview

This exercise explores simulation-based approaches to inventory and capacity optimization—core tools for managing risk and profit in hospitality and retail environments. By modeling uncertainty in customer behavior and product demand, these analyses help organizations set overbooking thresholds and order quantities that maximize profit while minimizing costly shortages or excess.

## Business Objective

To support smarter decision-making, this analysis answers:
- **How many rooms (or units) should a business overbook or pre-order to maximize profit while managing the risk of no-shows or unsold inventory?**
- **What does the tradeoff between profit and risk look like for different planning choices, and how should companies interpret and act on these tradeoffs?**

Organizations in both services and product industries must balance the risk of lost sales against the cost of over-committing resources. Simulation-based optimization empowers leaders to make informed, data-driven choices that align with real-world uncertainty, leading to more resilient and profitable operations.

## Methods & Analysis

### Part I: Overbooking Optimization for Hotels (Hyatt Problem)

**Scenario:**  
- Hyatt Atlanta can sell 100 room nights but faces no-shows; it can choose to overbook up to $$ Y $$ additional guests.
- No-shows are normally distributed (mean = 8, SD = 2).  
- Denied reservations incur penalties and compensation ($25 meal voucher for denied customer, $150 lost opportunity for empty room).
- Room rate is $150.

**Approach:**
- Simulate outcomes for 400,000 nights at each overbooking level (typically from 2 to 14 extra bookings).
- For each scenario:  
  - Calculate actual arrivals, overfilled/denied customers, and empty room costs.
  - Compute average and standard deviation of profit for each level.
- Identify the overbooking level that **maximizes average profit** while considering risk (profit variability).

**Outputs:**
- Table and plots for average profit, profit standard deviation, and the efficiency frontier (profit versus risk).
- **Recommendation:** The overbooking level offering the highest average profit, along with justification relating to both revenue and risk tradeoffs.

### Part II: Inventory Optimization for Seasonal Goods (The Parka Problem)

**Scenario:**  
- L.L. Bean must decide how many parkas to order before the winter season.
- Demand is normally distributed (mean = 26, SD = 3).
- Parka costs $70 to buy, sells at $140, and unsold items are marked down to $40.
- Unsold parkas after the selling season are discounted at a markdown price.

**Approach:**
- Simulate 400,000 seasons at each order level (from 17 to 35 parkas, mean ± 3SD).
- For each scenario:  
  - Calculate sales revenue, markdown revenue, procurement cost, and resulting profit.
  - Compute both the average and the standard deviation of profit.
- Identify order size that **maximizes expected profit**, and explain risk implications.

**Outputs:**
- Results table, profit and risk plots, and the efficiency frontier (average profit vs. risk).
- **Recommendation:** The order quantity that yields the highest expected profit, justified with reference to both statistical output and operational logic.

## Key Results

- **Hyatt overbooking:** The simulation identifies the optimal number of extra bookings to accept, balancing the gain from reducing empty rooms (no-shows) against the risk and cost of overfilling and denying guests. The recommended overbooking level is the one with the highest average profit, with diminishing returns and increased risk at very high levels.
- **L.L. Bean parkas:** There is a "sweet spot" in ordering—the optimal quantity buffers against demand uncertainty but avoids excessive markdown losses due to overstock. The results show how optimal order size shifts as sales and markdown dynamics interact.

- **Efficiency Frontier:** Both analyses present an "efficiency frontier"—the set of choices where you can't increase profit without also increasing risk, helping managers weigh risk tolerance against desired returns.

- For both parts: All findings are explained in straightforward business terms, making the results accessible and actionable for decision-makers.

## Business Impact & Interpretation

- **Revenue Maximization:** Companies can systematically choose overbooking/order levels that capture more sales that are missed due to customer “no-shows” or uncertain demand.
- **Risk Management:** By quantifying profit risk (standard deviation), managers see the likely variability in outcomes, which supports risk-aware, not just profit-maximizing, planning.
- **Competitive Edge:** The exercise empowers organizations to operate closer to full capacity, reduce lost revenue, and make smarter commitments in high-stakes environments.

## How to Run / Reproduce

1. Open `BA875-Ex-5-Inventory-Capacity-Planning.ipynb`.
2. Run the notebook sequentially to follow the analysis, see simulation results, and review visualizations.
3. All inputs and logic are clear and reproducible—parameters and assumptions are transparent and explained in code and markdown comments.

### Requirements

- Python 3.x  
- Libraries: pandas, numpy, matplotlib

## Learning & Takeaways

- Developed practical skills in profit and risk analysis under uncertainty using simulation.
- Learned how to automate scenario testing for inventory/capacity planning.
- Practiced written justification and visualization of optimal choices to support business communication and cross-functional understanding.

## Project Details

- **Completed:** April 2024  
- **Course:** Operations and Supply Chain Analytics (BA 875), Boston University MSBA

*By translating simulation results into clear recommendations, this exercise prepares future leaders to manage inventory and capacity proactively—balancing profitability with the realities of risk and customer behavior.*
