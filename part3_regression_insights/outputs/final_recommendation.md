# Final Recommendation

## Executive Summary

The regression analysis shows that monthly sales are most strongly associated with **footfall**, followed by operational and commercial factors such as **marketing spend**, **inventory availability**, **staff count**, **customer rating**, store type, and region.

The strongest overall model is the multiple regression model, with R-squared of **0.8570** and adjusted R-squared of **0.8504**.

## Factors Most Strongly Associated with Monthly Sales

The final model indicates the following:

- `footfall` has a strong positive association with sales.
- `marketing_spend` has a positive and statistically significant association with sales.
- `inventory_availability_pct` has a positive and statistically significant association with sales.
- `staff_count` has a positive and statistically significant association with sales.
- `customer_rating` has a positive and statistically significant association with sales.
- Region and store type also matter, meaning store context affects sales performance.

## Variables Leadership Should Focus On

Leadership should focus on:

1. **Footfall growth**
   - Improve local campaigns, store visibility, and traffic-driving activities.
   - Footfall is the strongest simple predictor of monthly sales.

2. **Inventory availability**
   - Avoid stockouts because better availability is associated with higher sales.
   - Inventory improvement is actionable and operationally realistic.

3. **Marketing efficiency**
   - Marketing spend is useful, but it should be tied to footfall and conversion outcomes.
   - Do not increase spending everywhere without tracking incremental results.

4. **Staff allocation**
   - Higher staff count is associated with higher sales, suggesting service capacity matters.
   - Prioritise staff allocation in high-footfall or high-opportunity stores.

5. **Customer experience**
   - Customer rating has a positive association with sales.
   - Service quality should be part of sales improvement planning.

## Variables That Should Not Be Over-Interpreted

### Average Discount Percentage

`avg_discount_pct` is not statistically strong in the final model. Leadership should not assume that deeper discounts automatically increase monthly sales.

### Competitor Distance

`competitor_distance_km` has a statistically significant but counterintuitive negative coefficient. This may reflect market density, location attractiveness, or omitted location factors. Leadership should not make real-estate decisions based only on this coefficient.

### Store Type and Region

Store type and region are useful for segmentation, but they should be used for prioritisation rather than simplistic conclusions such as “one region is always better.”

## Recommended Business Action

The recommendation is:

**Prioritise a combined growth plan focused on traffic, inventory availability, and operational readiness rather than relying on discounting alone.**

Practical next steps:

1. Increase targeted marketing for stores where footfall can realistically grow.
2. Improve inventory availability in stores with sales potential.
3. Review staffing levels for high-traffic stores.
4. Study high positive residual stores to identify best practices.
5. Investigate high negative residual stores for execution problems.
6. Test marketing and inventory interventions before scaling them chain-wide.

## Why This Is Not Proof of Causation

Regression shows association, not automatic causation. For example, marketing spend may be higher in stores that already have stronger sales potential. Similarly, staffing may be higher because stores are larger or busier, not necessarily because staffing alone causes higher sales.

To prove causation, leadership would need controlled experiments, such as:

- Marketing A/B tests by store group.
- Inventory improvement pilots.
- Staffing level pilots.
- Regional campaign experiments.

## Risks and Limitations

- The dataset covers only four months.
- Some missing values were median-imputed.
- Important drivers like store size, product mix, local events, and manager quality are not included.
- The model may still have omitted-variable bias.
- Regression coefficients should be used as guidance, not as final proof.

## Final Recommendation

Leadership should use the final regression model as a decision-support tool and launch targeted business actions around footfall, inventory, marketing efficiency, staffing, and customer experience. Leadership should avoid making decisions based only on discounts or any single coefficient.
