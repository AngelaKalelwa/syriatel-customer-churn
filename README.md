# Syriatel Customer Churn Prediction

## Project Overview

This project aims to predict customer churn for Syriatel, a telecommunications company. The primary goal is to build a classification model that accurately identifies customers who are likely to churn, allowing the business to take proactive measures to retain them. The project follows a comprehensive data science process, including data cleaning, feature engineering, model building, and evaluation.

---

## Table of Contents

- [Syriatel Customer Churn Prediction](#syriatel-customer-churn-prediction)
  - [Project Overview](#project-overview)
  - [Table of Contents](#table-of-contents)
  - [Data Science Process](#data-science-process)
    - [1. Business Understanding](#1-business-understanding)
      - [Problem Statement](#problem-statement)
      - [Stakeholders](#stakeholders)
  - [Data Understanding](#data-understanding)
    - [2. Data Understanding](#2-data-understanding)
    - [3. Data Preparation](#3-data-preparation)
    - [4. Modeling](#4-modeling)
    - [5. Evaluation](#5-evaluation)
    - [6. Conclusion and Recommendations](#6-conclusion-and-recommendations)
      - [**Recommendations**:](#recommendations)
        - [Enhancing Customer Retention](#enhancing-customer-retention)
        - [Marketing and Personalization](#marketing-and-personalization)
        - [Operational Improvements](#operational-improvements)
        - [Monitoring and Evaluation](#monitoring-and-evaluation)
      - [Conclusion](#conclusion)
  - [Installation and Usage](#installation-and-usage)
    - [Clone the repository](#clone-the-repository)

---



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

#### Problem Statement
The goal is to predict customer churn to help Syriatel implement retention strategies. By identifying at-risk customers, the company can focus on improving customer satisfaction and loyalty, ultimately reducing churn rates.
**Objective**: Predict whether a customer will churn ("soon" stop doing business with SyriaTel).

#### Stakeholders
- **Primary Stakeholder**: SyriaTel, a telecommunications company interested in reducing customer churn and improving customer retention.
- **Secondary Stakeholders**:
  - **Customer Service Teams**: To develop strategies and interventions for retaining customers identified as high risk.
  - **Marketing Teams**: To create targeted campaigns and offers aimed at at-risk customers.
  - **Financial Analysts**: To evaluate the financial impact of customer churn and measure the effectiveness of retention strategies. 
  
## Data Understanding

### 2. Data Understanding

In this phase, we explored the dataset to identify key patterns and relationships. We also examined the distribution of features and checked for any missing or inconsistent data. Key insights from the data exploration phase included:

- `churn` is a highly imbalanced target variable.
- Some features exhibited multicollinearity, requiring reduction.

### 3. Data Preparation

Key steps in the data preparation phase included:

- **Addressing Missing Values**: Since there were no missing values in the dataset, no imputation was necessary.
- **Encoding Categorical Variables**: We used one-hot encoding to convert categorical variables (`international plan`, `voice mail plan`) into numerical format.
- **Multicollinearity Reduction**: Features that exhibited high multicollinearity were removed using VIF analysis, reducing the dataset from 17 columns to 12.
- **Feature Scaling**: Numerical features were scaled using `MinMaxScaler` to standardize the range.

- **Handling Imbalanced Data**: SMOTE was applied to balance the classes in the target variable.
- **Feature Selection**: Selecting a subset of relevant features (variables, predictors) for use in model construction.

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
- **Train-Test Split**: 70.0%- 30.0%
- **Logistic Regression**: Test accuracy of 87%, ROC-AUC of 0.8123
- **Decision Tree**: Test accuracy of 94%, ROC-AUC of 
0.8417
  
- **Conclusion**: The decision tree model showed better overall performance, especially in improving recall for the churn class. However, both models could be further refined, especially to address the recall issue for churn predictions.

### 6. Conclusion and Recommendations
####  **Recommendations**: 
- Based on the findings, Syriatel should focus on:
  
##### Enhancing Customer Retention

1. **Focus on At-Risk Customers**:
   - Focus retention efforts on customers predicted to churn. This could involve offering discounts,improved services, special offers,loyalty cards to those who are flagged as high churn risk by the model.
   - Create personalized retention campaigns for at-risk customers identified by the model, especially those who demonstrate early signs of dissatisfaction.
   - Use predictive models to identify customers with a high likelihood of churn.

2. **Improve Customer Service and Experience Quality**:
   -  Since customer service interactions are a top predictor of churn, improving this experience is critical. Ensure that customers' issues are resolved quickly and effectively to prevent dissatisfaction and churn.
   - The high correlation between customer service calls and churn suggests that improving customer service experiences could significantly reduce churn.
   - Invest in network infrastructure to reduce call drops or enhance data quality, improve customer support services, and offer better engagement through proactive support.

3. **Optimize Usage Patterns**:
   -  Analyze customer usage patterns and adjust service plans or pricing based on usage metrics which will increase engagement and retention by aligning services with customer needs and usage behaviors.

4. **Incentivize Long-Term Commitment**:
   - Introduce loyalty programs or long-term contracts that offer better rates or exclusive benefits to customers who commit for a longer duration.
   - Create attractive packages such as bundling services, offering premium features at a discount, or exclusive rewards for staying with Syriatel for an extended period.
  
5. **Identify and Strengthen Relationships with Loyal Customers**:
   - Use the model to identify loyal customers and deepen their engagement with personalized offers, such as upgrades to premium services or early access to new features.
   - Develop a loyalty-based segmentation strategy that rewards high-value and loyal customers with exclusive perks to keep them engaged and reduce potential churn.
   - Features like "Total Day Calls" indicate that customer engagement with the service can reduce churn. Therefore, increasing customer interaction with the product through promotions, loyalty rewards, or additional services can strengthen retention.
  
6. **Optimize Customer Onboarding**:
   - Ensure that new customers are fully supported during the onboarding process to reduce the risk of early churn. This includes providing clear instructions, tutorials, and access to customer support.
   - Introduce an automated onboarding system with tutorials, how-to guides, and personalized assistance to reduce confusion and boost customer satisfaction from the start.

##### Marketing and Personalization

1. **Design Targeted Marketing Campaigns**:
   - Develop marketing campaigns based on insights from the predictive models.
   - Tailor offers and promotions to specific customer segments, improving the effectiveness of marketing efforts and enhancing customer engagement.

2. **Leverage Customer Data**:
   - Utilize customer data insights to create personalized experiences.
   -  Increase customer satisfaction and loyalty by providing relevant and personalized interactions.

##### Operational Improvements

1. **Allocate Resources Efficiently**:
   - Use model predictions to guide resource allocation in customer service and support.
   - Optimize resource usage to address high-risk customers effectively and improve overall operational efficiency.

2. **Adjust Pricing Strategies**:
   - Analyze pricing structures based on customer usage and churn predictions.
   -  Develop pricing strategies that better align with customer value and usage patterns, potentially reducing churn and increasing revenue.\  
   - If payment-related features (e.g., late payments or prepaid balances) are linked to churn, improve flexibility in payment options or offer better reminders and support around payment deadlines.
   - Features related to specific plans, such as the "International Plan," suggest that pricing and plan features play a crucial role in customer retention. Offering more value in these plans, ensuring they meet customers' needs, or providing personalized plan recommendations could help reduce churn.
   - Implement easier payment plans, send payment reminders through SMS/email, and offer auto-debit options to prevent service disruption.
  

##### Monitoring and Evaluation

1. **Regularly Review Model Performance**:
   - Continuously monitor and evaluate the performance of predictive models.
   - **Goal**: Ensure models remain accurate and relevant, making adjustments as needed to maintain effectiveness.

2. **Update Strategies Based on New Insights**:
   - Incorporate new data and insights into business strategies.
   - Stay responsive to changing customer behaviors and market conditions, ensuring strategies remain effective and relevant.

#### Conclusion

Implementing these general recommendations can help the business improve customer retention, enhance marketing efforts, optimize operations, and make data-driven decisions. By leveraging predictive models and focusing on actionable insights, the business can achieve better outcomes and drive long-term success.





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
git clone <https://github.com/AngelaKalelwa/syriatel-customer-churn.git>
cd <syriatel-customer-churn>

This README provides a structured and comprehensive overview of your project, including installation instructions and the data science process involved. Let me know if you need further adjustments!
