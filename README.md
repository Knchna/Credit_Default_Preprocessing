# Credit Card Default Prediction using Machine Learning

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]([Credit_Default_Preprocessing.ipynb](https://github.com/Knchna/Credit_Default_Preprocessing/blob/main/Credit_Default_Preprocessing.ipynb))

An end-to-end machine learning project on the UCI Credit Card Default dataset, covering data preprocessing, exploratory data analysis (EDA), feature analysis, classification model development, hyperparameter tuning, ensemble methods, and model evaluation.

### Team Project
Dataset: Default of Credit Card Clients (UCI Repository)

## Project Overview

This project aims to predict whether a credit card customer will default on the next month's payment using demographic information, payment history, bill statements, and previous payment records. Multiple machine learning models are developed, tuned, and evaluated to identify the best-performing approach for this binary classification problem.

---

## Dataset Information

* **Dataset Name:** Default of Credit Card Clients
* **Source:** UCI Machine Learning Repository
* https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients

The dataset contains demographic information, payment history, bill statements, previous payment amounts, and the target variable indicating whether the client defaulted on payment the next month.

* **Total Records:** 30,000
* **Total Features:** 25 (including the target variable)
* **Problem Type:** Binary Classification

The objective is to predict whether a customer will default on their credit card payment in the next month.

Target Variable:

* **default payment next month**

  * **0** → No Default
  * **1** → Default

---

## Technologies Used

- Python
- Google Colab / Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow / Keras

---

## Project Structure

Credit_Default_Prediction/
│
├── Credit_Default_Prediction.ipynb
├── default of credit card clients.xls
├── README.md

---

## Dataset Features

### Customer Information

| Feature   | Description                                 |
| --------- | ------------------------------------------- |
| ID        | Unique customer identifier                  |
| LIMIT_BAL | Amount of credit limit granted (NT dollars) |
| SEX       | Gender (1 = Male, 2 = Female)               |
| EDUCATION | Education level                             |
| MARRIAGE  | Marital status                              |
| AGE       | Customer age                                |

---

### Payment History

These variables represent the customer's repayment status during the previous six months.

| Feature | Description                   |
| ------- | ----------------------------- |
| PAY_0   | Repayment status in September |
| PAY_2   | Repayment status in August    |
| PAY_3   | Repayment status in July      |
| PAY_4   | Repayment status in June      |
| PAY_5   | Repayment status in May       |
| PAY_6   | Repayment status in April     |

Repayment Status Codes:

* -2 = No consumption
* -1 = Paid in full
* 0 = Paid on time
* 1 = Payment delay for one month
* 2–8 = Delay for multiple months

---

### Bill Statement Amount

Outstanding bill amount for the previous six months.

* BILL_AMT1
* BILL_AMT2
* BILL_AMT3
* BILL_AMT4
* BILL_AMT5
* BILL_AMT6

---

### Previous Payment Amount

Amount paid by the customer during the previous six months.

* PAY_AMT1
* PAY_AMT2
* PAY_AMT3
* PAY_AMT4
* PAY_AMT5
* PAY_AMT6

---

### Target Variable

| Value | Meaning                  |
| ----- | ------------------------ |
| 0     | Customer did not default |
| 1     | Customer defaulted       |

---

## Preprocessing Pipeline

The following preprocessing steps were performed before model training.

- Data loading
- Exploratory Data Analysis (EDA)
- Data cleaning
- Missing value verification
- Duplicate removal
- Dropping the ID column
- Outlier analysis
- Correlation analysis
- Train-test split
- Mutual Information Feature Analysis
- Feature scaling

---

## Machine Learning Methodology

Each team member independently implemented one baseline classification model:

- Logistic Regression
- Decision Tree
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)

For each model, the following workflow was performed:

- Baseline model training
- K-Fold / Stratified K-Fold Cross-Validation
- Hyperparameter tuning using GridSearchCV and RandomizedSearchCV
- Suitable ensemble learning techniques (Bagging, AdaBoost) where applicable
- Performance evaluation using classification metrics

The best-performing variant of each model was then compared to identify the overall best traditional machine learning approach.

---

### Artificial Neural Network (ANN)

Each team member independently developed an Artificial Neural Network (ANN) model on their respective Git branches. The best-performing ANN architecture was selected and merged into the main project branch for the final comparison with the traditional machine learning models.

---

## Results

The performance of all traditional machine learning models and the final ANN model was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Cross-Validation Score

The best-performing version of each model was compared to determine the overall most effective approach for credit card default prediction.

---

## Project Workflow

Load Dataset
      │
      ▼
Initial Exploratory Data Analysis
      │
      ▼
Data Cleaning
      │
      ▼
Feature Analysis
      │
      ▼
Train-Test Split
      │
      ▼
Feature Scaling
      │
      ▼
Baseline Model Training
      │
      ▼
Cross Validation
      │
      ▼
Hyperparameter Tuning
      │
      ▼
Ensemble Learning
      │
      ▼
ANN Implementation
      │
      ▼
Final Model Comparison

---

## How to Run the Project

### Option 1: Google Colab (Recommended)

1. Clone or download this repository.
2. Open `Credit_Default_Prediction.ipynb` in **Google Colab**.
3. Upload the dataset (`default of credit card clients.xls`) to the Colab session.
4. Run the notebook from the first cell to the last.

> **Note:** Google Colab includes all the required libraries (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, TensorFlow/Keras, and OpenPyXL) by default.

### Option 2: Run Locally

Clone the repository:

```bash
git clone https://github.com/your-username/Credit_Default_Prediction.git
cd Credit_Default_Prediction
```

Install the required dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow openpyxl
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open `Credit_Default_Prediction.ipynb` and run all the cells.

---

## Team Members

| Team Member | Contribution |
|-------------|--------------|
| **Gokul V S** | Performed dataset understanding, initial Exploratory Data Analysis (EDA) and Data Cleaning. Implemented the **K-Nearest Neighbors (KNN)** classifier, performed cross-validation, hyperparameter tuning (GridSearchCV and RandomizedSearchCV), applied suitable ensemble techniques, and participated in final model comparison. |
| **Devadeth B** | Executed Outlier Analysis, Bivariate Analysis, and visualization. Implemented the **Decision Tree** classifier, performed cross-validation, hyperparameter tuning, applied suitable ensemble techniques, developed the project's final **Artificial Neural Network (ANN)** model, and participated in final model comparison. |
| **Kanchana Krishna** | Applied Correlation analysis, Mutual Information feature selection, and feature analysis. Implemented the **Logistic Regression** classifier, performed cross-validation, hyperparameter tuning, applied suitable ensemble techniques, and participated in final model comparison. |
| **Rinimol R** | Completed Feature preprocessing, Scaling, documentation, and README preparation. Implemented the **Support Vector Machine (SVM)** classifier, performed cross-validation, hyperparameter tuning, applied suitable ensemble techniques, and participated in final model comparison. |

---

## Expected Outcome

Build, optimize, and evaluate multiple machine learning models for credit card default prediction, and compare their performance to identify the most effective classification approach.

---

## Dataset Citation

Yeh, I. C., & Lien, C. H. (2009). *The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients*. Expert Systems with Applications, 36(2), 2473–2480.

Dataset: **Default of Credit Card Clients**

Source: UCI Machine Learning Repository

https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients

---

## License

This project is intended for educational and academic purposes.

