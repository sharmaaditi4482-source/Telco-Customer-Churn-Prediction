# Customer Churn Prediction and Customer Segmentation System

## Project Introduction

Customer retention is a major concern for telecom companies, as losing existing customers can significantly affect revenue and long-term growth. This project focuses on predicting customer churn using Machine Learning techniques and grouping customers into meaningful segments through clustering.

The solution combines predictive analytics and customer segmentation to help businesses identify customers who are likely to leave and design targeted retention strategies.

### Key Components

* Exploratory Data Analysis (EDA)
* Data Cleaning and Preprocessing
* Customer Churn Prediction using Random Forest
* Model Optimization and Evaluation
* Customer Segmentation using K-Means Clustering

The project is built using the Telco Customer Churn dataset.

---

# Business Problem

Telecom customers may discontinue services for several reasons, including expensive plans, lack of support, contract-related issues, or dissatisfaction with services. Understanding these factors and identifying at-risk customers can help organizations take proactive actions before customers leave.

This project aims to:

* Predict whether a customer is likely to churn.
* Discover the key factors influencing churn behavior.
* Categorize customers into meaningful groups for business decision-making.

---

# Dataset Description

The dataset contains customer-related information such as:

### Demographic Information

* Gender
* Senior Citizen Status
* Partner
* Dependents

### Service Information

* Phone Service
* Internet Service
* Online Security
* Online Backup
* Device Protection
* Tech Support
* Streaming Services

### Billing Information

* Contract Type
* Payment Method
* Monthly Charges
* Total Charges

### Target Variable

**Churn Value**

* 1 → Customer Left the Company
* 0 → Customer Remained with the Company

---

# Tools and Technologies

The following technologies were used throughout the project:

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Google Colab

---

# Data Analysis and Preprocessing

Before model development, the dataset was explored to understand customer behavior and identify important patterns.

### Exploratory Data Analysis

Several analyses were performed, including:

* Customer tenure distribution
* Monthly charge trends
* Contract type comparison
* Payment method analysis
* Technical support impact on churn
* Correlation analysis of numerical features

### Data Cleaning

The **Total Charges** column contained missing values. These values were converted to numeric format and missing entries were replaced appropriately to maintain consistency.

### Feature Selection

Several columns with limited predictive value were removed, including location-based identifiers and other non-essential attributes, helping reduce noise within the dataset.

### Encoding

Categorical variables were transformed into numerical format using One-Hot Encoding to make the data suitable for machine learning algorithms.

---

# Churn Prediction Model

## Train-Test Split

The dataset was divided into:

* 80% Training Data
* 20% Testing Data

This ensures that model performance is evaluated on unseen data.

## Random Forest Classifier

Random Forest was selected because it:

* Handles complex datasets effectively.
* Reduces overfitting through ensemble learning.
* Supports both numerical and categorical features.
* Provides feature importance insights.
* Produces reliable classification performance.

### Random Forest Workflow

1. Multiple decision trees are generated.
2. Each tree is trained on a random subset of data.
3. Every tree makes an independent prediction.
4. Final prediction is determined through majority voting.

---

# Model Evaluation

The model was assessed using multiple performance metrics:

### Accuracy

Measures overall prediction correctness.

### Precision

Evaluates how many predicted churn cases were actually correct.

### Recall

Measures the model's ability to identify real churn customers.

### F1-Score

Provides a balance between Precision and Recall.

### Confusion Matrix

Used to analyze:

* True Positives
* True Negatives
* False Positives
* False Negatives

### ROC-AUC Analysis

ROC Curve and AUC Score were used to evaluate classification quality.

A higher AUC value indicates better separation between churn and non-churn customers.

---

# Model Optimization

Several techniques were applied to improve performance:

### Class Imbalance Handling

The parameter:

```python
class_weight='balanced'
```

was implemented to improve churn detection and reduce bias toward the majority class.

### Hyperparameter Tuning

Different combinations of:

* Number of Trees
* Maximum Tree Depth

were tested to improve model accuracy and generalization.

### Feature Importance Analysis

Feature rankings were generated to identify the most influential variables affecting customer churn.

### Cross Validation

A 5-Fold Cross Validation approach was used to ensure model stability and reduce the risk of overfitting.

---

# Customer Segmentation

In addition to churn prediction, customer segmentation was performed using K-Means Clustering.

## Features Used

* Tenure Months
* Monthly Charges
* Total Charges
* Predicted Churn Probability

### Feature Scaling

StandardScaler was applied before clustering because K-Means relies on distance-based calculations.

### Optimal Cluster Selection

The Elbow Method was used to determine the optimal number of clusters.

The best result was obtained with:

**K = 3**

---

# Customer Groups Identified

### Cluster 0 – Budget Loyal Customers

Characteristics:

* Lower monthly charges
* Long customer tenure
* Low churn risk

### Cluster 1 – High-Risk Customers

Characteristics:

* Relatively new customers
* High probability of churn
* Require immediate retention strategies

### Cluster 2 – Premium Loyal Customers

Characteristics:

* High spending behavior
* Long-term relationship with the company
* High business value

---

# Business Impact

The developed system can help telecom companies:

* Identify customers likely to churn.
* Improve customer retention initiatives.
* Design personalized marketing campaigns.
* Focus resources on high-risk customers.
* Increase customer lifetime value.

---

# Future Scope

Potential enhancements include:

* XGBoost and LightGBM implementation
* Interactive Streamlit Dashboard
* Flask-based Web Application
* Real-Time Prediction API
* Automated Customer Retention Recommendation System

# Conclusion

This project demonstrates how machine learning can be used to predict customer churn and segment customers based on behavioral patterns. By combining Random Forest Classification with K-Means Clustering, the system provides actionable insights that can support customer retention efforts and help telecom companies make data-driven business decisions.

