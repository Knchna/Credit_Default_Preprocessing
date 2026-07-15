# Credit_Default_Preprocessing
Machine Learning data preprocessing and EDA project on the UCI Credit Card Default dataset.

### Team Project
Dataset: Default of Credit Card Clients (UCI Repository)

## Project Overview

This project focuses on preprocessing the Default of Credit Card Clients dataset to prepare it for machine learning models that predict whether a customer will default on their credit card payment in the following month.

The notebook performs data cleaning, exploratory data analysis (EDA), feature analysis, outlier detection, feature scaling, and train-test splitting to ensure high-quality input for classification algorithm. 

The final processed dataset is ready for training classification models such as Logistic Regression, Decision Tree, Random Forest, XGBoost, and other machine learning algorithms.

The goal of this project is to produce a clean and standardized dataset that improves model performance while preventing data leakage.

---

# Dataset Information

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

---

## Project Structure

Credit_Default_Preprocessing/
│
├── Credit_Default_Preprocessing.ipynb
├── default of credit card clients.xls
├── README.md

---

# Dataset Features

## Customer Information

| Feature   | Description                                 |
| --------- | ------------------------------------------- |
| ID        | Unique customer identifier                  |
| LIMIT_BAL | Amount of credit limit granted (NT dollars) |
| SEX       | Gender (1 = Male, 2 = Female)               |
| EDUCATION | Education level                             |
| MARRIAGE  | Marital status                              |
| AGE       | Customer age                                |

---

## Payment History

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

## Bill Statement Amount

Outstanding bill amount for the previous six months.

* BILL_AMT1
* BILL_AMT2
* BILL_AMT3
* BILL_AMT4
* BILL_AMT5
* BILL_AMT6

---

## Previous Payment Amount

Amount paid by the customer during the previous six months.

* PAY_AMT1
* PAY_AMT2
* PAY_AMT3
* PAY_AMT4
* PAY_AMT5
* PAY_AMT6

---

# Target Variable

| Value | Meaning                  |
| ----- | ------------------------ |
| 0     | Customer did not default |
| 1     | Customer defaulted       |

---

## Preprocessing Pipeline

The following preprocessing steps were performed before model training.

### 1. Import Required Libraries

The notebook imports the required Python libraries for:

- Data manipulation
- Visualization
- Feature engineering
- Data preprocessing

Libraries include:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

---

### 2. Data Loading

* Loaded the Excel dataset using Pandas.
* Verified dataset dimensions and feature names.

---

### 3. Exploratory Data Analysis (EDA)

The notebook performs:

- Dataset overview
- Data types inspection
- Missing value analysis
- Duplicate record detection
- Statistical summary

---

### 4. Data Cleaning & Missing Value Check


Cleaning operations include:

- Checked for duplicate records.
- Removing duplicate records (if present).
- Dropping unnecessary columns
- Removing the **ID** column since it is only an identifier  and does not contribute to prediction.
- Verified that the dataset contains no missing values.

---

### 5. Data Preparation

The dataset is divided into:

- Numerical features
- Categorical features

This separation simplifies preprocessing and analysis.

---

### 6. Outlier Analysis

Outliers are identified using visualization techniques such as boxplots to understand the distribution of numerical variables.

---

### 7. Feature Analysis

The notebook includes:

- Bivariate analysis
- Correlation matrix
- Heatmap visualization
- Mutual Information analysis to evaluate feature importance

---

### 8. Feature and Target Separation

Separated the dataset into:

**Features (X)**

* LIMIT_BAL
* SEX
* EDUCATION
* MARRIAGE
* AGE
* PAY_0 to PAY_6
* BILL_AMT1 to BILL_AMT6
* PAY_AMT1 to PAY_AMT6
All independent variables.

**Target (y)**

* default payment next month

---

### 9. Train-Test Split

The data is divided into training and testing sets.

- Training Data: 80%
- Testing Data: 20%

This ensures that the model is evaluated on unseen data.

Splitting is performed before scaling to prevent data leakage.

---

### 10. Feature Scaling

Only numerical columns are standardized using **StandardScaler**.

Scaling is performed by:

- Fitting the scaler on training data
- Transforming both training and testing data using the same scaler

This ensures consistent preprocessing while avoiding information leakage.

---

## Output

After preprocessing, the notebook produces:

- Clean dataset
- Feature importance analysis
- Boxplots for Outlier Detection
- Correlation analysis
- Standardized numerical features
- Train and test datasets ready for machine learning
  
These analyses helped identify feature distributions, relationships, and potential outliers.

---

## How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Credit_Default_Preprocessing.git
```

### 2. Move into the Project Folder

```bash
cd Credit_Default_Preprocessing
```

### 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```
Credit_Default_Preprocessing.ipynb
```

Run the notebook from the first cell to the last.

---

## Team Members

| Team Member | Contribution |
|-------------|--------------|
| **Gokul** | Dataset Understanding & Initial Exploratory Data Analysis (EDA): Loaded the dataset, inspected its structure, identified numerical and categorical features, checked missing values and duplicates, validated categorical values, removed irrelevant columns (ID), identified the target variable, and performed univariate analysis on numerical, categorical, and target variables. |
| **Devadeth** | Outlier Handling & Visualization: Detected and analyzed outliers using the IQR method and boxplots, performed bivariate analysis between features and the target variable, created comparative visualizations, and documented key observations from the analysis. |
| **Kanchana** | Feature Selection: Conducted correlation analysis using a correlation matrix and heatmap, evaluated feature importance using Mutual Information, identified multicollinearity, selected relevant features, and prepared the final feature set for modeling. |
| **Rinimol R** | Feature Engineering & Data Preprocessing: Performed feature engineering where appropriate, documented preprocessing decisions, identified numerical features for scaling, applied **StandardScaler** after train-test splitting to prevent data leakage, verified the processed dataset, saved the final preprocessed dataset, summarized the preprocessing workflow, and prepared the GitHub project documentation (README). |

---

# Machine Learning Models

This preprocessed dataset can be used with several classification algorithms, including:

* Logistic Regression
* Decision Tree Classifier
* Random Forest
* Support Vector Machine (SVM)
* K-Nearest Neighbors (KNN)
* Naive Bayes
* AdaBoost
* Gradient Boosting
* XGBoost
* Artificial Neural Networks (ANN)

---

# Project Workflow

Load Dataset
      │
      ▼
Data Cleaning
      │
      ▼
Remove Duplicates
      │
      ▼
Drop ID Column
      │
      ▼
Check Missing Values
      │
      ▼
Outlier Handling
      │
      ▼
Bivariate Analysis
      │
      ▼
Feature Selection
      │
      ▼
Train-Test Split
      │
      ▼
Feature Scaling
      │
      ▼
Model Training
      │
      ▼
Model Evaluation


---

# Expected Outcome

The goal of this project is to build reliable machine learning models capable of predicting credit card payment defaults using customer demographic information, payment history, billing records, and previous payment behavior.

---

# Dataset Citation

Yeh, I. C., & Lien, C. H. (2009). *The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients*. Expert Systems with Applications, 36(2), 2473–2480.

Dataset: **Default of Credit Card Clients** from the UCI Machine Learning Repository.

https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients

---

## License

This project is intended for educational and academic purposes.

