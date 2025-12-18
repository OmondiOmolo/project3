## Telecom Customer Churn Prediction Project

**Overview**

Customer churn is a major challenge for telecom companies. Retaining customers is significantly cheaper than acquiring new ones, and predicting churn allows SyriaTel to proactively intervene with targeted retention strategies. This project builds and evaluates machine learning models to identify customers most at risk of leaving, translating technical results into actionable business recommendations.

**Business and Data Understanding**

**Business Context:**

SyriaTel experiences customer churn that impacts revenue and growth.

The goal is to predict churn risk so the company can reduce losses and improve loyalty.

**Stakeholder Audience:**

Business managers who are the decision makers: Need clear, actionable insights (e.g., which customers to target).

Customer support teams: Want to know which customers are at risk so they can prioritize outreach.

Executives: Care about overall churn reduction, cost savings, and customer satisfaction.

**Dataset Choice:**

Source: SyriaTel Customer Churn historical customer records of about 3,300 rows.

Features: Customer demographics, service plans (international/voicemail), usage patterns (day, evening, night, international minutes & calls), and customer service interactions.

Target variable: Churn (binary: stayed vs left).

Class balance: 85% stayed, 15% churned. It is an imbalanced dataset.

**Modeling**

Logistic Regression: A simple and interpretable model to establish a benchmark/baseline.

Decision Tree (untuned): Captures non-linear patterns and feature interactions.

Tuned Decision Tree: Adjusted hyperparameters to improve generalization and interpretability.

**Data Preparation:**

Dropped irrelevant identifiers and redundant features to avoid overfitting and overusing computational resources.

Train/test split the data before fitting the model.

Encoded categorical variables i.e. through one-hot encoding.

Scaled numeric features to ensure fair treatment across models.

## Evaluation

**Metrics Used:**

Recall: % of churners correctly identified.

Precision: % of flagged customers who are actual churners.

F1: Balance between recall and precision.

ROC-AUC: Overall ability to separate churn vs non-churn across thresholds.

## Results:

Logistic Regression: Recall 0.74, Precision 0.35, ROC-AUC 0.82.

Decision Tree (untuned): Recall 0.65, Precision 0.63, ROC-AUC 0.79.

Tuned Decision Tree: Recall 0.75, Precision 0.68, ROC-AUC 0.84.

**Interpretation:**

Logistic Regression provided a strong baseline but flagged too many false positives.

Untuned Decision Tree improved precision but underperformed in recall.

Tuned Decision Tree achieved the best balance: catches 3 of 4 churners, 7 of 10 flagged are true churners.

## Conclusion

**Recommendations:**

Offer loyalty bundles to international plan users.

Improve support for customers with repeat service calls.

Proactively recommend plans for heavy day users.

**Limitations:**

Historical snapshot only; churn drivers may change.

Model misses around 25% of churners (false negatives).

Around 30% of flagged customers won’t churn (false positives).

In conclusion the tuned Decision Tree provides a practical, interpretable solution that balances recall and precision. By focusing retention campaigns on high-risk customers, SyriaTel can reduce churn, save costs, and improve customer loyalty.