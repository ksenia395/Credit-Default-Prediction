# Credit-Default-Prediction

## Quick Links
- **Dataset:** [UCI Default of Credit Card Clients](default_of_credit_card_clients.xls)
- **Notebook:** [Google Colab Notebook](https://colab.research.google.com/drive/1acxDTzA2du-sVJ2HfCQw2Yw2F9tV7btu?authuser=1&hl=en#scrollTo=Pbe0GfHL1J5j...)
This project uses the UCI Default of Credit Card Clients dataset. It contains information about 30,000 clients, including credit limit, demographic variables, repayment status, bill amounts, and payment history. The target variable is default payment next month.
Problem Statement

Credit default prediction is an important business problem because banks need to identify risky clients in advance. The goal of this project is to predict whether a credit card client will default next month based on financial and customer information. This is a binary classification task with two classes: default or no default. The main challenge is not only to achieve good overall accuracy, but also to detect as many risky clients as possible.

Dataset

This project uses the UCI Default of Credit Card Clients dataset. It contains information about 30,000 clients, including credit limit, demographic variables, repayment status, bill amounts, and payment history. The target variable is default payment next month.

Project Workflow

The project was completed in the following steps:

data loading and quick data check
exploratory data analysis (EDA)
baseline Logistic Regression
class imbalance handling with balanced Logistic Regression
threshold experiment
model comparison with Random Forest and Gradient Boosting
Exploratory Data Analysis

The dataset had no missing values. The target was imbalanced, with more non-default cases than default cases. EDA showed that repayment status variables and bill amount variables were strongly related to each other. Credit limit also showed visible differences between default and non-default clients.

Models

I tested the following models:

Logistic Regression
Balanced Logistic Regression
Random Forest
Gradient Boosting
Results
Model	Accuracy	ROC-AUC	Precision	Recall	F1-score
Logistic Regression	0.808	0.708	0.687	0.240	0.355
Balanced Logistic Regression	0.680	0.708	0.367	0.620	0.461
Random Forest	0.812	0.754	0.631	0.365	0.462
Gradient Boosting	0.820	0.780	0.669	0.364	0.471

Gradient Boosting showed the best overall performance based on ROC-AUC, accuracy, and F1-score. Balanced Logistic Regression had the highest recall, which means it detected more risky clients. This shows the trade-off between overall model quality and the ability to catch default cases.

Threshold Experiment

I also tested different decision thresholds for the balanced Logistic Regression model. Lower thresholds increased recall, but they also reduced precision, accuracy, and F1-score. A very low threshold such as 0.3 was too aggressive because it created too many false positives. For the final comparison between models, I kept the standard threshold of 0.5.

Final Conclusion

This project showed that credit default prediction is not only about accuracy. A simple Logistic Regression model gave a useful baseline, while balanced Logistic Regression improved recall for risky clients. Among the tested models, Gradient Boosting gave the best overall result. At the same time, the final choice depends on the business goal: better overall balance or better detection of risky clients.

Repository Structure
credit-default-prediction/
│
├── data/
│   └── default_of_credit_card_clients.xls
├── notebooks/
│   └── credit_default_prediction.ipynb
├── images/
│   ├── target_distribution.png
│   ├── boxplot_limit_bal.png
│   ├── correlation_matrix.png
│   └── model_comparison.png
├── README.md
└── requirements.txt
Tools and Libraries

Main tools and libraries used in this project:

Python
pandas
matplotlib
seaborn
scikit-learn
