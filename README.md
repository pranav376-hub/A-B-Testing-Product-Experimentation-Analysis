# A/B Testing & Product Experimentation Analysis

**Author:** [pranav376-hub](https://github.com/pranav376-hub)  
**Status:** Milestone 1 — Repository setup

An end-to-end product analytics case study that audits a 50,000-user homepage redesign experiment and turns statistical evidence into a defensible ship/no-ship recommendation.

## Business Question

The redesigned homepage reports a conversion lift. Should PulseFlow Analytics release it to 100% of users without harming user experience or revenue?

## Planned Analysis

- Profile skewed latency data and choose robust summary metrics.
- Measure funnel conversion and isolate device-specific friction.
- Build monthly cohort-retention matrices and a retention heatmap.
- Test conversion lift with a two-sample proportion z-test and 95% confidence interval.
- Check experiment integrity with SRM, segment, novelty-effect, and Welch's ARPU tests.
- Present the final recommendation in a one-page executive memo using the Minto SCR framework.

## Tools

Python · pandas · NumPy · SciPy · statsmodels · Matplotlib · Seaborn · Jupyter · Git/GitHub

## Repository Structure

```text
.
├── findings/       # Business findings and the final decision memo
├── notebooks/      # Reproducible analysis notebooks
├── sql/            # Supporting SQL, if required by a milestone
├── .gitignore
├── README.md
└── requirements.txt
```

## Milestone Checklist

- [x] Milestone 1: Set up the project repository
- [x] Milestone 2: Multi-step funnel and friction analysis
- [x] Milestone 3: Monthly Cohort Retention & Lifecycle Decay
- [ ] Milestone 4: A/B test statistical evaluation and diagnostics
- [ ] Milestone 5: Executive decision memo and portfolio delivery

> Analytical results will be added milestone by milestone after validation. No findings are reported before the analysis is complete.


## Milestone Highlights

## Milestone 3 — Monthly Cohort Retention & Lifecycle Decay

Built a monthly cohort retention matrix from M0 through M6 by mapping each customer to their first transaction month and counting each user once per active month.

### Key findings

- Average M1 retention is **54.6%**, representing a **45.4% first-month drop-off**.
- Average observed M3+ retention is **30.7%**.
- The retention curve is classified as **Flattening**: a steep initial decline followed by stabilization among a smaller loyal customer segment.
- Improving first-month activation is the primary business opportunity.

![Monthly cohort retention heatmap](findings/figures/03_cohort_retention_heatmap.png)