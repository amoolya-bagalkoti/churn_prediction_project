# churn_prediction_project

Problem Setting

Objective: Identify customers likely to churn and develop strategies to retain them.

Challenge: Requires understanding large datasets and determining important features affecting churn.

Problem Definition

Industry: Telecom.

Approach: Binary classification to predict churn based on customer attributes (e.g., demographics, behavioral, transactional data).

Data Source and Description
 
Source: Kaggle dataset Telco Customer Churn.

Size: 7043 records, 21 attributes, and 1 target variable (“Churn”).

Key Attributes: Demographics (e.g., gender, senior citizen), services (e.g., internet, streaming), billing (e.g., contract type, payment method), and tenure.

 Data Cleaning
 
Unique Identifier: Removed “CustomerID.”

Null Handling: Dropped rows with nulls in “TotalCharges” (0.15% of data).

Data Type Conversion: Converted “TotalCharges” to numeric.

Data Exploration and Visualization

Imbalance: Dataset has a 73:27 ratio of non-churn to churn cases.

Correlations: Heatmap revealed weak correlations for some variables (e.g., gender, phone service) but trends were observed:

Higher churn rates: Customers with month-to-month contracts, electronic check payments, no online security, or fiber optic internet.

Loyal customers: Those with long tenure, higher total charges, and one/two-year contracts.

Impactful Factors: Internet service, contract type, payment method, paperless billing, and tenure.

Data Preprocessing

Encoding:

Label encoding for binary variables (e.g., Partner, Dependents).

One-hot encoding for nominal categorical variables.

Feature Selection: Used mutual_info_score to drop less impactful columns (e.g., gender, multiple lines).

Standardization: Scaled numeric features to maintain consistency.

Imbalance Handling: Addressed using techniques such as SMOTE or class weights.

Exploration of Machine Learning Models
1.	Logistic Regression:
•	Strengths: Robust to noise, interpretable.
•	Limitations: Assumes linear relationships; biased on imbalanced data.

2.	Support Vector Machines (SVM):
•	Strengths: Effective for high-dimensional data; handles noise.
•	Challenges: Computationally expensive for large datasets.

3.	Random Forest:
•	Strengths: Reduces overfitting; captures feature importance.
•	Challenges: High dimensionality impacts performance.

4.	K-Nearest Neighbors (KNN):
•	Strengths: Simple; non-parametric.
•	Limitations: Sensitive to noise and class imbalance.

5.	Decision Tree:
•	Strengths: Captures non-linear relationships; interpretable.
•	Challenges: Prone to overfitting.

 Implementation and Results
 
Feature Selection: 14 predictors retained after EDA and mutual information analysis.

Performance Metrics:

Logistic Regression: Accuracy ~79%.

Random Forest, SVM, and other models’ performance can be finalized by comparing precision, recall, F1-score, and AUC-ROC.

 
