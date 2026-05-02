# Credit risk scoring

## Dataset Overview

**Source:** The dataset is derived from the **'[Give Me Some Credit](https://www.kaggle.com/competitions/GiveMeSomeCredit/overview)'** competition on Kaggle. It is designed to solve the problem of credit scoring by predicting the probability that somebody will experience financial distress in the next two years.



**Feature Dictionary:**
1.  **SeriousDlqin2yrs (Target):** Person experienced 90 days past due delinquency or worse.
2.  **RevolvingUtilizationOfUnsecuredLines:** Total balance on credit cards and personal lines of credit divided by the sum of credit limits.
3.  **age:** Age of borrower in years.
4.  **NumberOfTime30-59DaysPastDueNotWorse:** Number of times borrower has been 30-59 days past due but no worse in the last 2 years.
5.  **DebtRatio:** Monthly debt payments, alimony, living costs divided by monthy gross income.
6.  **MonthlyIncome:** Monthly income.
7.  **NumberOfOpenCreditLinesAndLoans:** Number of Open loans (installment like car loan or mortgage) and Lines of credit (e.g. credit cards).
8.  **NumberOfTimes90DaysLate:** Number of times borrower has been 90 days or more past due.
9.  **NumberRealEstateLoansOrLines:** Number of mortgage and real estate loans including home equity lines of credit.
10. **NumberOfTime60-89DaysPastDueNotWorse:** Number of times borrower has been 60-89 days past due but no worse in the last 2 years.
11. **NumberOfDependents:** Number of dependents in family excluding themselves.

## Requirements

To run this project, you need a Python 3.8+ environment with the following libraries installed:

### Core Libraries
* **pandas:** Data manipulation and analysis.
* **numpy:** Support for large, multi-dimensional arrays and matrices.
* **matplotlib:** Comprehensive library for creating static, animated, and interactive visualizations.
* **seaborn:** Statistical data visualization based on matplotlib.

### Machine Learning (scikit-learn)
* `train_test_split`: For splitting data into training and test sets.
* `StandardScaler`: For feature scaling.
* `LogisticRegression`: Linear model for classification.
* `RandomForestClassifier`: Ensemble learning method for classification.
* `metrics`: To calculate ROC-AUC score, classification reports, and confusion matrices.

### Installation
You can install the required dependencies using pip:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Business Understanding

Credit risk assessment is a critical process in financial institutions, where the goal is to determine the likelihood that a borrower will default on a loan.

Incorrect predictions can have significant consequences:
- False negatives (classifying a risky client as safe) may lead to direct financial losses
- False positives (classifying a safe client as risky) may result in lost business opportunities

In this context, minimizing risk is more important than maximizing overall accuracy. Therefore, special attention is given to evaluation metrics such as recall, which measures the model's ability to correctly identify high-risk clients.

### Insight

The distribution of the target variable shows that the dataset is imbalanced, with significantly fewer default cases compared to non-default cases.

This imbalance can affect model performance, as models may become biased toward predicting the majority class. Therefore, evaluation metrics beyond accuracy are required.

### Interpretation

The visualization indicates a clear relationship between financial indicators and default risk.

Customers with higher debt ratios and lower income levels tend to have a higher probability of default. This aligns with financial intuition and confirms that the dataset captures meaningful risk patterns.

## Model Evaluation

In credit risk modeling, accuracy alone is not sufficient to evaluate model performance.

A key focus is placed on recall, as it reflects the model's ability to correctly identify high-risk clients. Missing such clients (false negatives) can result in significant financial losses.

The ROC-AUC metric is also used to assess the model's ability to distinguish between risky and non-risky customers across different thresholds.

## Model Comparison

The comparison of models shows that ensemble methods such as Random Forest generally outperform linear models in terms of predictive power.

However, Logistic Regression remains valuable due to its interpretability, which is particularly important in financial environments where model transparency is required.

Overall, Random Forest provides better performance, while Logistic Regression offers easier explanation of predictions.

| Model | ROC-AUC |
|------|--------|
| Logistic Regression | ~0.75 |
| Random Forest | ~0.82 |

## Feature Importance

The model identifies key financial indicators such as DebtRatio and MonthlyIncome as strong predictors of default risk.

This is consistent with real-world financial logic, where individuals with higher debt burdens and lower income are more likely to experience financial difficulties.

Understanding feature importance improves trust in the model and supports its use in real-world decision-making.

## Model Validation

Cross-validation was used to ensure that the model generalizes well to unseen data.

This technique reduces the risk of overfitting and provides a more reliable estimate of model performance across different subsets of the dataset.

## Previous Research

Previous studies in credit risk modeling show that machine learning methods, particularly ensemble models such as Random Forest and Gradient Boosting, often outperform traditional statistical approaches.

However, Logistic Regression continues to be widely used in financial institutions due to its interpretability and regulatory acceptance.

These findings are consistent with the results observed in this project.

## Conclusion

In this project, machine learning models were developed to predict the probability of loan default based on financial and demographic data.

The results show that ensemble models such as Random Forest achieve strong predictive performance, particularly in identifying high-risk clients.

From a business perspective, such models can support financial institutions in making better lending decisions, reducing default risk, and improving overall risk management strategies.

By integrating predictive analytics into decision-making processes, organizations can enhance both efficiency and financial stability.



