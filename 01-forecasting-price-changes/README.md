## Exercise 1: Forecasting Price Changes & Promotions

## Overview

This exercise examines how price changes and special event promotions impact the weekly sales of a popular jeans model for a U.S. fashion retailer. Using historical data and predictive analytics, the goal is to help the retailer plan effective pricing strategies to maximize revenue—especially during major sales events.

## Business Objective

To give the retailer actionable recommendations, the analysis answers:  
- **How do different price points and special event weeks impact jeans sales?**  
- **How would a new special promotion (“$25 Off” during an event week) likely affect sales?**

The retailer seeks to understand and predict the effect of both regular discount promotions and a newly proposed "$25 Off" special event on product sales. The analysis goes beyond retrospective evaluation of past promotions, using regression models to simulate business outcomes for future pricing scenarios.  

## Dataset

- **Source:** jeans_data_full_dataset.xlsx (weekly sales from a U.S. fashion retailer)
- **Main columns:**
  - `price`: Selling price for each week.
  - `sales`: Number of jeans sold per week.
  - `special_event`: Name of a major retail week (e.g., “Christmas”), or left blank otherwise.
  - `se_indicator`: 1 if special event week, 0 otherwise.

## Method & Analysis

### Model I: Using Price ($) and Special Event Indicator

- **Approach:**  
  A multiple linear regression model predicts weekly sales based on two factors:
    1. The jeans' selling price (in dollars).
    2. Whether the week features a special event (1) or not (0).  

- **Rationale:**  
  This allows us to see, for any given week, how lowering the price or running a special event changes demand. It's particularly useful for simulating a new scenario (for example, a “$25 Off” promotion during a special sale week).

- **Layman’s explanation:**  
  Think of it as a line that predicts sales:  
  - If price drops, sales usually rise—this model tells us *by how much*.
  - If it’s a special week (e.g., Christmas), we measure how much extra “lift” that brings on top of price effects.

- **Steps:**
  1. Ran a regression analysis with “price” and “special event indicator” as independent variables, and “sales” as the target.
  2. Interpreted coefficient meanings (e.g., sales decrease for every $1 increase in price).
  3. Predicted expected sales if the retailer drops the price by $25 during a special event.

### Model II: Using % Discount and Special Event Indicator

- **Approach:**  
  Instead of using price in dollars, we calculate the percentage discount off the original price ($135). The model then predicts sales based on:
    1. The % discount applied each week.
    2. Special event status.

- **Rationale:**  
  Using % discount helps the retailer plan promotions: “How much do sales jump if I increase my discount by 10% during Black Friday?”

- **Layman’s explanation:**  
  It’s like asking: if we give a bigger discount (e.g., 20% off instead of 10% off), *how many more pairs will sell*—and does this bonus get even bigger during a holiday?

- **Steps:**
  1. Created a “discount_percent” variable (e.g., 25% off, 15% off, etc.).
  2. Ran a regression with “discount_percent” and “special event” as inputs, “sales” as the target.
  3. Predicted expected sales for a new $25 off discount (translated into a percent) combined with a special event.

## Key Results

- **Model I (Price in $):**
  - *Every $1 decrease in price* leads to a clear, quantifiable increase in weekly sales (the regression coefficient directly shows the effect).
  - *Special event weeks* (like Christmas or Black Friday) cause a significant additional boost in sales, beyond the effect of price alone.
  - A simulated "$25 Off" promotion—especially during a special event—would result in a notable spike in sales compared to regular weeks and prices.

- **Model II (% Discount):**
  - *Increasing the percent discount* consistently drives up sales, with steeper discounts yielding bigger results—especially when combined with special events.
  - The regression clearly shows how much each extra % discount boosts demand.
  - For a "$25 Off" (roughly an 18.5% discount from $135), forecasts indicate higher sales than smaller discounts, with amplified effects in event weeks.

- **Summary Table (from the analysis):**
  | Scenario                  | Predicted Weekly Sales |
  |---------------------------|-----------------------|
  | Regular Price, Non-Event  | Lower                |
  | Regular Price, Event Week | Higher (due to event)|
  | "$25 Off", Non-Event      | Higher (due to price)|
  | "$25 Off", Event Week     | Highest              |

- Both models agree: price is a powerful lever; special events multiply its effect. Smart timing and discounting can unlock major sales gains.

## Business Impact & Interpretation

- Retailers can use these models to *predict how many jeans to stock and when to run promotions* for maximum return.
- Data-driven insights help avoid under- or over-discounting—striking a balance between high sales and profitability.
- The analysis provides *clear, actionable predictions* for planning future campaigns, leading to better inventory management and revenue optimization.

## How to Run / Reproduce

1. Open `BA875-Ex-1-Forecasting-Price-Changes-and-Promotions.ipynb`.
2. Ensure `jeans_data_full_dataset.xlsx` is in the same folder.
3. Run notebook cells to see original code, charts, and sales forecasts step-by-step.

### Requirements

- Python 3.x
- Libraries: pandas, numpy, matplotlib, seaborn, statsmodels

## Learning & Takeaways

- Proven real-world method for predicting retail sales using price, time, and event data.
- Practical experience in translating model results into business recommendations.
- Enhanced communication of technical findings for diverse stakeholders—ensuring actionable results for the company.

## Project Details

- **Completed:** March 2024
- **Course:** Operations and Supply Chain Analytics (BA875), Boston University MSBA

*This exercise demonstrates how business questions can be turned into data-driven plans—making analytics accessible and impactful for decision-makers.*
