# Model Card — Customer Churn Prediction

## Model Overview

| Property          | Value                   |
| ----------------- | ----------------------- |
| Model Name        | XGBoost Churn Predictor |
| Model Type        | Binary Classification   |
| Target            | churn_next_60d          |
| Prediction Window | 60 Days                 |
| Version           | 1.0                     |

## Intended Use

The model predicts whether a customer is likely to churn within the next 60 days. It is intended to support customer retention campaigns and prioritization of outreach efforts.

## Data Used

Features include:

* Customer demographics
* Purchase behavior
* Marketing engagement
* Website/app activity
* Support ticket history

Target variable:

* churn_next_60d

Only information available at or before the snapshot date was used.

## Model Approach

Models trained:

1. Logistic Regression (baseline)
2. XGBoost (final model)

The final model was selected based on ROC-AUC, PR-AUC, Recall, and F1-score.

## Performance

Populate from metrics.json after training:

| Metric    | Value |
| --------- | ----- |
| Accuracy  | TBD   |
| Precision | TBD   |
| Recall    | TBD   |
| F1-score  | TBD   |
| ROC-AUC   | TBD   |
| PR-AUC    | TBD   |

## Key Features

Typical important features:

* recency_days
* sessions_30d
* ticket_count_90d
* abandoned_carts_30d
* return_rate_180d

## Limitations

* Performance may decline as customer behavior changes.
* New customers have limited history.
* External events are not captured.
* Model does not incorporate sentiment analysis.

## Ethical Risks

Potential risks include:

* Incorrect customer targeting
* Unequal performance across customer segments
* Over-discounting customers unnecessarily

## Monitoring

Monitor:

* ROC-AUC
* Recall
* Data drift
* Feature drift
* False negative rate

Recommended retraining frequency: monthly or quarterly.

## When Not To Use

Do not use this model:

* For pricing decisions
* For service denial
* For automated irreversible actions
* During severe data quality issues
