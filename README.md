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
I used credit.csv, which contained 1,000 observations and 21 features, combining factor and integer data types.

Since the loan data was obtained from Germany, the currency is recorded in Deutsche Marks (DM).

**📌 Step 2 – Data Exploration & Preprocessing**

1- Observe:

The `default` variable indicates whether the loan applicant could not meet the agreed payment terms and went into default. A total of 30 percent of the loans went into default.

A high default rate is not desirable for a bank as it would mean the bank is less likely to get back its investment. 

2- Reorder the data since it was sorted in the `credit.csv`

3- Randomly split data into 90% training and 10% testing sets.

**📌 Step 3 – Training the Decision Tree Model**
Train a decision tree using the C5.0() function in the C50 package.

The model had a 14.1% error rate. Decision trees tend to overfit the model to the training data. For this reason, the error rate on training data can be overly optimistic, and it is especially important to test decision trees on a test dataset

**📌 Step 4 – Evaluating Model Performance**
Evaluate the model performance using the CrossTable() function in the gmodels package to compare the actual default with the predicted default.

The results obtained were somewhat worse than its performance on the training data, with an accuracy rate of just 75%

**📌 Step 5 – Improving Model Performance**
1- Boost the accuracy of decision trees by tuning the parameter `trails` to 10 in the c5.0() function.

The classifier made 30 mistakes on 900 training examples for an error rate of 3%. This is quite an improvement over the 14.1% training error rate we noted before adding boosting.
Similarly, the error rate in the test data decreased from 25% to 21% in the boosted model.
2- Assign a penalty to each error to reduce False Negatives:
This version unfortunately makes more mistakes overall: 35%. However, the types of mistakes vary dramatically.  This trade resulting in a reduction of false negatives at the expense of increasing false positives may be acceptable if our cost estimates were accurate.

**📊 Model Insights**
The model struggles to correctly classify high-risk applicants.
Fine-tuning the model can help reduce misclassification costs.

