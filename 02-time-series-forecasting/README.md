## Exercise 2: Time Series Forecasting in Supply Chain Analytics

## Overview

This exercise applies **time series forecasting techniques** to real-world retail and financial datasets. The primary focus is on developing, comparing, and interpreting forecasting models for both stationary and non-stationary data, equipping business analysts to anticipate demand, understand trends, and improve supply chain planning. 

## Business Objective

To help decision-makers plan more effectively, this exercise answers:
- **How can we best forecast and plan for different types of supply chain and financial time series data—whether stable, trending, or highly seasonal?**
- **What methods provide the most accurate and business-ready predictions for operational and strategic planning?**

Businesses need to navigate uncertain and varied demand patterns—some predictable, some erratic, some driven by trends or seasonality. This analysis equips analysts and managers with practical, actionable forecasting tools—comparing classic and modern methods—so organizations can make more informed decisions about inventory, capacity, and financial risk across retail, airlines, and digital assets. By translating data into clear forecasts, the exercise bridges the gap between analytical rigor and everyday business needs.

## Datasets

1. **Jeans Sales (Stationary Residual Series)**
   - **Source:** `jeans_data_full_dataset.xlsx`
   - **Variable:** Week-to-week sales residuals from a regression controlling for price and special events.

2. **Bitcoin Closing Price (Non-Stationary with Trend)**
   - **Source:** `bitcoin_data.xlsx`
   - **Variables:** Daily closing price of bitcoin from March 2023–March 2024.

3. **Airline Load Factor (Seasonal Series)**
   - **Source:** `airline_data.xlsx`
   - **Variables:** Monthly load factors (utilization) for Virgin Airlines, 2003–2013.

## Methods & Analysis

### Part I: Forecasting Stationary Series (Jeans Sales Residuals)

- **Objective:** Forecast unexplained week-to-week variation ("residuals") in jeans sales, providing inventory managers a sense of regular demand 'noise' after accounting for known factors.
- **Approaches:**
  - **Moving Average (MA) Method:** Calculated forecasts using window sizes (N) from 1–5 on residuals, starting at week 6.
  - **Single Exponential Smoothing (ES):** Applied smoothing with alpha (weight) between 0.1 and 1.0 (step 0.1), using a burn-in of 5 weeks.
- **Process:**
  - Computed and compared Mean Squared Error (MSE) for all MA and ES parameter settings.
  - Identified the optimal MA window and ES alpha by minimum error.
  - Plotted true residuals against both optimal forecasts for direct comparison.

### Part II: Forecasting Non-Stationary Series with Trend (Bitcoin Prices)

- **Objective:** Predict future closing prices of bitcoin—a financial time series known for strong trends and volatility.
- **Approach:**
  - **Trend Detection:** Used the Augmented Dickey-Fuller (ADF) test to confirm non-stationarity.
  - **Double Exponential Smoothing (DES):** Ran DES with alpha and beta parameters (0–1, step 0.05), using 266 days for training and forecasting the final 100 days.
  - Calculated training and test MSE, identified optimal smoothing parameters, and plotted actuals vs forecast.
- **Interpretation:** Compared model performance on train vs. test data and explained how well DES captured price trends.

### Part III: De-Seasonalizing and Forecasting Seasonal Series (Airline Load Factor)

- **Objective:** Forecast monthly airline load factors, a key metric in supply chain capacity planning, for the final two months of 2013.
- **Approach:**
  - **De-Seasonalizing:** Computed seasonal indices to remove monthly effects and reveal underlying trend/pattern.
  - **Stationarity Check:** Used ADF test on de-seasonalized data to determine suitable forecasting approach.
  - **Forecasting:** Applied method(s) justified by stationarity results (e.g., exponential smoothing if non-stationary, mean methods if stationary).
  - **Re-Seasonalizing:** Scaled forecasts back by adding back the seasonal factor before interpreting results.
- **Interpretation:** Explained the meaning of the forecast and how such projections can guide business capacity decisions.

## Key Results

### Part I: Stationary Series (Jeans Sales)

- **Best MA window**: 5 weeks; **Best ES alpha**: 0.1, both yielding lowest MSE.
- **Interpretation:** Moving Average model with a 5-week window and Exponential Smoothing with low alpha provide most accurate forecasts, indicating that small/random fluctuations are best anticipated by methods that smooth over multiple previous weeks rather than abrupt changes.
- **Recommendation:** For sales residuals, use 5-week MA or ES with alpha 0.1 for forecasting minor demand noise.

### Part II: Bitcoin Trend Forecasting

- **Data confirmed as non-stationary** (has a trend).
- **Optimal DES parameters** found by lowest MSE (see notebook for exact values).
- **Interpretation:** DES successfully models the underlying trend in the training period, with increased prediction error in the volatile test period—a common pattern in financial forecasting.
- **Recommendation:** DES is suitable for trending financial data, but forecasts should be interpreted with caution for periods of rapid shift.

### Part III: Airline Load Factor

- **Data is highly seasonal:** Must be de-seasonalized for accurate short-term forecasting.
- **ADF Test result:** Guides whether to use mean or smoothing/forecasting models.
- **Forecasts for December 2013:** Produced and re-scaled to include seasonality.
- **Interpretation:** Predicted values give management an expectation of demand for year-end planning, accounting for both recent trends and underlying monthly patterns.

## Business Impact & Interpretation

- **Inventory and Staffing:** Accurate week-to-week forecasting of demand "noise" helps avoid costly overstock or missed sales.
- **Financial Planning:** Trend-aware forecasting of assets (like bitcoin) supports smarter investment and risk management.
- **Capacity Planning:** Seasonal airline forecasts allow for proactive resource allocation—key for logistics and service efficiency.

## How to Run / Reproduce

1. Open `BA875-Ex-2-Time-Series-Forecasting.ipynb`.
2. Ensure all data files (`jeans_data_full_dataset.xlsx`, `bitcoin_data.xlsx`, `airline_data.xlsx`) are in the folder.
3. Run notebook cells in sequence to view the entire analysis, from data prep to model comparison and forecast interpretation.

### Requirements

- Python 3.x
- Libraries: `pandas`, `numpy`, `matplotlib`, `statsmodels`, `sklearn`

## Learning & Takeaways

- Developed hands-on skill with three major time series forecasting approaches (MA/ES, DES, de-seasonalizing).
- Enhanced ability to choose and justify the right forecasting model for a given business scenario.
- Practiced translating technical forecasts into actionable guidance for supply chain, finance, and management teams.

## Project Details

- **Completed:** March 2024
- **Course:** Operations and Supply Chain Analytics (BA875), Boston University MSBA

*This exercise demonstrates how to select, apply, and interpret forecasting models to solve real business problems, bridging the gap between analytics and actionable business recommendations for non-technical audiences.*
