# Advanced Newsvendor Optimization
Optimizing Production and Pricing Decisions in Publishing Using Extensions to the Newsvendor Model

## Overview

This project explores two extensions to the standard **Newsvendor Model (NVM)** to enhance production and pricing decisions for a publishing company. The goal is to optimize the quantity of publications to print while considering not just the costs of overproduction and underproduction, but also the effect of price on demand and the costs associated with rushed printing and disposal.

The project is broken into the following parts:
1. **Extension 1**: Incorporates additional costs for rushed printing and disposal for overproduction.
2. **Extension 2**: Incorporates price-dependent demand, allowing for simultaneous optimization of both price and production quantity.

### Problem Statement

The main challenge addressed by this project is the balance between overproduction (leading to waste and disposal costs) and underproduction (leading to missed sales). The goal is to determine the optimal production quantity and price that maximizes profit while considering demand uncertainty and additional costs.

### Approach

1. **Linear Regression**: A linear regression model is fit to the historical price-demand data to understand the relationship between price and demand. The residuals from this regression are then used to simulate future demand scenarios.
2. **Extensions to NVM**: 
    - **Extension 1** adds costs for rushed printing and disposal.
    - **Extension 2** introduces price-sensitive demand and jointly optimizes price and production quantity using non-linear programming techniques.

## Key Results

### Optimal Production Quantity and Price

Based on the optimization models, the following optimal results were obtained:

| Model                              | Optimal Production Quantity (q) | Optimal Price (p) | Maximum Profit |
|------------------------------------|---------------------------------|-------------------|----------------|
| **Standard NVM**                   | 471.87                          | 1.00 (fixed)      | $231.48        |
| **Extension 1 (with costs)**       | 471.87                          | 1.00 (fixed)      | $231.48        |
| **Extension 2 (price-dependent demand)** | 535.29                      | 0.95              | $234.42        |

#### Insights from the Results:
- **Extension 2** (with price-dependent demand) resulted in a slightly higher maximum profit ($234.42) compared to both the **Standard NVM** and **Extension 1** (both at $231.48).
- The price optimization in **Extension 2** allows the model to better align production with customer demand, providing a clear advantage in terms of profitability.

### Sensitivity Analysis

To assess how changes in the dataset affect the optimal production and pricing decisions, a **bootstrap sampling** technique was used. This method generates multiple resampled datasets, each used to fit a new linear regression model and re-run the optimization.

### Key Findings from Sensitivity Analysis:
- **Extension 2** consistently yields higher profits across all bootstrapped samples, demonstrating that the incorporation of price-dependent demand enhances the robustness of the model.
- Small fluctuations in price (around $0.95) have a significant impact on profit, highlighting the importance of price optimization in a competitive market.
- The sensitivity of optimal production quantities to changes in price is evident in the scatter plot and histograms, where a small decrease in price can result in a substantial increase in demand.

## Conclusion and Recommendations

- **Extension 2 Outperforms Other Models**: Extension 2, which optimizes both price and production quantity, leads to higher profits than both Extension 1 and the Standard NVM. The ability to adjust price based on demand provides greater flexibility and profitability.
  
- **Limitations of Standard NVM and Extension 1**: While these models consider additional costs, they lack the dynamic pricing flexibility seen in Extension 2, resulting in lower profits.

- **Price Sensitivity**: The sensitivity analysis highlights the significant impact of price changes on profitability, emphasizing the need for dynamic pricing.

- **Recommendation**: Extension 2 is recommended for publishing operations as it offers a more adaptable and profitable solution by incorporating price-dependent demand and optimizing both price and quantity.

This project was guided as part of the Optimization course by Prof.Dan Mitchell at McCombs School of Business at University of Texas at Austin.
