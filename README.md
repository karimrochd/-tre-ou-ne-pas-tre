# To Be or Not to Be: Hospital Patient Mortality Prediction

## Introduction

This project focuses on developing a supervised learning model to predict mortality in hospital patients. Using a dataset of 80,000 patients with various attributes such as gender, age, and ethnicity, we aim to create an algorithm that can automatically assess a patient's likelihood of survival.

## Project Structure

The project is divided into three main parts:

1. **Data Loading and Preprocessing**
2. **Exploratory Data Analysis**
3. **Model Building and Evaluation**

## 1. Data Loading and Preprocessing

### Key Steps:
- Load the dataset and explore its characteristics
- Handle missing values and outliers
- Convert categorical variables to numerical format using LabelEncoder and One-Hot Encoding
- Implement Principal Component Analysis (PCA) for dimensionality reduction

### Data Cleaning:
- Replace undefined values with the mode of each variable
- Remove or modify unusable data to ensure model accuracy

## 2. Exploratory Data Analysis

### Variable Types:
- Majority of variables are numeric
- Several binary variables
- Eight categorical variables

### Target Variable:
- Examined the 'y' variable indicating patient survival
- Found that the majority of patients in the dataset survive

### Visualization:
- Created graphs to visualize data distribution and relationships
- Analyzed correlation between variables

## 3. Model Building and Evaluation

### Model Selection:
- Implemented Logistic Regression as the primary model
- Also tested K-Nearest Neighbors (KNN) for comparison

### Evaluation Methods:
- Used hold-out method for initial validation
- Implemented cross-validation for more reliable results
- Utilized GridSearchCV for hyperparameter tuning

### Performance Metrics:
- Calculated balanced accuracy for both models
- Analyzed AUC (Area Under the Curve) scores

### Visualization of Results:
- Created bar charts with error bars to display model performance across different hyperparameters

## Results and Conclusions

1. **Balanced Classification:**
   - If the priority is balanced performance across both classes (survival and non-survival), the **KNN model** shows a higher balanced accuracy score.

2. **Precise Distinction:**
   - For scenarios requiring accurate distinction between survival and non-survival, which is crucial in medical contexts, the **Logistic Regression model** outperforms with a significantly higher AUC score.


## Tools and Libraries Used

- Python
- Pandas for data manipulation
- Scikit-learn for machine learning models and evaluation
- Matplotlib and Seaborn for data visualization

---

This project demonstrates the application of machine learning in healthcare, specifically in predicting patient outcomes. The insights gained can potentially assist medical professionals in making informed decisions and improving patient care strategies.
