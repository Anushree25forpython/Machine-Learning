# 📊 Customer Churn Prediction باستخدام Machine Learning

## 🚀 Project Overview

This project focuses on predicting customer churn using supervised machine learning techniques. The goal is to identify customers who are likely to leave a telecom service, enabling proactive retention strategies.

---

## 📂 Dataset

* Source: Telecom Customer Churn Dataset
* Total Records: **3333 customers**
* Target Variable: **Churn (Yes/No)**

### ⚠️ Key Observation

* The dataset is **imbalanced**:

  * Non-churners: 2850
  * Churners: 483

---

## 🔍 Exploratory Data Analysis (EDA)

Key insights:

* Customers with **higher customer service calls** are more likely to churn
* **Day usage (minutes & charges)** strongly influences churn
* Features like **Account Length** and **Vmail Plan** show minimal impact
* Some features are **highly correlated** (e.g., Minutes vs Charges)

---

## ⚙️ Data Preprocessing

* Converted categorical variables to numeric:

  * `Churn`, `Intl_Plan`, `Vmail_Plan`
* Applied **One-Hot Encoding** for `State`
* Feature Engineering:

  * Created `Avg_Night_Calls`
* Dropped irrelevant columns:

  * `State`, `Area_Code`, `Phone`
* Applied **StandardScaler** for normalization

---

## 🤖 Models Implemented

| Model                | Accuracy | Precision | Recall | F1 Score |
| -------------------- | -------- | --------- | ------ | -------- |
| Logistic Regression  | 0.85     | 0.59      | 0.19   | 0.28     |
| Decision Tree        | 0.86     | 0.61      | 0.19   | 0.29     |
| SVM                  | 0.86     | 0.61      | 0.19   | 0.29     |
| Random Forest (Base) | High     | Low       | Low    | Poor     |

### ⚠️ Problem Identified

* High accuracy but **low recall & F1-score**
* Caused by:

  * Class imbalance
  * Overfitting

---

## 🔧 Model Improvement

### Hyperparameter Tuning

Used **RandomizedSearchCV** to optimize:

* `max_depth`
* `max_features`
* `criterion`
* `bootstrap`

### Final Model Configuration

```python
RandomForestClassifier(
    n_estimators=200,
    criterion='entropy',
    max_depth=10,
    max_features=6,
    min_samples_split=10,
    min_samples_leaf=5,
    bootstrap=True,
    class_weight='balanced',
    random_state=42
)
```

---

## 📈 Final Model Performance

* **Accuracy:** 0.96
* **Precision:** 0.88
* **Recall:** 0.83
* **F1 Score:** 0.85
* **AUC:** 0.93

### ✅ Improvements Achieved

* Reduced overfitting
* Handled class imbalance
* Balanced precision and recall
* Significant improvement in F1-score

---

## 📊 Feature Importance Insights

Top drivers of churn:

* `Day_Charge`
* `Day_Mins`
* `CustServ_Calls`
* `Intl_Plan`

### 💡 Key Takeaways

* High customer service calls → strong churn signal
* Daytime usage heavily impacts churn behavior
* Redundant features (Charge vs Minutes) can be removed

---

## 🧠 Business Recommendations

* Improve **customer service experience**
* Monitor customers with **high day usage**
* Target users with **international plans**
* Build retention campaigns for high-risk customers

---

## 🛠️ Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* Matplotlib, Seaborn

---

## 🚀 Future Improvements

* Apply **SMOTE** for better imbalance handling
* Try **XGBoost / LightGBM**
* Optimize decision threshold for better recall
* Deploy model using Flask/Streamlit

---

## 📌 Conclusion

Hyperparameter tuning and class balancing significantly improved model performance. The final Random Forest model provides a reliable solution for predicting customer churn and generating actionable business insights.

---
