# User Retention & Cohort Analysis Framework
### Churn Prediction for Subscription & Marketplace Businesses

---

## Overview

This project builds a cohort-based retention analysis and churn prediction framework — the standard methodology used by Netflix, Spotify, Airbnb, and other subscription and marketplace businesses to understand user lifecycle, measure retention, and identify at-risk users before they churn.

**Built with:** Python, Pandas, Scikit-learn, Matplotlib, Seaborn

---

## Key Analyses

1. **Cohort Retention Heatmap** — Visualize retention rates across acquisition cohorts to identify improving or deteriorating trends
2. **Retention Curves** — Plot survival curves by cohort to understand lifecycle drop-off patterns
3. **Churn Segmentation** — Break down churn rates by acquisition channel and plan type to surface highest-value user segments
4. **Churn Prediction Model** — Logistic regression using early engagement signals to identify at-risk users within their first week

---

## Methodology

### Cohort Construction
Users are grouped by acquisition month and tracked across subsequent months to measure retention. This approach isolates cohort-level trends from overall growth effects.

### Churn Prediction Features

| Feature | Type | Signal |
|---------|------|--------|
| Day 1 actions | Engagement | Early product activation |
| Week 1 sessions | Engagement | Habit formation signal |
| Plan type | Behavioral | Intent and commitment level |
| Acquisition channel | Source | User quality by channel |

### Model
Logistic regression with StandardScaler normalization. AUC-ROC used as primary evaluation metric given class imbalance in churn datasets.

---

## Key Findings

| Metric | Insight |
|--------|---------|
| M3 Retention | Critical intervention window — most churn occurs months 1-3 |
| Referral vs Paid Social | ~15% churn gap — referral users are significantly higher quality |
| Premium vs Basic | ~20% churn gap — plan upgrade is the strongest retention lever |
| Model AUC | >0.65 using only first-week engagement signals |

---

## Business Recommendations

1. **Early engagement interventions** — Day-1 actions are the strongest early churn predictor. Onboarding nudges in the first 48 hours meaningfully improve M3 retention.
2. **Referral program investment** — Referral-acquired users show lowest churn. Compounding retention effect on LTV.
3. **Plan upgrade prompts** — Strategic upgrade prompts during high-engagement moments improve both retention and LTV.
4. **Cohort monitoring** — Deteriorating M3 retention in recent cohorts is an early warning signal for product or acquisition quality issues.

---

## Files

```
├── user_retention_cohort_analysis.ipynb   # Main analysis notebook
├── README.md                              # Project documentation
```

---

## How to Run

```bash
git clone https://github.com/mcdeverin/user_retention_cohort_analysis.git
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook user_retention_cohort_analysis.ipynb
```

---

## Framework Generalization

This analysis applies directly to:
- **Streaming platforms** — content consumption as the engagement signal
- **Marketplaces** — transaction frequency as the retention signal
- **SaaS products** — feature adoption as the churn predictor
- **Media subscriptions** — content engagement depth as the retention driver

---

*Built as part of a portfolio demonstrating applied data science in user retention and growth analytics.*
