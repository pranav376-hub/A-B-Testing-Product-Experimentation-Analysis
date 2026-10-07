# Multi-Step Funnel and Friction Analysis

## Executive Summary

This analysis examined the five-stage customer journey from Homepage to Payment using clickstream data representing 10,000 users. After removing 3,000 duplicate tracking events, each user was counted only once per funnel stage. The results reveal that mobile users experience severe friction when progressing from Cart to Checkout, making this transition the most important product improvement opportunity.

## Methodology

The raw clickstream contained 26,061 event rows, including repeated tracking events caused by simulated refreshes and user re-entry. Records were deduplicated at the `user_id + funnel_stage` grain, leaving 23,061 valid user-stage observations.

For each funnel stage, three metrics were calculated:

- Step-over-step conversion rate relative to the preceding stage
- Step drop-off rate and absolute user loss
- Cumulative conversion relative to Homepage users

The same calculations were then segmented by Desktop and Mobile device types.

## Key Findings

Of the 10,000 users entering the Homepage, 6,731 reached the Product Page, 3,396 added a product to the Cart, 1,633 reached Checkout, and 1,301 completed Payment. The overall Homepage-to-Payment conversion rate was therefore 13.01%.

The largest absolute user loss occurred between Product Page and Cart, where 3,335 users exited. However, the highest proportional drop-off occurred between Cart and Checkout: 51.91% of Cart users failed to continue.

Device segmentation exposed a concentrated mobile bottleneck. Desktop Cart-to-Checkout conversion was 61.14%, while Mobile conversion was only 30.14%—a 31.00 percentage-point gap. Consequently, Mobile lost 69.86% of users at this transition.

The problem appears specific to entering Checkout rather than completing Payment. Among users who reached Checkout, Desktop Payment conversion was 80.20% and Mobile conversion was 78.19%, a difference of only 2.01 percentage points.

## Recommendation

The product team should prioritize investigation of the mobile Cart-to-Checkout transition. Potential causes—including CTA visibility, page speed, form usability, validation errors, and responsive-layout issues—should be tested rather than assumed.

The next step should combine mobile error-log analysis, session replays, and usability testing. A targeted A/B test should then evaluate the most evidence-supported checkout improvement. Success should be measured through Mobile Cart-to-Checkout conversion while monitoring Payment completion and revenue as guardrail metrics.

Because this case study uses synthetic clickstream data, the findings demonstrate the analytical process and decision framework rather than actual customer behaviour.