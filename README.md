# Churn-prediction
For Churn prediction we can do EDA to explore the correlation of different features with churn, how it is impacting.

XGBoost is a powerful and efficient algorithm that builds a series of decision trees, where each tree attempts to improve upon the previous ones, resulting in highly accurate predictions.

1. EDA:
   - First we try to explore the different columns/ features that are present for the churn prediction.
   - The dataset has too many features with text data and are probably categorical features! Total Charges is a feature with numerical values but are stored in string 
     datatype. First, we will convert this column into float.
   - While converting the TotalCharges to float, an error occurred with the message describing that it could not convert string to float.
   - This message popped up because of the empty strings present in the above displayed index positions of the TotalCharges column. As these elements were defined as string, 
      they did not appear as Null values and hence the heatmap for missing values did not display anything.E.g : a = ' '
   - we split the individual elements of TotalCharges and store the index values of the elements whose splitted string length is not equal to 1.This created a list with index 
     numbers of the empty strings which are filled with their preceding value and finally the entire column is converted into float using astype function.
   - We drop the customerID column as well!  

3. ML Model used
   - KNN
   - Logistic Regression
   - Random Forest
   - SVM
   - AdaBoost
   - XGBoost
