# Credit Risk Assessment and Probability of Default Modeling

## Project Overview

This project analyzes retail credit risk using Python and builds a Probability of Default (PD) model. The objective is to simulate the work of a Risk Assessment Analyst by identifying borrower risk patterns, evaluating default drivers, and developing a simple credit risk model.

The project is based on the Home Credit Default Risk dataset.

## Business Objective

The main question of the project is:

**Can borrower characteristics be used to identify customers with a higher probability of repayment difficulty?**

The analysis focuses on:

* Portfolio default rate analysis
* Income-based risk segmentation
* Debt-to-income risk segmentation
* External credit score analysis
* Logistic Regression PD modeling
* Model performance interpretation

## Dataset

The dataset contains borrower-level information including income, credit amount, annuity amount, employment characteristics, regional risk indicators, and external credit scores.

Target variable:

* `TARGET = 0`: No repayment difficulty
* `TARGET = 1`: Repayment difficulty

The dataset is not included in this repository due to file size. It can be downloaded from the Home Credit Default Risk dataset source.

## Methodology

### 1. Portfolio Default Rate

The overall portfolio default rate was calculated as a baseline credit risk indicator.

Result:

* Non-default rate: 91.89%
* Default rate: 8.11%

This means approximately one out of every twelve borrowers experienced repayment difficulties.

### 2. Income Segmentation

Borrowers were divided into five income groups.

The results showed that default rates were relatively stable across most income groups, ranging between 8.15% and 8.65%. However, the highest-income group showed a lower default rate of 6.52%.

This suggests that higher income provides some protection against default, but income alone is not a strong discriminator of credit risk.

### 3. Debt-to-Income Segmentation

Debt-to-income ratio was calculated using annual annuity payments divided by total income.

Default rates generally increased as debt burden rose, with the fourth DTI quintile showing the highest default rate of 8.82%. However, the relationship was not strictly linear.

This indicates that DTI is a relevant risk factor, but it should be combined with other borrower characteristics in a multi-factor credit assessment framework.

### 4. External Credit Score Analysis

External credit score variables showed a strong relationship with default risk.

For `EXT_SOURCE_2`, borrowers in the lowest score group had a default rate of 15.30%, while borrowers in the highest score group had a default rate of 3.64%.

This confirms that external credit information is one of the strongest predictors of borrower repayment behavior.

### 5. Probability of Default Model

A Logistic Regression model was developed to estimate borrower Probability of Default.

Model features included:

* Income
* Credit amount
* Annuity amount
* External credit scores
* Regional risk rating

Model performance:

* AUC: 0.694
* Accuracy: 0.656
* Default recall: 0.61

The model achieved moderate discriminatory power and was able to identify approximately 61% of defaulting borrowers.

## Key Findings

* The portfolio default rate is 8.11%.
* Income alone has limited predictive power, except for the highest-income group.
* Debt burden is associated with higher default risk, but the relationship is not fully linear.
* External credit scores are the strongest observed risk indicators.
* Logistic Regression provides a useful baseline PD model for borrower risk classification.

## Risk Management Interpretation

The model can be used as an initial risk-screening tool to identify borrowers with elevated repayment risk. Although the model produces a relatively high number of false positives, this is acceptable in a risk management context where missing risky borrowers may be more costly than reviewing additional low-risk borrowers.

## Tools Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Logistic Regression
* Jupyter Notebook

## Project Status

Completed as a portfolio project for credit risk and risk assessment analyst roles.

Amir Alinaghi
