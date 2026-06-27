# Part 3: Regression-Based Business Insights & Model Interpretation

## Business Problem Summary

The retail leadership team wants to understand which factors are most strongly associated with monthly sales performance across stores. The purpose of this analysis is to support decisions about marketing spend, inventory availability, staffing, discount strategy, and store-level prioritisation.

The key business question is:

**Which measurable store and operating factors are most useful for explaining monthly sales, and what actions should leadership prioritise?**

## Dataset Description

The dataset contains **320 store-month records** across **80 stores** and **4 months**.

The original dataset is stored in:

`data/business_regression_data.xlsx`

The regression analysis workbook is stored in:

`analysis/regression_workbook.xlsx`

## Dependent and Independent Variables

### Dependent Variable

- `monthly_sales`

This is the target variable the models try to explain.

### Potential Independent Variables

Numerical predictors reviewed:

- `marketing_spend`
- `footfall`
- `avg_discount_pct`
- `staff_count`
- `inventory_availability_pct`
- `competitor_distance_km`
- `holiday_flag`
- `customer_rating`

Categorical predictors reviewed:

- `region`
- `store_type`

Variables not used as main predictors:

- `store_id`: identifier only, not a business driver by itself.
- `month`: useful for context, but only four months are available, so it was not used as a main driver in the final regression model.
- `monthly_profit`: another outcome metric, not a suitable predictor for monthly sales because it would create leakage.

## Data Preparation

The following preparation checks were completed:

| Check | Result | Handling |
| --- | --- | --- |
| Raw records | 320 | Input rows excluding header |
| Exact duplicate rows | 0 | None found |
| Duplicate store_id + month pairs | 0 | None found |
| Missing customer_rating | 8 | Imputed with median 3.90 |
| Missing competitor_distance_km | 6 | Imputed with median 3.37 |
| Invalid holiday_flag binary values | 0 | Expected values are 0 and 1 |
| Monthly sales outliers by IQR | 0 | Flagged only |
| Monthly profit outliers by IQR | 1 | Flagged only |

Missing `customer_rating` values were imputed using the median value of **3.90**. Missing `competitor_distance_km` values were imputed using the median value of **3.37**. No exact duplicate rows or duplicate store-month records were found.

## Dummy Variable Approach

Dummy variables were created for:

- `region`
- `store_type`

Reference categories:

- Region reference category: **East**
- Store type reference category: **Airport**

Only `k-1` dummy variables were included for each categorical variable to avoid redundancy and the dummy variable trap.

## Regression Approach

The analysis includes:

1. Simple regression: `monthly_sales` vs `footfall`
2. Simple regression: `monthly_sales` vs `marketing_spend`
3. Simple regression: `monthly_sales` vs `inventory_availability_pct`
4. Multiple regression using operational, marketing, store type, and region predictors

## Model Comparison Summary

| Model | Variables used | R² | Adj. R² | RMSE | Significant variables |
| --- | --- | --- | --- | --- | --- |
| Simple regression: monthly_sales vs footfall | footfall | 0.7363 | 0.7355 | 53,374 | footfall |
| Simple regression: monthly_sales vs marketing_spend | marketing_spend | 0.1672 | 0.1646 | 94,846 | marketing_spend |
| Simple regression: monthly_sales vs inventory_availability_pct | inventory_availability_pct | 0.0131 | 0.0100 | 103,251 | inventory_availability_pct |
| Multiple regression: operational and store drivers | footfall, marketing_spend, inventory_availability_pct, avg_discount_pct, staff_count, customer_rating, holiday_flag, competitor_distance_km, store_type_High_Street, store_type_Mall, store_type_Residential, region_North, region_South, region_West | 0.8570 | 0.8504 | 40,134 | footfall, marketing_spend, inventory_availability_pct, staff_count, customer_rating, holiday_flag, competitor_distance_km, store_type_High_Street, store_type_Residential, region_South, region_West |

The final selected model is the **multiple regression model** because it has the highest explanatory power with R-squared of **0.8570** and adjusted R-squared of **0.8504**.

## Final Model Selected

The final model includes:

- Footfall
- Marketing spend
- Inventory availability
- Average discount percentage
- Staff count
- Customer rating
- Holiday flag
- Competitor distance
- Store type dummy variables
- Region dummy variables

## Business Recommendation

Leadership should prioritise:

1. Increasing qualified store footfall.
2. Maintaining strong inventory availability.
3. Allocating marketing spend carefully to stores where it can create measurable incremental traffic.
4. Reviewing staffing levels in high-demand stores.
5. Monitoring customer experience because customer rating has a positive association with sales.

Leadership should **not blindly increase discounts** because `avg_discount_pct` was not statistically strong in the final model.

## Assumptions and Limitations

- Regression shows association, not automatic causation.
- The model is based on observational business data, not a randomized experiment.
- Missing numeric values were median-imputed.
- Competitor distance has a counterintuitive negative coefficient and should not be over-interpreted without more business context.
- The dataset covers only four months, so seasonal effects may not be fully captured.
- Store-level unobserved differences may still affect sales.

## Screenshots Included

The following screenshots are included:

- `screenshots/simple_regression_output.png`
- `screenshots/multiple_regression_output.png`
- `screenshots/residuals_preview.png`
- `screenshots/model_comparison_preview.png`
