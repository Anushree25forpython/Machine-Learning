# 📊 Customer Churn Prediction using Machine Learning

## 🚀 Project Overview

This project aims to predict customer churn in a telecom dataset using machine learning models. 
The objective is to identify customers likely to leave the service, enabling proactive retention strategies.

---

## 📂 Dataset

* Telecom Customer Churn Dataset
* Total records: **3333 customers**
* Target variable: **Churn (Yes/No)**

### ⚠️ Key Challenge

* The dataset is **imbalanced**, with significantly fewer churners than non-churners.

---

## 🔍 Exploratory Data Analysis (EDA)

### Key Observations:

* Continuous features like *Day Minutes* and *Evening Minutes* show relatively symmetric distributions.
* *Customer Service Calls* is slightly skewed and strongly associated with churn.
* *International Plan* (binary feature) shows a clear relationship with churn behavior.
* Features such as *Day_Mins* and *Day_Charge* are highly correlated (redundant).

---

## ⚙️ Data Preprocessing

* Converted categorical variables into numeric format
* Removed irrelevant features:

  * `Phone` (unique identifier)
  * `State` (high cardinality)
* Feature engineering applied
* Maintained consistent feature set across models for fair comparison

---

## 🤖 Models Used

* Logistic Regression
* Decision Tree
* Support Vector Machine (SVM)
* Random Forest
* XGBoost

---

## 🔧 Model Improvement Strategy

* Addressed **class imbalance**
* Performed **hyperparameter tuning** using RandomizedSearchCV
* Focused on **F1-score** instead of accuracy
* Controlled overfitting using parameter constraints

---

## 📊 Final Model Comparison

| Model    | Accuracy | Precision | Recall | F1 Score |
| XGBOOST  |   0.96   |   0.87    |  0.84  |   0.85   |
| RFC      |   0.96   |   0.87    |  0.82  |   0.85   |
