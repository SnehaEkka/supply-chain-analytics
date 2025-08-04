## Exercise 3: Pricing Analysis

## Overview

This exercise puts pricing strategies under the microscope, leveraging real-world data to optimize revenue and profit across multiple business scenarios. Using regression, profit maximization, and segmentation analysis, the work demonstrates how data-driven pricing decisions can create value—from adjusting prices by day of week, to matching new and refurbished product offers, to strategic customer segmentation.

## Business Objective

To answer critical pricing questions and equip managers with actionable recommendations, this analysis explores:
- **How should prices be set for products and services to maximize profitability across different customer segments and market conditions?**
- **What’s the business impact of nuanced pricing strategies versus one-size-fits-all approaches?**

Businesses constantly need to balance demand, cost, and consumer willingness to pay. This exercise provides a transparent, data-informed approach to price optimization—empowering organizations to make more informed, profitable, and customer-aligned pricing decisions.

## Datasets

- **demand_data_full.xlsx:** Simulated demand for a product across various price points, with indicators for weekend versus weekday purchases (egg sales example).
- **refurb_data:** (Described in notebook) Purchase choices and price points for new vs. refurbished products in a technology retail context.

## Methods & Analysis

### Part I: Optimal Pricing by Weekday vs. Weekend

- **Objective:** Identify how prices should differ between weekdays and weekends to maximize profit, accounting for shifting demand patterns.
- **Approach:**
  - Used a linear regression model to estimate the price-response curve: demand as a function of price and a weekend indicator.
  - Optimized price separately for weekdays and weekends given a fixed cost structure.
  - Calculated profit-maximizing prices for both cases and interpreted their credibility and business implications in plain language.
- **Result:** Provides clear recommendations for when, how much, and why to adjust prices for different days of the week.

### Part II: Pricing for New vs. Refurbished Products

- **Objective:** Determine the best refurbished product price to offer, depending on the price of a new product, and maximize profit from both options.
- **Approach:**
  - Counted daily choices for the refurbished product to estimate demand at each price point.
  - Modeled demand using regression on both refurbished and new product prices.
  - For each new price scenario ($300, $350, $400), determined the optimal refurbished price and the resulting profit.
  - Compared optimal prices and profits across new product price levels and interpreted differences.
- **Result:** Shows how refurbished pricing needs to adjust as new product prices change, helping businesses compete and maximize secondary product channel profits.

### Part III: Two-Segment vs. Single-Price Strategy

- **Objective:** Evaluate whether segmenting customers and setting two distinct prices delivers higher profit than offering a uniform price.
- **Approach:**
  - Used a known price-response curve and modeled profit under both a single-price and a two-segment (split by willingness-to-pay) scenario.
  - Calculated and compared optimal prices and total profit for both approaches.
  - Provided an explicit business conclusion on when, and why, segmentation boosts profitability.
- **Result:** Highlights the profit advantage of sophisticated segmentation strategies.

## Key Results

- **Dynamic pricing**—adapting prices for weekends vs. weekdays—unlocks higher profit by matching true demand patterns.
- **Refurbished pricing** should be tied closely to new product pricing. As new prices rise, the optimal refurbished price and profit potential also shift, requiring constant benchmarking.
- **Customer segmentation**—even with simple rules—can deliver materially higher profits compared to flat pricing by capturing more value from customers with higher willingness to pay.
- All findings are stated in actionable terms with direct recommendations suitable for both technical and non-technical stakeholders.

## Business Impact & Interpretation

- The analysis offers a playbook for companies to make smarter, more competitive, and more profitable pricing decisions—regardless of industry.
- By quantifying opportunities for differentiation, the work empowers managers to target promotions, design better product mixes, and communicate value effectively to diverse customer segments.

## How to Run / Reproduce

1. Open `BA875-Ex-3-Pricing-Analysis.ipynb`.
2. Ensure `demand_data_full.xlsx` (and any other referenced files) are present.
3. Run notebook cells in sequence to review data exploration, modeling, optimization, and business interpretation.

### Requirements

- Python 3.x
- Libraries: pandas, numpy, statsmodels, scipy

## Learning & Takeaways

- Built proficiency in regression-based demand estimation, price optimization, and segmentation.
- Gained perspective on translating analytical output into practical business recommendations for pricing and product strategy.
- Practiced communicating findings for cross-functional audiences—enabling direct impact on profitability and strategy.

## Project Details

- **Completed:** April 2024
- **Course:** Operations and Supply Chain Analytics (BA 875), Boston University MSBA

*By blending analytics, optimization, and market knowledge, this exercise demonstrates the power of data-driven pricing to drive better business outcomes for modern organizations.*
