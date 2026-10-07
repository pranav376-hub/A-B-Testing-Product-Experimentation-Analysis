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

## Project Progress

- [x] Milestone 1: Set up the project repository
- [x] Milestone 2: Multi-step funnel and friction analysis- [ ] Milestone 3: Monthly cohort retention and lifecycle decay
- [ ] Milestone 4: A/B test statistical evaluation and diagnostics
- [ ] Milestone 5: Executive decision memo and portfolio delivery

> Analytical results will be added milestone by milestone after validation. No findings are reported before the analysis is complete.

