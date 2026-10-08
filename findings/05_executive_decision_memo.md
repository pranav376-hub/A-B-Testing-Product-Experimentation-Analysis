# Executive Decision Memo: Homepage Experiment

**To:** CPO, VP of Growth, Lead Product Manager  
**Decision:** **DO NOT SHIP GLOBALLY. Run a controlled desktop-only follow-up test.**

## Situation

The Growth Team tested a new homepage with 50,000 users. Assignment passed the 50/50 sample ratio check (SRM p = 0.6355). Signup conversion rose from 2.84% in control to 3.21% in variant: a +0.3728 percentage-point lift (p = 0.0150; 95% CI: +0.0724 to +0.6733 pp).

## Complication

The statistically significant signup result is insufficient for a global release.

1. **MDE:** The observed +0.3728 pp lift falls below the +0.50 pp target. Because the confidence interval includes +0.50 pp, the experiment does not establish that the target was cleared.
2. **Revenue guardrail:** Mean 30-day revenue per user fell from $3.31 to $2.92 (−11.98%; Welch p = 0.0323). This is a statistically significant adverse result.
3. **Mobile friction:** Desktop signup lift was +0.91 pp (p = 0.0002), while mobile lift was −0.16 pp (p = 0.3983). The effects differed by device (interaction p = 0.0005). Mobile revenue was $2.67 in control versus $1.92 in variant; this segment revenue comparison is descriptive. A separate funnel analysis also found mobile Cart-to-Checkout conversion of 30.14%, versus 61.14% on desktop.
4. **Time:** Signup lift declined from +0.47 pp in Week 1 to +0.27 pp in Week 2. The change between weeks was not statistically significant (p = 0.5089), so novelty decay remains a concern to monitor, not a confirmed finding.

## Resolution

**Reject a global rollout.** A p-value below 0.05 answers whether the overall signup rates differ; it does not show that the lift clears the business target or compensate for lost revenue. The desktop result merits a controlled follow-up, but the device findings are exploratory and desktop revenue safety has not been established in a dedicated test.

## Next Steps

- **Product and engineering:** Inspect mobile layout, CTA visibility, form errors, page speed, and event tracking. Investigate where signups fail to produce revenue.
- **Analytics and Growth:** Pre-register a desktop-only experiment with a signup target, an agreed revenue guardrail and stopping rule, a fixed analysis date, and a persistent control holdout.
- **Release decision:** Consider wider desktop exposure only after the follow-up meets its predefined success and revenue criteria. Keep mobile on control while its friction is investigated.