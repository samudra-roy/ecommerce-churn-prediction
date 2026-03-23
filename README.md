📊 Customer Churn Prediction & Business Optimization
🚀 Project Overview

This project focuses on predicting customer churn using machine learning and translating predictions into business decisions.

Instead of just building a model, we go one step further:
👉 Optimize who to target based on business value (profit vs cost).

🎯 Problem Statement

Telecom companies lose revenue when customers churn.

Goal:

Predict which customers are likely to churn
Take action to retain them
Maximize net profit from retention campaigns
📂 Dataset
Source: IBM Telco Customer Churn dataset
Contains:
Customer demographics
Subscription details
Charges & tenure
Target: Churn (Yes/No)
⚙️ Project Workflow
1. Data Loading
Loaded dataset directly from GitHub using pandas
2. Data Cleaning
Removed irrelevant column: customerID
Converted TotalCharges to numeric
Handled missing values
3. Feature Engineering

Created new features:

charges_per_month_ratio → spending behavior
is_new_customer → early churn indicator
4. Encoding
Applied one-hot encoding to categorical variables
5. Train-Test Split
80% training / 20% testing
Used random_state=42 for reproducibility
🤖 Model Used
Random Forest Classifier

Why?

Handles non-linear patterns well
Works well with tabular data
Minimal preprocessing required
📈 Evaluation Metrics
Classification Report (Precision, Recall, F1-score)
Confusion Matrix
💡 Business Logic (Most Important Part 🚨)

Instead of stopping at predictions, we simulate real-world decisions:

Assumptions:
💰 Profit per retained customer = ₹2000
💸 Cost per wrong targeting = ₹100
🧠 Threshold Optimization

We don’t blindly use default threshold (0.5).

We test multiple thresholds (0.1 → 0.9) to answer:

👉 “Which customers should we target given limited resources?”

Key Metrics:
Caught churners → true positives
False alarms → unnecessary cost
Total flagged users → workload
Net value → profit - cost
🧪 Custom Function
def churn_report(threshold, capacity=None):

This function:

Applies threshold
Calculates confusion matrix
Computes business value
Checks if within team capacity
📊 Example Insight
Lower threshold → more customers targeted → higher cost
Higher threshold → fewer customers → may miss churners

👉 Optimal threshold balances:

Profit
Cost
Operational capacity
🏆 Key Takeaways
ML is not just about accuracy
Business impact matters more than model score
Threshold tuning is critical in real-world systems
Data science = prediction + decision-making
🛠️ Tech Stack
Python
Pandas
Scikit-learn
