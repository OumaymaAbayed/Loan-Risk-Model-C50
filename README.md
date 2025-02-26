# Loan-Risk-Model-C50

## 📌 Project Overview
The 2007-2008 financial crisis highlighted the importance of **accurate risk assessment** in banking.  
This project builds a **machine learning model using C5.0 decision trees** to help banks **identify risky loans**.  

Banks often use automated credit scoring models to decide **loan approvals**.  
Our model aims to **predict loan defaults** based on applicant data, ensuring **fair and transparent lending decisions**.  

## 📂 Project Structure
- **data/** → Contains raw and processed datasets.  
- **scripts/** → R scripts for data processing, training, and evaluation.  
- **results/** → Model performance reports and visualizations.  

## 🗂️ Dataset
- **File:** `credit.csv`
- **Source:** Packt Publishing
- **Description:** Contains 1,000 loan applications with 21 (numeric and categorical) features.  
- **Target Variable:** `default` (indicates whether the loan was defaulted or not).  

## Steps to Build the Model
**📌 Step 1 – Data Collection**
We use credit.csv, which contains loan applicant data and loan default outcomes.
**📌 Step 2 – Data Exploration & Preprocessing**
Convert categorical variables into factors.
Handle missing values if necessary.
Randomly split data into 90% training and 10% testing sets.
**📌 Step 3 – Training the Decision Tree Model**
Train a C5.0 decision tree using the C50 package.
credit_model <- C5.0(credit_train[-last_col], credit_train$default)
summary(credit_model)
**📌 Step 4 – Evaluating Model Performance**
Use the confusion matrix to analyze misclassifications.
Predict on test data:
credit_pred <- predict(credit_model, credit_test)
**📌 Step 5 – Improving Model Performance**
Tune model hyperparameters for better accuracy.
Adjust decision tree cost-sensitive parameters to reduce financial losses.
**📊 Model Insights**
The checking account balance plays a key role in predicting loan defaults.
The model struggles to correctly classify high-risk applicants.
Fine-tuning the model can help reduce misclassification costs.

