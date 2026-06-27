# Model Comparison

## Purpose

This document compares the simple and multiple regression models used to explain `monthly_sales`.

## Model Comparison Table

| Model | Variables used | R² | Adj. R² | RMSE | Significant variables |
| --- | --- | --- | --- | --- | --- |
| Simple regression: monthly_sales vs footfall | footfall | 0.7363 | 0.7355 | 53,374 | footfall |
| Simple regression: monthly_sales vs marketing_spend | marketing_spend | 0.1672 | 0.1646 | 94,846 | marketing_spend |
| Simple regression: monthly_sales vs inventory_availability_pct | inventory_availability_pct | 0.0131 | 0.0100 | 103,251 | inventory_availability_pct |
| Multiple regression: operational and store drivers | footfall, marketing_spend, inventory_availability_pct, avg_discount_pct, staff_count, customer_rating, holiday_flag, competitor_distance_km, store_type_High_Street, store_type_Mall, store_type_Residential, region_North, region_South, region_West | 0.8570 | 0.8504 | 40,134 | footfall, marketing_spend, inventory_availability_pct, staff_count, customer_rating, holiday_flag, competitor_distance_km, store_type_High_Street, store_type_Residential, region_South, region_West |

## Interpretation

### Simple Regression: Footfall

The footfall model has R-squared of **0.7363**, which means footfall alone explains a large share of monthly sales variation. Its coefficient is **35.68**, meaning each additional visitor is associated with about **35.68** additional sales units.

This model is business-friendly because footfall is easy to understand and action. However, it ignores other drivers such as marketing, inventory, region, staffing, and store type.

### Simple Regression: Marketing Spend

The marketing spend model has R-squared of **0.1672**. The relationship is statistically significant, but the explanatory power is much lower than the footfall model.

This means marketing spend is associated with sales, but marketing spend alone is not enough to explain performance.

### Simple Regression: Inventory Availability

The inventory availability model has R-squared of **0.0131**. The coefficient is positive and statistically significant at the 5% level, but the model explains very little of sales variation on its own.

Inventory matters, but it should be interpreted alongside demand, staff, and store characteristics.

### Multiple Regression Model

The multiple regression model has R-squared of **0.8570** and adjusted R-squared of **0.8504**, making it the strongest model tested.

It is more useful for decision-making because it controls for several factors at the same time instead of isolating one variable.

## Significant Variables in Final Model

| Variable | Coefficient | P-value | Statistically useful at 5%? |
| --- | --- | --- | --- |
| footfall | 27.34 | 0.000000 | Yes |
| marketing_spend | 1.21 | 0.000000 | Yes |
| inventory_availability_pct | 3,062.21 | 0.000000 | Yes |
| avg_discount_pct | -41,243.15 | 0.224365 | No |
| staff_count | 3,508.40 | 0.002743 | Yes |
| customer_rating | 12,509.46 | 0.005245 | Yes |
| holiday_flag | 15,157.29 | 0.013923 | Yes |
| competitor_distance_km | -3,438.11 | 0.000000 | Yes |
| store_type_High_Street | -24,475.84 | 0.004798 | Yes |
| store_type_Mall | -11,862.24 | 0.186917 | No |
| store_type_Residential | -44,695.09 | 0.000001 | Yes |
| region_North | 9,948.71 | 0.130835 | No |
| region_South | 21,089.57 | 0.001619 | Yes |
| region_West | 25,291.42 | 0.000024 | Yes |

## Final Model Selection

The final model selected is the **multiple regression model**. It is selected because it has the highest explanatory power and gives leadership a more realistic view of the factors associated with monthly sales.

## Limitations

- The model does not prove causality.
- Store-level factors not included in the dataset may influence sales.
- Four months of data may not fully capture seasonality.
- Some variables, especially competitor distance, require business context before action.
