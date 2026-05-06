# Survival Analysis: Heart Failure Clinical Records

**Author:** Aaron Pongsugree  
**Tools:** R, R Markdown, survival, survminer, gtsummary, broom  
**Dataset:** [Heart Failure Clinical Records — Kaggle](https://www.kaggle.com/datasets/andrewmvd/heart-failure-clinical-data)

---

## Overview

This project applies survival analysis techniques to clinical data from 299 heart failure patients to identify predictors of mortality. The analysis covers Kaplan-Meier survival estimation, log-rank hypothesis testing, and Cox Proportional Hazards regression.

---

## Objectives

- Estimate survival functions using Kaplan-Meier (KM) curves
- Compare survival between clinically relevant subgroups via log-rank tests
- Identify independent predictors of death using a multivariable Cox PH model

---

## Dataset

The Heart Failure Clinical Records Dataset (Chicco & Jurman, 2020) contains 299 patients recruited at the Faisalabad Institute of Cardiology (Pakistan, 2015), with follow-up ranging from 4 to 285 days. It includes 13 clinical features such as ejection fraction, serum creatinine, age, and blood pressure status.

> Data is publicly available on Kaggle — not included in this repository.  
> Download it and place the CSV in a `data/` folder before knitting.

---

## Key Findings

| Predictor | HR | p-value |
|---|---|---|
| Serum Creatinine | 1.356 | < 0.001 |
| Age | 1.045 per year | < 0.001 |
| Ejection Fraction | 0.954 per unit | < 0.001 |
| High Blood Pressure | 1.606 | 0.026 |
| Serum Sodium | 0.958 | 0.068 (borderline) |

- 32.1% mortality rate over a median follow-up of 115 days; median survival was not reached
- Ejection fraction, serum creatinine, and age group all showed significant survival differences via log-rank test (all p < 0.0001)
- Global Schoenfeld test confirmed PH assumption was met (p = 0.207); concordance = 0.73

---

## Analysis Structure

```
SA_Heart_Failure.Rmd
│
├── 1. Introduction
├── 2. Data Overview
├── 3. Setup & Data Loading
├── 4. Descriptive Statistics
├── 5. Kaplan-Meier Survival Estimates
│   ├── 5.1 Overall Survival
│   ├── 5.2 Survival by Ejection Fraction Group
│   ├── 5.3 Survival by Serum Creatinine Group
│   └── 5.4 Survival by Sex
├── 6. Log-Rank Tests
├── 7. Cox Proportional Hazards Model
│   ├── 7.1 Univariable Cox Models
│   ├── 7.2 Multivariable Cox Model
│   └── 7.3 Proportional Hazards Assumption Check
├── 8. Key Findings
├── 9. Conclusion
└── 10. References
```

---

## How to Run

1. Clone this repository
2. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/andrewmvd/heart-failure-clinical-data) and place it at `data/heart_failure_clinical_records_dataset.csv`
3. Open `SA_Heart_Failure.Rmd` in RStudio
4. Click **Knit** — missing packages will install automatically

---

## Reference

Chicco, D., & Jurman, G. (2020). Machine learning can predict survival of patients with heart failure from serum creatinine and ejection fraction alone. *BMC Medical Informatics and Decision Making, 20*(16).
