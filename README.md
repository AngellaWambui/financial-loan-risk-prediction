<img src="banner.jpg.jpg" style="width:100%; height:200px; object-fit:cover;">

# FinTech Innovations — Automated Loan Approval Risk Model
## Predicting Loan Default Using Machine Learning Pipelines
### CRISP-DM Framework | Risk Analytics Team

---

## Overview (BLUF — Bottom Line Up Front)

This project developed a machine learning solution to support loan approval decisions at FinTech Innovations using the CRISP-DM methodology. Four classification algorithms — Logistic Regression, Decision Tree, Random Forest, and Gradient Boosting  were trained and compared using standardized preprocessing pipelines.

**Logistic Regression achieved the best overall performance:**
- Accuracy: **95.93%** | F1-Score: **91.94%** | ROC-AUC: **99.46%**

From a business perspective, the model reduces inconsistency in manual loan decisions. Given the asymmetric error costs ($50,000 per false approval vs $8,000 per false denial), the model was also evaluated using a **custom business cost metric** that translates prediction errors directly into dollar impact — a more actionable measure for stakeholders than accuracy alone.
---
## Business Understanding

FinTech Innovations is modernising its manual loan approval process, which suffers from inconsistency, slow turnaround, and scalability issues. The objective is to build a reliable classification model that supports loan officers with data-driven approval decisions.

### Stakeholder Analysis

| Stakeholder | Need | Business Value |
|---|---|---|
| Loan Officers | Faster, consistent decisions | Reduces manual workload |
| Risk Management | Minimise loan defaults | Identifies high-risk applicants |
| Senior Management | Improve profitability | Data-driven portfolio performance |
| Loan Applicants | Fair and timely decisions | Consistent, unbiased evaluation |

### Business Impact of Prediction Errors

| Error Type | Description | Estimated Cost |
|---|---|---|
| **False Positive** (approve bad loan) | High-risk applicant approved, defaults | **$50,000** |
| **False Negative** (deny good loan) | Creditworthy applicant rejected, lost revenue | **$8,000** |

A false approval costs **6.25× more** than a false denial. This asymmetry directly drives our metric selection and threshold decisions.

### Classification vs. Regression

We use **binary classification** because `LoanApproved` is a binary target (0/1). Classification directly maps to approve/deny decisions and probability outputs give loan officers a nuanced risk score.

### Evaluation Metrics & Success Criteria

| Metric | Rationale | Target |
|---|---|---|
| **Custom Business Cost** | `FP×$50K + FN×$8K` — direct dollar impact | Minimise |
| **ROC-AUC** | Threshold-agnostic discrimination | ≥ 0.90 |
| **F1-Score** | Balances precision & recall on imbalanced data | ≥ 0.85 |
| **Recall** | Of all bad loans, how many did we catch? | ≥ 0.85 |
| **Accuracy** | Overall correctness (secondary due to imbalance) | ≥ 0.90 |
