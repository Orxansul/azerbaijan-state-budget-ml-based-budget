# Azerbaijan State Budget — ML-Assisted Budget Execution & Anomaly Analysis

## 2024–2025 Forecast vs Execution, Residual Analysis & Stability-Aware Anomaly Detection

## Project Overview

This project analyzes Azerbaijan state budget allocations and execution using publicly available functional-classification data for 2024 and 2025.

The workflow combines data quality validation, forecast-vs-execution analysis, year-to-year paired comparison, deviation persistence, residual analysis, Isolation Forest anomaly detection and stochastic stability testing.

The objective is to identify meaningful execution deviations and model-based anomaly signals rather than create an unsupported numerical financial-risk score.

## Research Question

Which functional budget categories show persistent under-execution or unusual execution/deviation patterns across 2024–2025, and which observations are identified as anomalous by a machine-learning model?

## Dataset

- 155 source observations
- 5 source columns
- 2 years: 2024 and 2025
- 79 unique functional codes
- 0 exact duplicate rows
- 0 missing cells
- 3 missing code-year combinations
- 76 functional codes common to both years

## Key Results

| Metric | Result |
|---|---:|
| Raw observations | 155 |
| Unique functional codes | 79 |
| Paired functional codes | 76 |
| Persistent below forecast | 74 / 76 (97.37%) |
| Reference ML anomalies | 10 / 76 (13.16%) |
| Anomalies in all 10 tested seeds | 6 |
| Anomalies in at least one tested seed | 12 |
| Mean pairwise Jaccard overlap | 0.7305 |
| Multi-evidence observations | 61 / 76 (80.26%) |

## Annual Execution Summary

| Year | Forecast | Execution | Variance | Execution Rate | Deviation Rate |
|---|---:|---:|---:|---:|---:|
| 2024 | 79.48B AZN | 75.43B AZN | -4.06B AZN | 94.90% | -5.10% |
| 2025 | 82.82B AZN | 77.21B AZN | -5.61B AZN | 93.23% | -6.77% |

## Analytical Workflow

Raw Data
→ Structural Validation
→ Data Quality
→ 2024–2025 Paired Analysis
→ Deviation Persistence
→ Residual Analysis
→ Isolation Forest
→ Evidence Integration
→ Stability Testing
→ Final Analytical Evidence

## 1. Data Validation

The source dataset contains 155 observations across 2024 and 2025.

There are no exact duplicate rows and no missing cells.

Three expected code-year combinations are absent:

- 10.1 — 2024
- 11.8 — 2025
- 5.3 — 2024

These combinations are not imputed.

## 2. Paired 2024–2025 Analysis

The direct year-to-year comparison uses only the 76 functional codes observed in both years.

Among these 76 paired codes:

- 74 remained below forecast in both years.
- 1 changed deviation direction.
- 1 remained equal to forecast.

## 3. Deviation Analysis

The analysis evaluates:

- Forecast amount
- Execution amount
- Absolute variance
- Execution rate
- Deviation rate
- Year-to-year deviation changes

The goal is to distinguish persistent patterns from isolated observations.

## 4. Residual Analysis

Residual relationships are evaluated for the paired functional codes before machine-learning anomaly detection.

The residual models report:

- 2024 R² = 0.3185
- 2025 R² = 0.6157

These relationships are used as analytical evidence and not as causal models.

## 5. Isolation Forest

Isolation Forest is used to identify unusual observations in the multivariate analytical feature space.

The reference model identifies 10 anomalies among the 76 paired functional codes.

The anomaly label is model-based and descriptive.

## 6. Stability Analysis

Because Isolation Forest is stochastic, the analysis tests 10 random states.

Results:

- Minimum anomaly count: 6
- Maximum anomaly count: 9
- Mean anomaly count: 7.5
- Mean pairwise Jaccard overlap: 0.7305
- 6 functional codes are anomalous in all tested seeds
- 12 are anomalous in at least one tested seed

The stable anomaly codes are:

1.7 — Dövlət borcu
1.3 — Xarici yardımlar
7.2 — Televiziya, radio və nəşriyyat
9.9 — Kənd təsərrüfatı üzrə digər müəssisə və tədbirlər
10.3 — Torpaq və yerquruluşu
8.3 — Su təsərrüfatı

## 7. Evidence-Based Interpretation

The project separates:

- budget execution deviation,
- persistent under-execution,
- residual evidence,
- model-detected anomaly signals,
- stability of those anomaly signals.

No numerical risk score is created.

No manual weights are used.

No arbitrary risk threshold is introduced.

## Important Interpretation Note

A model-detected anomaly does not automatically indicate fraud, corruption, misuse or another form of misconduct.

The results should be interpreted as analytical evidence for further investigation.

## Limitations

- The source dataset covers only 2024 and 2025.
- Three code-year combinations are missing.
- Paired analysis is limited to 76 common functional codes.
- Isolation Forest is stochastic.
- Anomaly detection does not establish causality or the underlying explanation.
- Annual totals are based on all available code-year observations and do not impute missing combinations.

## Selected Visualizations

See the `figures/` directory for selected analytical outputs covering:

- Forecast vs execution
- Largest absolute deviations
- ML anomaly signals
- Isolation Forest stability
- Evidence profile distribution

## Power BI Dashboard

The project was also developed as a five-page Power BI analytical dashboard covering budget execution, functional-area deviations, year-to-year changes, evidence-based risk profiling and ML anomaly stability.

### 1. Budget Overview
Forecast vs execution across 2024–2025, including total budget execution and major absolute deviations.

![<img width="1158" height="654" alt="image" src="https://github.com/user-attachments/assets/4520cfb2-073e-4148-b8bd-76ff1cf74140" />]

### 2. Functional Area Analysis
Plan vs execution and execution-rate comparison across functional budget areas.

![<img width="1156" height="651" alt="image" src="https://github.com/user-attachments/assets/88216992-868b-4718-92a1-8db2057cdba4" />]

### 3. 2024–2025 Change Analysis
Persistent under-execution and changes in relative deviation and execution rate.

![<img width="1158" height="653" alt="image" src="https://github.com/user-attachments/assets/cbd54a78-099d-4efe-862c-1dfdeeeb1056" />]

### 4. Evidence-Based Risk Analysis
Distribution of execution-risk evidence profiles and detailed evidence comparison.

![<img width="1152" height="651" alt="image" src="https://github.com/user-attachments/assets/166fe2e1-2a47-40cb-bf64-1ebc2a8e2add" />]

### 5. ML Anomaly Stability
Isolation Forest anomaly detection and stability across 10 random states.

![<img width="1156" height="653" alt="image" src="https://github.com/user-attachments/assets/18d99d94-eb2b-470b-ab6f-d0e7e062e623" />]

[file:///C:/Users/user/Desktop/Shirket_ucun/Layih%C9%99l%C9%99r/Layih%C9%99%202/power%20bi/Layih%C9%99%202.pdf]

## Project Links

- Kaggle Dataset: [https://www.kaggle.com/datasets/orxansuleymanov/azerbaijan-state-budget-ml-based-budget]
- Kaggle Notebook: [https://www.kaggle.com/code/orxansuleymanov/azerbaijan-state-budget]
- LinkedIn: [https://www.linkedin.com/posts/xiiidelta_case-study-azerbaijan-state-budget-analytics-activity-7512969072985333760-xlpB?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEnEo4cBum0enaGAuG6_VnioLhFaXT3jPjg]
- Upwork Portfolio: [https://www.upwork.com/freelancers/~01b5e3506436f6d4b1]
