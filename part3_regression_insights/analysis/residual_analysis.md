# Residual Analysis

## Purpose

Residual analysis was conducted to compare actual monthly sales against predicted monthly sales from the selected final multiple regression model.

Residual formula:

`residual = actual monthly sales - predicted monthly sales`

Positive residuals mean the model under-predicted sales. Negative residuals mean the model over-predicted sales.

## Largest Positive Residuals

These stores performed better than the model expected.

| Store | Month | Region | Store type | Actual sales | Predicted sales | Residual |
| --- | --- | --- | --- | --- | --- | --- |
| STR-1058 | Feb 2025 | East | High Street | 870,937 | 759,920 | 111,017 |
| STR-1028 | Apr 2025 | East | Mall | 713,611 | 610,532 | 103,079 |
| STR-1073 | Mar 2025 | East | Residential | 813,317 | 721,416 | 91,901 |
| STR-1051 | Feb 2025 | East | Airport | 787,716 | 701,381 | 86,334 |
| STR-1026 | Apr 2025 | East | Mall | 625,514 | 540,235 | 85,279 |

## Largest Negative Residuals

These stores performed worse than the model expected.

| Store | Month | Region | Store type | Actual sales | Predicted sales | Residual |
| --- | --- | --- | --- | --- | --- | --- |
| STR-1023 | Feb 2025 | South | Mall | 627,172 | 764,039 | -136,867 |
| STR-1017 | Mar 2025 | West | High Street | 685,379 | 805,280 | -119,901 |
| STR-1012 | Jan 2025 | West | Residential | 595,468 | 709,914 | -114,446 |
| STR-1007 | Feb 2025 | West | Mall | 800,452 | 912,345 | -111,893 |
| STR-1060 | Jan 2025 | West | Mall | 721,079 | 808,022 | -86,942 |

## Business Interpretation

Large positive residuals may indicate stores that are outperforming because of factors not fully captured in the dataset. Possible explanations include better local management, stronger local demand, local events, better merchandising, or customer loyalty.

Large negative residuals may indicate stores that are underperforming despite having inputs that should have produced stronger sales. Possible explanations include poor execution, local competition, stock mix issues, lower service quality, or one-off operational problems.

## Under-Prediction and Over-Prediction Pattern

The largest positive residuals include several East region stores, meaning the model may be underestimating some East stores with strong local performance. The largest negative residuals include stores where the model expected stronger sales than actually achieved, which should be reviewed operationally.

## Recommendation from Residual Analysis

Leadership should not only rely on average model coefficients. The residual analysis should be used to identify:

- Stores that are outperforming and may hold best practices.
- Stores that are underperforming and need operational review.
- Possible missing variables for future models, such as local events, store manager quality, product mix, and campaign timing.
