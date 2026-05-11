# Predicting Workplace Mental Health Treatment Using Machine Learning

## Project Overview
Mental health challenges in the technology industry often go underreported due to stigma, lack of support, and workplace culture barriers.

This project applies supervised machine learning to predict whether employees are likely to seek mental health treatment based on workplace, demographic, and organizational support factors.

Beyond prediction, the goal is to create organizational value by identifying actionable workplace risk indicators that employers can address through policy and wellness interventions.

## Business / Organizational Value
This project creates value for organizations by helping HR leaders, workplace wellness teams, and decision-makers better understand mental health risk patterns.

Potential applications include:

- identifying workplace environments associated with higher mental health strain
- improving employee wellness program targeting
- reducing absenteeism and productivity loss
- detecting organizational support gaps
- informing mental health policy decisions

Example organizational impact:

If a company can identify employees in environments strongly associated with untreated mental health struggles, interventions can be deployed earlier, improving employee wellbeing while reducing turnover and lost productivity.

---

## Problem Statement
Mental health treatment decisions are influenced by multiple factors:

- workplace benefits
- access to care resources
- perceived stigma
- manager support
- coworker openness
- family history
- work interference

The challenge is determining which of these factors most strongly influence treatment-seeking behavior and whether machine learning can reliably predict outcomes.

---

## Dataset
### Source
Open Sourcing Mental Illness (OSMI) Mental Health in Tech Survey

### Dataset Details
- 1,259 observations
- 27 features
- survey-based categorical + demographic data

### Target Variable
`treatment`

Prediction target:

> Whether an individual has sought treatment for a mental health condition.

---

## Machine Learning Framing (Rubric Alignment)
For this project:

- **Task (T):** Binary classification
- **Experience (E):** Historical survey observations
- **Performance Metric (P):**
  - Accuracy
  - F1 Score
  - Precision
  - Recall
  - ROC-AUC

This follows the formal ML definition:

P(T, E + ΔE) > P(T, E)

where model performance improves as additional experience (training data) is incorporated.

---

## Data Preparation
Preprocessing included:

### Cleaning
- removed irrelevant fields:
  - Timestamp
  - comments

- filtered invalid age values
- standardized inconsistent gender labels

### Feature Engineering
Created:
- Age buckets
- cleaned gender categories
- encoded categorical variables

---

## Exploratory Analysis
EDA was used to identify potential predictive factors.

Key observations:
- employees reporting frequent work interference had significantly higher treatment rates
- family history strongly increased treatment likelihood
- organizations with stronger mental health support options saw different treatment behavior
- stigma-related workplace concerns impacted help-seeking decisions

Visualizations included:
- treatment rate by workplace feature
- support system comparisons
- age distribution
- workplace stigma analysis

---

## Models Evaluated
### Scikit-Learn
- Logistic Regression
- Random Forest
- Gradient Boosted Trees

### Spark MLlib
To compare scalable implementations:

- Logistic Regression
- Random Forest
- Gradient Boosted Tree

---

## Results
| Model | Accuracy | F1 Score | ROC-AUC |
|------|----------|----------|---------|
| Spark Logistic Regression | 0.7914893617021277 |  0.7881655634052445 | 0.8470652173913044 |
| Spark Random Forest | 0.8042553191489362 | 0.8017502018741431 | 0.8467753623188405  |
| Spark Gradient Boosted Tree | 0.7957446808510639 | 0.7935183218600467 | 0.84481884057971  |

Best performing model:
**Random Forest**

Why:
Random forests captured nonlinear interactions between workplace factors better than linear approaches.

---

## Key Findings
Top predictive signals included:

- work interference
- family history
- access to care options
- wellness programs
- anonymity protections
- supervisor support

Interpretation:

This suggests organizational culture and support infrastructure significantly influence treatment behavior.

---

## Practical Recommendations
Based on findings, organizations should consider:

1. expanding accessible care options
2. improving mental health benefits visibility
3. increasing anonymity protections
4. training managers to reduce stigma
5. improving wellness program awareness

---

## Technologies Used
- Python
- Jupyter Notebook
- Polars
- Scikit-Learn
- Spark MLlib
- Matplotlib
- NumPy

---

## Repository Structure
```bash
mental-health-treatment-prediction/
│
├── Final_Project_2_67364.ipynb
├── README.md
├── requirements.txt
└── data/
