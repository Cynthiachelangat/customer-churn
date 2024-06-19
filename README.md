# Predicting Customer Churn in a Telecom Company

## Introduction
In today's competitive market, subscription-based businesses face significant challenges in retaining customers. Customer churn, or the rate at which customers discontinue their subscription services, is a critical metric for these businesses. A high churn rate can significantly impact revenue and growth, making it essential for companies to identify and mitigate factors leading to customer churn.

This project aims to develop a predictive model to identify customers who are likely to churn. By leveraging historical data on customer behavior, demographics, and interactions, we can build a machine learning model that accurately predicts churn. This enables the business to implement targeted retention strategies, enhancing customer satisfaction and loyalty while reducing the overall churn rate.

## Business Understanding
Subscription-based businesses rely heavily on recurring revenue from their customer base. Losing customers not only affects immediate revenue but also increases the cost of acquiring new customers. Therefore, understanding the factors that contribute to customer churn and being able to predict churn is crucial for sustaining long-term growth and profitability.

### Objective
The primary objective of this project is to predict customer churn for a subscription-based business. By identifying customers at risk of leaving, the business can take proactive measures to retain them, thereby reducing churn rates and improving customer retention.

### Key Questions
- Which customers are likely to churn?
- What are the key factors contributing to churn?
- How can the business reduce the churn rate?

## Data Understanding
The dataset contains customer information such as demographics, account details, and services used. The target variable is `Churn`, indicating whether a customer has left the service.

### Data Fields
- `customerID`: A unique identifier for each customer.
- `gender`: The gender of the customer (e.g., Male or Female).
- `SeniorCitizen`: Indicates whether the customer is a senior citizen (1 for Yes, 0 for No).
- `Partner`: Indicates whether the customer has a partner (True for Yes, False for No).
- `Dependents`: Indicates whether the customer has dependents (True for Yes, False for No).
- `tenure`: The number of months the customer has stayed with the company.
- `PhoneService`: Indicates whether the customer has a phone service (True for Yes, False for No).
- `MultipleLines`: Indicates whether the customer has multiple lines (Yes, No, or NaN if not applicable).
- `InternetService`: The type of internet service the customer has (e.g., DSL, Fiber optic, No).
- `OnlineSecurity`: Indicates whether the customer has online security service (Yes, No, or NaN if not applicable).
- `OnlineBackup`: Indicates whether the customer has online backup service (Yes, No, or NaN if not applicable).
- `DeviceProtection`: Indicates whether the customer has device protection service (Yes, No, or NaN if not applicable).
- `TechSupport`: Indicates whether the customer has tech support service (Yes, No, or NaN if not applicable).
- `StreamingTV`: Indicates whether the customer has streaming TV service (Yes, No, or NaN if not applicable).
- `StreamingMovies`: Indicates whether the customer has streaming movies service (Yes, No, or NaN if not applicable).
- `Contract`: The type of contract the customer has (e.g., Month-to-month, One year, Two year).
- `PaperlessBilling`: Indicates whether the customer is enrolled in paperless billing (True for Yes, False for No).
- `PaymentMethod`: The payment method used by the customer (e.g., Electronic check, Mailed check, Bank transfer, Credit card).
- `MonthlyCharges`: The amount charged to the customer monthly.
- `TotalCharges`: The total amount charged to the customer.
- `Churn`: Indicates whether the customer has churned (left the company) (Yes or No).

### Churn Rates by Contract Type
- Month-to-month Contracts: Customers with month-to-month contracts have the highest churn rate (17.60%). This indicates that these customers are more likely to leave compared to those with longer contract durations.
- One-year Contracts: The churn rate for one-year contracts is significantly lower at 5.02%. This suggests that customers with a one-year commitment are less likely to churn.
- Two-year Contracts: The churn rate is the lowest for two-year contracts at 1.61%. This implies that customers who commit to a two-year contract are the least likely to churn.

## Preprocessing
- Missing values were handled by imputing with mean/mode values.
- Categorical variables were encoded using Label Encoding.
- Numerical features were scaled using StandardScaler.

## Modeling
We experimented with the following models:
- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier

The Random Forest Classifier performed the best based on precision.

## Feature Importance
The top features contributing to the prediction of churn were:
- `Contract`
- `TotalCharges`
- `MonthlyCharges`
- `InternetService`

## Final Model
The final model is a Random Forest Classifier with the following hyperparameters:
- `n_estimators`: 100
- `max_depth`: 10
- `min_samples_split`: 5
- `min_samples_leaf`: 2
- `max_features`: 'sqrt'

The model achieved a precision of 0.7059 on the test set.


