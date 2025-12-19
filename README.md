# 🌐 Telecom-Customer-Churn-Prediction-(Machine-Learning)

![image_alt](https://www.shutterstock.com/image-photo/customer-churn-shown-using-text-600nw-2443621059.jpg)

## 🔍 Project Overview

Customer churn is a major challenge for telecom companies, directly impacting revenue and growth. This project builds a **machine learning–based churn prediction system** that identifies customers who are likely to discontinue services, enabling proactive retention strategies.

The solution follows a **complete end-to-end data science pipeline**, from exploratory data analysis to model training, evaluation, and prediction on unseen data.


## 🎯 Objectives

- Analyze customer behavior using exploratory data analysis (EDA)

- Identify key factors influencing customer churn

- Train and compare multiple machine learning models

- Select the best-performing model using cross-validation

- Build a deployable churn prediction pipeline


## 🗂 Dataset Description

The dataset contains customer demographic details, service usage information, billing data, and churn status.

**Target Variable**

- `Churn` (Yes / No)

**Feature Types**

- **Categorical:** `gender`, `Partner`, `Dependents`, `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`, `Contract`, `PaperlessBilling`, `PaymentMethod`.

- **Numerical:** `Tenure`, `Monthly Charges`, `Total Charges`.



## 🔎 Exploratory Data Analysis (EDA)

- Distribution analysis using histograms and box plots

- Categorical feature analysis using count plots

- Correlation analysis using heatmaps

### Key Insights:

- tenure and TotalCharges show strong positive correlation

- Customers with short tenure have higher churn probability

- Monthly charges significantly influence churn behavior



## 🛠 Data Preprocessing

- Label Encoding for categorical features

- Feature scaling using StandardScaler

- Encoders stored and serialized for future inference

- Data split using Stratified Train–Test Split



## 🤖 Baseline Model Training

Multiple baseline machine learning models were trained using **default hyperparameters** and evaluated using **5-Fold Stratified Cross-Validation**:

- Logistic Regression

- SGD Classifier

- Decision Tree

- K-Nearest Neighbors

- Random Forest

- Extra Trees

- Gradient Boosting

- AdaBoost

- XGBoost

- Support Vector Machine (SVM)


## 📈 Baseline Model Performance Summary

| Model | Cross-Validation Accuracy |
| :--- | :---: |
| **Random Forest** | 77.6% |
| **Gradient Boosting** | 77.1% |
| **XGBoost** | 76.7% |
| **Extra Trees** | 76.0% |
| **SVM** | 75.5% |

### Baseline Results

Among all baseline models, **Random Forest achieved the highest cross-validation accuracy = (`77.6%`)**, making it the best-performing model at this stage.



## ⚙️ Hyperparameter Tuning

To further improve performance, hyperparameter tuning was applied, with a particular focus on top 3 baseline models (`Random Forest`, `Gradient Boosting`, `XGBoost`).

- Optimized parameters such as:

   - Number of estimators

   - Learning rate

   - Maximum depth

   - Subsample and column sampling

- Cross-validation used to ensure generalization

### 📌 Post-Tuning Outcome

After hyperparameter optimization:

   - XGBoost outperformed all baseline models

   - Demonstrated better generalization on unseen data

   - Reduced overfitting compared to baseline models

➡️ **Tuned XGBoost was selected as the final model**


## 🧪 Final Model Evaluation

The tuned **XGBoost classifier** was evaluated on the test dataset using:

    - Confusion Matrix

    - Precision, Recall, F1-Score

    - Accuracy on unseen data

The evaluation confirms that the tuned XGBoost model provides the **best balance between performance and generalization**.


## 💾 Model Persistence

- Final tuned **XGBoost** model saved using pickle

- **Label encoders** saved to ensure consistent preprocessing during inference


## 📌 Conclusion
This project showcases a production-ready ML workflow for `telecom customer churn prediction`, from EDA to uncover behavioral patterns, `baseline modeling`, `hyperparameter tuning`, and thorough `evaluation`.

#### Key Takeaways:

- **Data Insights:** EDA highlights tenure, monthly charges, and contract type as key churn predictors, enabling targeted retention strategies.

- **Model Optimization:** `Random Forest` led baselines, but tuned `XGBoost` boosted generalization and test accuracy, emphasizing tuning's real-world value.

- **Reliable Evaluation:** `Stratified CV` and test metrics ensure low overfitting and strong unseen-data performance.

- **Deployable Pipeline:** Integrated preprocessing, encoding, and persistence support real-time predictions in enterprise systems.

- **Business Value:** Accurate churn forecasting drives proactive retention, enhancing revenue and customer lifetime value.
