# Telecom Churn Prediction

## Overview

This project focuses on predicting customer churn for a telecommunications company using various machine learning algorithms. Churn prediction is crucial for businesses to retain customers and maintain steady revenue. In this project, we explore the dataset through extensive exploratory data analysis (EDA), handle data preprocessing, balance the data using SMOTE, perform feature selection, and apply multiple machine learning models to achieve accurate predictions.

## 1. Exploratory Data Analysis (EDA)

### Data Exploration

- **Feature Overview**: We start by examining the different columns/features in the dataset to understand their types and relevance to churn prediction.
- **Handling Categorical Features**: The dataset contains numerous categorical features represented as text data.
- **Handling Numerical Features**: The `TotalCharges` feature, though numerical, is stored as a string datatype. This needs conversion to float.

### Data Cleaning

- **Conversion to Float**: During the conversion of `TotalCharges` to float, an error occurs due to the presence of empty strings. These empty strings are not recognized as Null values.
- **Identifying Empty Strings**: We identify the indices of these empty strings by checking the length of the split string elements.
- **Filling Empty Values**: The empty strings are filled with their preceding values.
- **Column Drop**: We drop the `customerID` column as it does not contribute to the predictive analysis.

## 2. Machine Learning Models

We employ a variety of machine learning models to predict churn:

- **K-Nearest Neighbors (KNN)**
- **Logistic Regression**
- **Random Forest**
- **Support Vector Machine (SVM)**
- **AdaBoost**
- **XGBoost**

## 3. Feature Selection

### Importance of Feature Selection

Feature selection is the process of identifying and selecting the most relevant features for use in model construction. This helps in:

- Removing irrelevant features that could negatively impact model performance.
- Addressing the curse of dimensionality.
- Reducing training and deployment time, which is crucial for efficient model operation.

### Types of Feature Selection

- **Supervised Methods**: Used when labels are available. This includes:
  - **Wrappers**: Use model performance to evaluate the importance of features.
  - **Filters**: Use statistical techniques to evaluate the significance of features.
  - **Embedded**: Perform feature selection during the model training process.

### Methods Used

- **SelectKBest**: Selects the top K features based on statistical tests.
- **Chi-Square Test**: A filter method used for categorical features.
- **ANOVA (Analysis of Variance)**: A filter method used for numerical features.

## 4. Data Balancing Using SMOTE

### Why Data Balancing?

Class imbalance is a common issue in datasets, which can lead to biased models that perform poorly on the minority class. Resampling techniques are used to address this imbalance.

### Methods

- **Undersampling**: Removes instances from the majority class.
- **Oversampling**: Adds instances to the minority class.

### SMOTE (Synthetic Minority Over-sampling Technique)

We use SMOTE to perform oversampling, as it generates synthetic samples for the minority class, which helps in achieving a balanced dataset without losing any important information.

## 5. Model Performance After Feature Selection and SMOTE

### Model Scores

- **XGBoost**: CV Score - 90.03%
- **LightGBM**: CV Score - 90.20%
- **Random Forest Classifier**: CV Score - 85.62%
- **Decision Tree Classifier**: CV Score - 83.94%
- **Stacked Model (XGBClassifier, LightGBMClassifier, Random Forest Classifier & Decision Tree Classifier)**: CV Score - 90.77%

## Conclusion

This project demonstrates the effectiveness of using EDA, data preprocessing, feature selection, and advanced machine learning techniques to predict customer churn. By balancing the dataset and selecting relevant features, we significantly improve the model's performance, making it a valuable tool for the telecommunications company to retain customers and reduce churn.

---

Feel free to check the code and detailed implementation in the repository. If you have any questions or suggestions, please open an issue or contact me directly.

Happy Coding!
