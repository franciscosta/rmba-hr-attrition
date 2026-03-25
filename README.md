# Employee Attrition Analysis: Age & Work-Life Balance

> **Research Methods in Business Analytics (2024) — Group Project**

## Research Question

> *"How do age and work-life balance influence employee attrition, and do younger employees value work-life balance more than older employees when deciding to leave?"*

---

## Project Overview

This project investigates the drivers of employee attrition using the IBM HR Employee Attrition dataset. The analysis focuses on understanding how **age** and **work-life balance** interact to influence an employee's decision to leave a company.

The study combines exploratory data analysis with two statistical methods — logistic regression and a t-test — to test specific hypotheses about age-related attrition patterns and work-life balance perceptions.

---

## Objectives

- Identify which demographic and job-related factors are most strongly associated with employee attrition
- Test whether younger employees (under 36) are statistically more likely to leave than older employees
- Determine whether younger employees who leave report worse work-life balance than their older counterparts
- Provide data-driven insights that could inform employee retention strategies

---

## Dataset

- **Source:** [IBM HR Employee Attrition Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) (publicly available)
- **Size:** 1,470 employee records, 35 features
- **Target variable:** `Attrition` (Yes/No — whether the employee left the company)

---

## Key Results

- **Younger employees (<36)** exhibit a significantly higher attrition rate of **21.95%**, compared to **10.39%** for employees aged 36 and above
- **Overtime** is the strongest predictor of attrition — employees working overtime have a **30.05%** attrition rate vs **12.36%** for those who don't
- **Logistic Regression** confirms that each additional year of age reduces the log odds of leaving by ~0.046 (p < 0.001)
- **T-Test** found no statistically significant difference in work-life balance scores between younger and older employees who left — suggesting age alone doesn't explain work-life balance perceptions
- **McFadden's pseudo R² = 0.155**, indicating a modest but reasonable model fit for predicting human behaviour

---

## Methodology

### 1. Data Cleaning & Preprocessing
- Checked for missing values and duplicates (none found)
- Applied binary mapping and one-hot encoding to categorical variables
- Removed constant columns (`Over18`, `StandardHours`)

### 2. Exploratory Data Analysis (EDA)
- Descriptive statistics across all key variables
- Correlation matrix and heatmap (top 20 variables correlated with attrition)
- Visual analysis of attrition by: Age, Work-Life Balance, Job Satisfaction, Job Involvement, Job Level, Salary Hike, Business Travel, Department, Overtime, and Marital Status

### 3. Method 1 — Logistic Regression
- Modelled attrition as a function of Age, Overtime, Work-Life Balance, Marital Status (Single), Job Role (Sales Rep), and Business Travel (Frequent)
- Checked assumptions: No multicollinearity (VIF < 2 for all variables), Independence of errors (Durbin-Watson = 1.93)
- Computed McFadden's, Cox & Snell, and Nagelkerke pseudo R² values

### 4. Method 2 — Independent Samples T-Test (One-Tailed, Pooled)
- Compared work-life balance scores between younger (<36) and older (≥36) employees who left
- Verified assumptions: Normality via Central Limit Theorem (n > 30), Independence, Homogeneity of variances (Levene's test p = 0.34)
- Result: Failed to reject H₀ (no significant difference in work-life balance by age group among leavers)

---

## Technologies Used

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)
![Statsmodels](https://img.shields.io/badge/Statsmodels-3776AB?style=flat)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat&logo=googlecolab&logoColor=white)

---

## Skills Demonstrated

- **Data Wrangling:** Cleaning, encoding, and transforming a real-world HR dataset using pandas
- **Exploratory Data Analysis:** Identifying patterns and relationships through visualisation and statistics
- **Statistical Testing:** Designing and running hypothesis tests (t-test, Levene's test) and interpreting results rigorously
- **Regression Modelling:** Building and validating a logistic regression model with assumption checking (VIF, Durbin-Watson)
- **Data Visualisation:** Creating dual-axis bar/line plots to communicate distributional and attrition insights clearly
- **Research Communication:** Structuring findings as an academic report with executive summary, methodology, and conclusions

---

## How to Run

1. Clone this repository
   ```bash
   git clone https://github.com/YOUR_USERNAME/rmba-hr-attrition.git
   ```
2. Open the notebook in [Google Colab](https://colab.research.google.com/) or Jupyter
3. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) and upload it when prompted
4. Run all cells in order

> **Note:** The notebook uses `google.colab.files.upload()` to load the dataset. If running locally in Jupyter, replace that cell with `pd.read_csv('HR-Employee-Attrition.csv')`.

---

## Authors

*Add your name and your group members' names here*

---

## Course

Research Methods in Business Analytics — 2024
