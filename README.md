# Customer Churn Prediction 📉

**Course:** CSE422: Artificial Intelligence  
**Institution:** BRAC University  
**Group:** 03

## 📝 Project Overview

The primary goal of this project is to build a machine learning system capable of predicting **Customer Churn**. Churn occurs when a customer stops doing business with an entity. In a competitive market, retaining existing customers is significantly more cost-effective than acquiring new ones. 

This project utilizes Artificial Intelligence to move from "guessing" why people leave to "predicting" it based on demographic and financial profiles.

## 📂 Dataset Description

The dataset consists of **1,500 data points** with **9 features** (8 independent variables + 1 target variable).

* **Target Variable:** `Churn` (Binary: 0 or 1)
* **Numerical Features:** `Age`, `Income`, `Credit_Score`, `Num_Purchases`, `Membership_Years`
* **Categorical Features:** `Gender`, `Marital_Status`, `Device_Used`

## 🔍 Exploratory Data Analysis (EDA)

We performed statistical profiling and visualization to understand the data logic:

1.  **Skewness:** Most features were symmetric, but `Num_Purchases` was **Right-Skewed**, indicating a "long tail" of power users.
2.  **Outlier Detection:** Using **Boxplots**, we identified impossible data points, such as negative incomes and credit scores above 850.
3.  **Correlation:** A heatmap analysis revealed very low correlation between demographics (Age, Income) and Churn, suggesting prediction would be a complex task.

## 🛠 Data Pre-processing

To make the data machine-readable, the following steps were taken:

* **Cleaning:** Removed rows with impossible values (e.g., negative income).
* **Imputation:**
    * *Numerical:* Filled missing values with the **Median** to avoid skewness impact.
    * *Categorical:* Filled missing `Gender` entries with the **Mode**.
* **Encoding:** Applied **One-Hot Encoding** (`drop_first=True`) for categorical variables.
* **Scaling:** Applied **StandardScaler** to center the data and reduce the impact of skewness.

## 🧠 Models Implemented

We trained four distinct models on an 80/20 train-test split:

1.  **Logistic Regression:** Uses the Sigmoid function to predict class probability.
2.  **Random Forest Classifier:** An ensemble model building 500 decision trees using majority voting.
3.  **Multi-Layer Perceptron (MLP):** A Neural Network with hidden layers using weights, biases, and activation functions.
4.  **K-Means Clustering (Unsupervised):** Groups data points based on Euclidean distance to centroids.

## 📊 Results

Despite the low correlation in the raw data, we evaluated the models based on **Accuracy Score**.

| Model | Accuracy |
| :--- | :--- |
| **K-Means Clustering** | **56.67%** |
| Logistic Regression | 51.00% |
| Random Forest | 50.00% |
| MLP (Neural Network) | 49.33% |

### Conclusion & Analysis
The **K-Means Clustering** model performed the best. This suggests that the supervised labels (Churn) might be noisy, and the unsupervised model was better at finding the real, natural groupings within the feature data itself. The Neural Network (MLP) struggled likely due to the dataset size and lack of strong behavioral patterns.

## 👥 Contributors

* **Amirun Nahin** (ID: 23201416)
* **Sultan Mohammad Farid** (ID: 23201107)

## 🎓 Instructor
Submitted to **Rafiad Sadat Shahir (RSS)**, Lecturer, BRAC University.