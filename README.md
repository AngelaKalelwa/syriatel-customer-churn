# Syriatel Customer Churn Prediction

## Project Overview

This project aims to predict customer churn for Syriatel, a telecommunications company. The primary goal is to build a classification model that accurately identifies customers who are likely to churn, allowing the business to take proactive measures to retain them. The project follows a comprehensive data science process, including data cleaning, feature engineering, model building, and evaluation.

---

## Table of Contents

- [Syriatel Customer Churn Prediction](#syriatel-customer-churn-prediction)
  - [Project Overview](#project-overview)
  - [Table of Contents](#table-of-contents)
  - [Dataset Information](#dataset-information)
  - [Data Science Process](#data-science-process)
    - [1. Business Understanding](#1-business-understanding)
    - [2. Data Understanding](#2-data-understanding)
    - [3. Data Preparation](#3-data-preparation)
    - [4. Modeling](#4-modeling)
    - [5. Evaluation](#5-evaluation)
    - [6. Conclusion and Recommendations](#6-conclusion-and-recommendations)
  - [Installation and Usage](#installation-and-usage)
    - [Clone the repository](#clone-the-repository)

---

## Dataset Information

The dataset used in this project contains customer information related to churn. Below are the features included in the dataset:

- `state`: The U.S. state in which the customer resides.
- `account length`: The number of days the customer has had an account with Syriatel.
- `area code`: The area code of the customer.
- `phone number`: The customer's phone number (this will be dropped from the dataset).
- `international plan`: Whether the customer has an international plan (binary).
- `voice mail plan`: Whether the customer has a voice mail plan (binary).
- Various usage metrics (e.g., `total day minutes`, `total eve calls`, etc.).
- `customer service calls`: Number of customer service calls made by the customer.
- `churn`: The target variable (whether the customer churned or not).

---

## Data Science Process

### 1. Business Understanding

**Problem Statement:**
The goal is to predict customer churn to help Syriatel implement retention strategies. By identifying at-risk customers, the company can focus on improving customer satisfaction and loyalty, ultimately reducing churn rates.

### 2. Data Understanding

In this phase, we explored the dataset to identify key patterns and relationships. We also examined the distribution of features and checked for any missing or inconsistent data. Key insights from the data exploration phase included:

- `churn` is a highly imbalanced target variable.
- Some features exhibited multicollinearity, requiring reduction.

### 3. Data Preparation

Key steps in the data preparation phase included:

- **Addressing Missing Values**: Since there were no missing values in the dataset, no imputation was necessary.
- **Encoding Categorical Variables**: We used one-hot encoding to convert categorical variables (`international plan`, `voice mail plan`) into numerical format.
- **Feature Scaling**: Numerical features were scaled using `MinMaxScaler` to standardize the range.
- **Multicollinearity Reduction**: Features that exhibited high multicollinearity were removed using VIF analysis, reducing the dataset from 17 columns to 8.
- **Handling Imbalanced Data**: SMOTE was applied to balance the classes in the target variable.

### 4. Modeling

Two models were built and evaluated:

- **Logistic Regression**:
  - Baseline and tuned models were built.
  - The model performed well for the "non-churn" class but struggled with recall for the "churn" class.
  
- **Decision Tree Classifier**:
  - Baseline and tuned models were built.
  - The tuned model achieved better performance overall, particularly in improving recall for the "churn" class.

### 5. Evaluation

Both models were evaluated using the following metrics:

- **Accuracy**: The percentage of correct predictions made by the model.
- **Precision**: The proportion of true positive predictions relative to the total number of positive predictions.
- **Recall**: The proportion of true positive predictions relative to the total number of actual positives.
- **F1-Score**: The harmonic mean of precision and recall.
- **ROC-AUC**: The area under the Receiver Operating Characteristic curve, measuring the model's ability to discriminate between classes.

Key results:
- **Logistic Regression**: Test accuracy of 86.2%, ROC-AUC of 0.68.
- **Decision Tree**: Test accuracy of 87.1%, ROC-AUC of 0.75.

### 6. Conclusion and Recommendations

- **Conclusion**: The decision tree model showed better overall performance, especially in improving recall for the churn class. However, both models could be further refined, especially to address the recall issue for churn predictions.
- **Recommendations**: Based on the findings, Syriatel should focus on improving customer service and implementing targeted retention strategies for customers who have a higher risk of churn. This can be done by analyzing specific usage patterns and offering personalized offers to at-risk customers.

---

## Installation and Usage
pip install pandas numpy matplotlib seaborn scikit-learn imblearn
Dependencies
The project uses the following libraries:
pandas
numpy
matplotlib
seaborn
scikit-learn
imblearn


### Clone the repository

```bash
git clone <repo_link>
cd <repo_directory>

This README provides a structured and comprehensive overview of your project, including installation instructions and the data science process involved. Let me know if you need further adjustments!
