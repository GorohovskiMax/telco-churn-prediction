# Telco Customer Churn Prediction

**Author:** Maxim Gorohovski

## 🎉 Project Overview
This repository contains a complete end-to-end data science project that tackles the
business-critical challenge of **customer churn** prediction in the telecom sector.
By identifying which customers are likely to leave and why, companies can build
targeted retention strategies and minimize losses. 

**Goal**: Predict whether a customer will churn based on their demographic, service,
and billing data, and offer insights into the key drivers of churn

## 🗂️ Project Structure
- **notebook/**: Main notebook for the data science project
- **README.md**: Project overview and usage instructions
- **data/**: Folder in which the .csv file will be placed for work

  
## 📊Dataset
- **Name**: Telco Customer Churn
- **Source**: [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data)

  - **Rows**: 7,043 customer records
  - **Features**: 21, including:
     - Demographics (Gender, Senior Citizen, etc.)
     - Services (Internet, Phone, Tech Support, etc.)
     - Account info (Contract, Tenure, Monthly Charges, etc.)
  - **Target**: `Churn` (Yes/No)

> **Note**: Due to licensing restrictions, the full dataset is **not** included in this repository.
> Please download `WA_Fn-UseC_-Telco-Customer-Churn.csv` from Kaggle, and place it in the `data/` folder.


## 🤸‍♂️ Methodology

1. Exploratory Data Analysis (EDA)

2. Data Cleaning and Preprocessing

3. Feature Engineering

4. Model Training & Tuning

5. Evaluation

6. Business Insights & Recommendations



## 🎨 Visual Insights from EDA 
- Customers with **low tenure** (≤ 12 months) are at the highest churn risk
- **Fiber Optic** internet users churn more than DSL/No Internet users
- **Month-to-month contracts** have much higher churn than long-term ones.
- Churners tend to have **higher monthly charges**

## 🧰 Feature Engineering
- Created **SpendTrend** feature to capture billing shifts:
  - Positive `SpendTrend`: Current charges > historical average
  - Negative `SpendTrend`: Current charges < historical average
 
## 📈 Models used
1. Logistic Regression (As baseline model)
   - Used GridSearchCV for hyperparameter tuning
   - Provides good interpretability, fast and solid performance

2. Random Forest Classifier (Balanced)
   - Handled class imbalance with `class_weight = 'balanced'`
   - Captures nonlinear relationships and interactions


## 🔄 Model Performance Comparison  
| Model                          | Accuracy | ROC AUC | Churn Recall | Churn F1 |
|--------------------------------|----------|---------|-------------|----------|
| **Logistic Regression**        | 80%      | 84%     | 0.53        | 0.58     |
| **Random Forest (Balanced)**   | 78%      | 83%     | 0.61        | 0.60     |

**Note** that Random Forest had slightly lower accuracy than Logistic Regression but a much better **recall**,
which is crucial in real-world churn prevention.

## 📉 Top Influential Features
**(from Logistic Regression and Random Forest)**
- Tenure
- Contract Type (Month-to-month, One year, Two year)
- Monthly Charges
- Internet Service (Fiber Optic)
- SpendTrend
- Payment Method (Electronic Check)


## 📆 Business Recommendations
1. **Target early-tenure customers** with retention offers and programs and encourage longer contracts
2. Offer **discounts or bundles** to customers with high monthly charges
3. Investigate **fiber optic service quality** or pricing strategy
4. Understand why **paperless billing and electronic check** users churn more

## 🚫 Limitations and Future Work
- Only a one-time snapshot of data is available, there is no time series or customer history
- **Class Imbalance** mitigated but not fully resolved
- **External factors** like competitor offers are not included
- Future work: Larger dataset, advanced models (e.g., neural networks), time-series analysis, deeper feature engineering.

## 🔧 Tools and Libraries Used
- Python (Pandas, Numpy)
- Visualization (Seaborn, Matplotlib)
- Scikit-learn (Logistic Regression, Random Forest, GridSearchCV)

## 🙏 Few finals words
🚀 This project is a full cycle application of machine learning in a real business scenario.
from data preparation and feature engineering to insights and model tuning, it highlights how data science
can offer concrete business value. If you found this project useful or interesting, feel free to ⭐ the repo or reach out!🚀 
