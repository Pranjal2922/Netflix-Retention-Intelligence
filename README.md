# Netflix Retention Intelligence

### AI-Powered Subscriber Churn Prediction & Risk Analytics

Netflix Retention Intelligence is a machine-learning project that predicts whether a subscriber is **likely to churn (cancel their subscription)** based on their subscription tenure, engagement behavior, customer support interactions, payment failures, and plan tier.

The project uses **Logistic Regression**, an interpretable classification algorithm, to estimate churn risk and identify the factors that influence subscriber retention.

> **Tagline:** Predict Churn. Identify Risk. Retain Customers.

---

## 📌 Project Overview

Customer churn is a major challenge for subscription-based businesses. Identifying subscribers who may cancel their subscription allows businesses to take proactive retention actions.

This project demonstrates an end-to-end churn prediction workflow:

**Data Generation → Data Exploration → Preprocessing → Feature Engineering → Model Training → Prediction → Evaluation → Business Interpretation**

The model learns patterns from subscriber data and predicts whether a subscriber is:

* **0 — Stayed**
* **1 — Churned**

---

## 🎯 Business Objective

The primary objective is to build a simple and interpretable ML model that can:

* Predict subscriber churn
* Identify high-risk subscribers
* Understand major churn drivers
* Support proactive customer retention
* Demonstrate how AI/ML can be applied to subscription businesses

---

## 🤖 Machine Learning Approach

### Model: Logistic Regression

Logistic Regression was selected because churn is a **binary classification problem**.

The model provides a coefficient/weight for each feature, making it easier to understand how different subscriber behaviors influence churn risk.

### Why Logistic Regression?

* Easy to explain
* Fast and efficient
* Suitable for binary classification
* Provides churn probabilities
* Highly interpretable
* Useful for demonstrating business impact

---

## 📊 Dataset

The project uses a **synthetic dataset containing 3,000 subscriber records**.

Netflix's real subscriber-level data is private, so the dataset was created specifically for this educational project using realistic subscriber characteristics.

### Features

| Feature              | Description                                                     |
| -------------------- | --------------------------------------------------------------- |
| `tenure_months`      | Number of months the subscriber has been subscribed             |
| `weekly_watch_hours` | Average hours watched per week                                  |
| `logins_per_month`   | Number of times the subscriber logs into the platform per month |
| `support_tickets`    | Support tickets raised during the last 90 days                  |
| `payment_failures`   | Failed payments during the last 90 days                         |
| `plan_tier`          | Subscriber's Basic, Standard, or Premium plan                   |
| `churn`              | Target variable: 0 = Stayed, 1 = Churned                        |

---

## 🔄 ML Pipeline

### 1. Data Generation

A synthetic subscriber dataset is created using realistic business variables and predefined churn-risk patterns.

### 2. Data Exploration

The dataset is examined using:

* Dataset shape
* Churn rate
* Descriptive statistics
* Churn distribution visualization

### 3. Data Preprocessing

The categorical `plan_tier` variable is converted into numerical variables using **one-hot encoding**.

The dataset is then divided into:

* **80% Training Data**
* **20% Testing Data**

Stratified splitting is used to maintain the churn/non-churn distribution.

### 4. Feature Scaling

`StandardScaler` is applied so that features with different numerical ranges can be processed consistently by the Logistic Regression model.

Importantly, the scaler is fitted only on the training data and then applied to the test data.

### 5. Model Training

A Logistic Regression classifier is trained using the processed training data.

### 6. Prediction

The trained model predicts churn on unseen test data and can also estimate the **probability of churn for an individual subscriber**.

### 7. Model Evaluation

The model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix

---

## 📈 Model Evaluation

The project uses multiple evaluation metrics rather than relying only on accuracy.

### Accuracy

Measures the overall percentage of correct predictions.

### Precision

Shows how many subscribers predicted as churners actually churned.

### Recall

Shows how many actual churners were successfully identified.

### F1-Score

Provides a balance between precision and recall.

### Confusion Matrix

Shows:

* Correctly predicted stays
* Correctly predicted churners
* False churn predictions
* Missed churners

---

## 🔍 Churn Driver Analysis

One of the key advantages of Logistic Regression in this project is interpretability.

Each feature receives a **model coefficient**:

* **Positive coefficient** → pushes churn risk higher
* **Negative coefficient** → pushes churn risk lower
* Larger absolute coefficient → stronger influence in the model

Based on the notebook's generated data and model design, important churn-risk patterns include:

### Higher Churn Risk

* Payment failures
* Lower weekly watch hours
* Fewer monthly logins
* Higher support-ticket activity

### Lower Churn Risk

* Longer subscription tenure
* Higher engagement
* Premium plan membership

---

## 🧪 Live Churn Prediction

The notebook includes a reusable `predict_churn()` function.

It accepts subscriber information such as:

```text
Tenure
Weekly Watch Hours
Monthly Logins
Support Tickets
Payment Failures
Plan Tier
```

The model then returns:

```text
Predicted churn probability
+
LIKELY TO CHURN / LIKELY TO STAY
```

This allows the model to be demonstrated using different subscriber profiles.

---

## 💼 Business Application

A real-world subscription business could use a similar system to create a **customer retention workflow**.

For example:

**Subscriber Data → Churn Probability → Risk Segmentation → Retention Action**

High-risk subscribers could potentially be routed to a retention team for actions such as:

* Personalized offers
* Free upgrade periods
* Proactive customer support
* Payment assistance
* Engagement campaigns
* Personalized content recommendations

The exact retention strategy would depend on business rules, customer value, and experimentation.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Scikit-learn**
* **Logistic Regression**
* **StandardScaler**
* **Google Colab / Jupyter Notebook**

---

## 📁 Project Structure

```text
Netflix-Retention-Intelligence/
│
├── netflix_churn_logistic_regression.ipynb
├── README.md
└── requirements.txt
```

---

## 🧠 Key Learning Outcomes

This project demonstrates practical understanding of:

* Machine Learning classification
* Customer churn analytics
* Data preprocessing
* One-hot encoding
* Train-test splitting
* Feature scaling
* Logistic Regression
* Churn probability prediction
* Confusion matrices
* Classification metrics
* Model interpretability
* Business-oriented ML applications

---

## ⚠️ Project Limitation

This project uses a **synthetic dataset created for a classroom/case-study exercise**.

It does not use Netflix's actual private subscriber data.

Therefore, the model should **not be considered production-ready**. A real deployment would require:

* Real subscriber data
* Larger and more representative datasets
* Additional customer behavior features
* Cross-validation
* Model tuning
* Threshold optimization
* Privacy and data governance
* Continuous model monitoring
* Business impact validation

---

## 🚀 Future Enhancements

The project can be extended by adding:

* Customer Lifetime Value (CLV)
* Content preference
* Viewing frequency
* Device usage
* Subscription history
* Payment behavior
* Customer demographics
* Engagement trends
* A/B testing of retention campaigns
* Random Forest and Gradient Boosting models
* Churn-risk dashboards
* Automated retention recommendations

---

## 📌 Business Impact

A mature version of this solution could help a subscription business move from:

**Reactive Retention**

> Customer cancels → Business reacts

to:

**Predictive Retention**

> Model identifies risk → Business intervenes → Customer is potentially retained

This is the core business value of churn prediction: **using data to identify retention opportunities before customer loss occurs.**

---

## 👩‍💻 Project Type

**Domain:** FinTech / Business Analytics / AI & Machine Learning
**Use Case:** Customer Churn Prediction
**ML Task:** Binary Classification
**Algorithm:** Logistic Regression
**Dataset:** Synthetic Subscriber Dataset
**Records:** 3,000

---

## ⭐ Project Summary

**Netflix Retention Intelligence** demonstrates how machine learning can transform subscriber behavior into actionable churn-risk insights.

By combining **engagement, tenure, support, payment, and subscription-plan data**, the system predicts churn probability and helps identify subscribers who may require proactive retention efforts.

> **Predict Churn. Identify Risk. Retain Customers.**
