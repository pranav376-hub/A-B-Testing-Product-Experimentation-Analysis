# A/B Test Experiment Diagnostics

## Executive Decision

**Do not launch the variant globally.**

The variant produced a statistically significant improvement in signup conversion, but it also caused a statistically significant decline in 30-day revenue per user. Device analysis shows that the improvement is concentrated on desktop, while mobile users experience weaker conversion and substantially lower revenue.

![Milestone 4 experiment diagnostics](figures/m4_experiment_diagnostics.png)

## Experiment Validation

The experiment contains 50,000 users:

- Control: 25,053 users
- Variant: 24,947 users
- Duplicate rows: 0
- Missing values: 0

A chi-square Sample Ratio Mismatch test returned a p-value of **0.6355**. Therefore, there is no evidence that the observed allocation differs from the intended 50/50 assignment.

## Primary Metric: Signup Conversion

Signup conversion increased from **2.84% in control to 3.21% in variant**.

- Absolute lift: **+0.37 percentage points**
- Relative lift: **+13.12%**
- Z-statistic: **2.4326**
- P-value: **0.0150**
- 95% Wald confidence interval: **+0.07 to +0.67 percentage points**

The result is statistically significant because the p-value is below 0.05 and the confidence interval excludes zero.

## Guardrail: 30-Day Revenue

Mean 30-day revenue per user decreased from **$3.31 to $2.92**.

- Absolute difference: **-$0.40 per user**
- Relative change: **-11.98%**
- Welch t-statistic: **-2.1411**
- P-value: **0.0323**

The revenue decline is statistically significant. Therefore, the variant fails the revenue guardrail despite improving signup conversion.

## Novelty Check

The signup lift was **+0.47 percentage points in Week 1** and **+0.27 percentage points in Week 2**.

The Week 2-minus-Week 1 effect change was **-0.20 percentage points**, with a p-value of **0.5089**. Although the observed lift became smaller, there is insufficient evidence to conclude that the treatment effect genuinely faded over time.

## Device Analysis

Desktop users responded positively:

- Control conversion: **3.39%**
- Variant conversion: **4.31%**
- Absolute lift: **+0.91 percentage points**
- P-value: **0.0002**

Mobile users did not benefit:

- Control conversion: **2.29%**
- Variant conversion: **2.13%**
- Absolute lift: **-0.16 percentage points**
- P-value: **0.3983**

The mobile-minus-desktop treatment-effect difference was **-1.07 percentage points**, with a p-value of **0.0005**. This confirms statistically significant device-level divergence.

Mobile revenue also declined from **$2.67 to $1.92**, while desktop revenue remained approximately stable at **$3.95 versus $3.92**.

## Recommendation

Do not implement a full rollout. Investigate mobile usability, tracking, checkout behaviour, and the reason additional signups generate less revenue. A desktop-only version may be tested in a follow-up experiment, but it should include a predefined revenue non-inferiority guardrail before launch approval.