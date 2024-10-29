# User LTV Calculation Through Cohort Analysis

This notebook contains code for calculating user LTV through cohort analysis and retention rate.

## Overview of the Dataset

![Dataset Overview](https://github.com/user-attachments/assets/d6e916b4-c9f5-4aad-89b6-466b34d940dd)

Firstly, the data is divided into monthly cohorts based on the first payment event. Cohort analysis is then performed, calculating the retention rate by determining the percentage of users who remain active each month after their first purchase. A pivot table is created and visualized to show each cohorts retention rate over months.

![Cohort Analysis](https://github.com/user-attachments/assets/e617dbb6-f958-4f4e-85df-1de3a460c13f)

#### Next steps include :

 Counting Revenue Per Cohort: 
   - Pivot table (`revenue_cohorts`) is created to group data by `first_purchase_month` and `cohort_lifetime`, counting unique users (`uuid`) and summing `revenue_usd`.

 Total Revenue Calculation: 
   - Using `groupby` total revenue is calculated for each cohort's first purchase month.

 LTV Calculation: 
   - Having revenue, retention, and unique users for each cohort, LTV is calculated by multiplying each cohort's retention rate by its revenue.

 Plotting Retention Curves: 
   - Each cohort's retention rate over time is visualized to analyze retention trends across months.
![Retention curves](https://github.com/user-attachments/assets/fb9cc5a2-0266-4e36-b5cf-a71e7ca9f79c)

#### Exponential Curve Fitting for future prediction

The last part of code includes exponential curve fit to the retention rates for selected cohorts (03_2023, 04_2023, and 05_2023, as they contain the most data). Then we calculate the fitting parameters \(a\) and \(b\) for each cohort and visualize the actual retention against the fitted curve.
![Retention Curve Fit](https://github.com/user-attachments/assets/70691eeb-3887-4cc2-8590-c43015eece4f)
Future retention rates are projected for up to 14 months (8 actual + 6 predicted)  based on the fitted curves. The results are then plotted to compare actual retention with projected retention 
for each cohort.
![Future Retention Projections](https://github.com/user-attachments/assets/87c6cc11-325a-4924-8e73-474124a198ef)
