# Model Equations

## Dependent Variable

The dependent variable for all regression models is:

`monthly_sales`

## Simple Regression Equations

### Simple Model 1: Footfall

`monthly_sales = 446,410.58 + 35.68 × footfall`

Interpretation: footfall is strongly associated with monthly sales. Each additional visitor is associated with about **35.68** additional monthly sales units.

### Simple Model 2: Marketing Spend

`monthly_sales = 560,777.35 + 2.13 × marketing_spend`

Interpretation: each additional unit of marketing spend is associated with about **2.13** additional monthly sales units. This is statistically significant, but the simple model has limited explanatory power compared with footfall.

### Simple Model 3: Inventory Availability

`monthly_sales = 484,814.26 + 2,217.83 × inventory_availability_pct`

Interpretation: each one-point increase in inventory availability percentage is associated with about **2,217.83** additional monthly sales units in the simple model. However, this model has low R-squared, so inventory should not be interpreted alone.

## Dummy Variable Explanation

Dummy variables were created for categorical variables.

### Region Dummy Variables

Reference category: **East**

Included dummies:

- `region_North`
- `region_South`
- `region_West`

Each coefficient shows the expected difference in monthly sales compared with East region, holding other variables constant.

### Store Type Dummy Variables

Reference category: **Airport**

Included dummies:

- `store_type_High_Street`
- `store_type_Mall`
- `store_type_Residential`

Each coefficient shows the expected difference in monthly sales compared with Airport stores, holding other variables constant.

The reference categories are excluded to avoid redundancy and the dummy variable trap.

## Multiple Regression Equation

The final model is:

`monthly_sales = 86,319.14 + 27.34×footfall + 1.21×marketing_spend + 3,062.21×inventory_availability_pct - 41,243.15×avg_discount_pct + 3,508.40×staff_count + 12,509.46×customer_rating + 15,157.29×holiday_flag - 3,438.11×competitor_distance_km - 24,475.84×store_type_High_Street - 11,862.24×store_type_Mall - 44,695.09×store_type_Residential + 9,948.71×region_North + 21,089.57×region_South + 25,291.42×region_West`

## Final Model Coefficients

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

## Final Model Selected

The multiple regression model was selected as the final model because it has the strongest explanatory power:

- R-squared: **0.8570**
- Adjusted R-squared: **0.8504**
- RMSE: **40,133.89**

## Business Meaning

The model suggests that sales are most strongly associated with demand and operational readiness. Footfall, marketing spend, inventory availability, staffing, customer rating, holiday timing, store type, and region all help explain monthly sales.

However, coefficients should be interpreted as associations, not automatic causal effects.
