# A/B Test Experiment Diagnostics

## Executive Decision

**Do not launch the variant globally.**

The variant improves signup conversion, but the observed lift does not reach the +0.5 percentage point minimum detectable effect (MDE). It also produces a statistically significant decline in 30-day revenue per user. The signup benefit is concentrated on desktop; mobile shows no significant conversion benefit and substantially lower observed revenue.

![Milestone 4 experiment diagnostics](figures/m4_experiment_diagnostics.png)

## Experiment Validation

The experiment contains 50,000 unique users: 25,053 in control and 24,947 in variant. There are no duplicate rows or missing values.

A chi-square Sample Ratio Mismatch (SRM) test against the intended 50/50 allocation returned a statistic of 0.2247 and p-value of 0.6355. We found no evidence of an allocation mismatch.

## Primary Metric: Signup Conversion

Signup conversion increased from 2.84% in control to 3.21% in variant.

- Absolute lift: +0.37 percentage points
- Relative lift: +13.12%
- Two-sample Z-statistic: 2.4326
- Two-sided p-value: 0.0150
- 95% Wald confidence interval for variant minus control: +0.07 to +0.67 percentage points

The difference is statistically significant at the 5% level because the confidence interval excludes zero.

### Minimum Detectable Effect Check

The observed +0.37 percentage point lift is below the specified +0.5 percentage point MDE. The 95% confidence interval includes +0.5 percentage points. Therefore, the experiment does **not establish** that the variant clears the target, although the data also do not rule out a true lift above it. Statistical significance against zero alone is insufficient to claim that the target was met.

## Guardrail: 30-Day Revenue per User

Mean 30-day revenue per user decreased from $3.31 in control to $2.92 in variant.

- Absolute difference: approximately -$0.40 per user
- Relative change: -11.98%
- Welch t-statistic: -2.1411
- Two-sided p-value: 0.0323

Welch's two-sample t-test used `equal_var=False`. The observed revenue decline is statistically significant at the 5% level, so the variant fails the revenue guardrail.

## Novelty Check

Signup lift was +0.47 percentage points in Week 1 and +0.27 percentage points in Week 2. The Week 2 minus Week 1 change was -0.20 percentage points, with p = 0.5089.

The observed lift is smaller in Week 2, but the difference between weekly treatment effects is not statistically significant. We cannot conclude that the effect faded.

## Device Analysis

| Device | Control signup | Variant signup | Lift | Signup p-value | Control revenue | Variant revenue |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Desktop | 3.39% | 4.31% | +0.91 pp | 0.0002 | $3.95 | $3.92 |
| Mobile | 2.29% | 2.13% | -0.16 pp | 0.3983 | $2.67 | $1.92 |

The mobile-minus-desktop signup treatment-effect difference is -1.07 percentage points, with p = 0.0005. This provides evidence that the signup effect differs by device. The mobile signup decline alone is not statistically significant. Mobile revenue is substantially lower in the variant; this segment comparison is descriptive here and has not been separately tested for statistical significance.

## Recommendation

Do not launch globally. Investigate mobile usability, tracking, checkout behavior, and why the additional signups do not translate into revenue. A desktop-only follow-up experiment is worth considering, with its signup target and revenue guardrail specified before the test begins.