# Monthly Cohort Retention and Lifecycle Decay

## Objective

This analysis evaluates whether newly acquired customer cohorts retain better than older cohorts and identifies how quickly engagement declines after acquisition. Users were grouped by their first active transaction month, which represents the acquisition cohort. Each later active month was converted into a cohort index from M0 through M6. Multiple transactions by the same user within one month were deduplicated so that every user was counted only once per active month.

![Monthly cohort retention heatmap](figures/03_cohort_retention_heatmap.png)

## Key Findings

Month 0 retention is 100% for every cohort, confirming that cohort sizes and retention denominators were calculated correctly. Average M1 retention is 54.6%, meaning the product loses approximately 45.4% of newly acquired customers immediately after their acquisition month. This first-month decline is the largest and most commercially important point of lifecycle friction.

M1 retention ranges from 52.4% to 57.9% across the observable cohorts. The relatively narrow range indicates that the initial drop is persistent rather than being caused by one unusually weak acquisition month. Retention continues declining after M1, but at a slower rate. Average observed retention from M3 onward is 30.7%, while the oldest January cohort reaches 25.0% by M6.

The blank cells in the heatmap are expected. Newer cohorts have not existed long enough to reach later cohort ages, producing the required triangular retention structure.

## Curve Classification

The retention curve is classified as **Flattening**. It shows a steep decline between M0 and M1, followed by progressively smaller reductions from approximately M3 onward. This suggests that the product loses many customers during early lifecycle activation but retains a smaller, comparatively loyal customer group over time.

The pattern is not a smiling curve because retention does not recover at later ages. It is also not a continuously worsening leaky bucket because the rate of decline slows and begins to stabilize.

## Recommendations

The primary business priority should be improving first-month activation. The product team should examine onboarding completion, time to first value, and early repeat-purchase behaviour. Lifecycle messaging, personalised recommendations, and targeted incentives should be tested during the first 30 days.

Customers who remain active through M3 form a more stable segment. Their behaviours, acquisition channels, devices, and purchase categories should be compared with early churners to identify characteristics associated with long-term retention.

Because this portfolio dataset is synthetically generated and reproducible, the findings demonstrate the analytical method rather than claiming actual company performance. In production, the same analysis should be refreshed monthly and segmented by channel, geography, device, and customer value.