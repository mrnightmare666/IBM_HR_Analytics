# Attrition Prediction Model - IBM HR Analytics
## Introduction
Attrition represents the rate at which employees depart from a company over a specific period. It is a critical metric that measures employee turnover and departure frequency within an organization.
Understanding and addressing attrition is integral to fostering a stable, productive, and motivated workforce. By leveraging data-driven insights and employing effective retention strategies, businesses can mitigate the negative impacts of attrition and build a resilient and high-performing team.

## Aim - To analyse the IBM HR Dataset and build a predictive model
- To prepare and clean the data
- To analyse the existing data using PowerBI to understand attrtion values
  - Attrition across Department
  - Attrition by Gender
  - Attrition across Job Roles
  - Attrition by Age Group
  - Attrition across Average Salary vs Working Years
 ![image](https://github.com/mrnightmare666/IBM_HR_Analytics/assets/53763049/e6a824c1-011a-4954-9f51-2dd4c57e284d)

## Machine Learning Models
- Logistic Regression
- Random Forest

## Understanding the Data
All the fields may not be required for creating the model as these fields will not impact the attrition chances :
- BusinessTravel
- EmployeeCount
- EmployeeNumber
- StandardHours

  

## Logistic Regression and model Training
By splitting the dataset into these two sets ( training set and test set), it's possible to check the model's performance on data it hasn't seen before, which helps in understanding how well the model is likely to perform in the real world with new data.
The typical split ratio is commonly 80% for training and 20% for testing

### One-Hot encoding
One-hot encoding is a technique used to handle categorical data which is necessary because many machine learning algorithms work with numerical data, and they struggle to interpret categorical variables directly.
Categorical variables contain different categories or groups, but their labels don't inherently imply an order or hierarchy. One-hot encoding helps represent these categorical variables as binary vectors.

### Splitting the data
```
X = encoded_df.drop('Attrition', axis=1)
y = encoded_df['Attrition']

# Split the data into training and testing sets (80% train, 20% test)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```
### Predictions and Evaluations
   ![image](https://github.com/mrnightmare666/IBM_HR_Analytics/assets/53763049/6d4eff5e-77cb-4fdb-9c24-0184ca2ea7e9)

The classification report shows:
- Precision: It measures the accuracy of positive predictions. For the class 'No', precision is 0.90, indicating that among all instances predicted as 'No', 90% are actually 'No'. For the class 'Yes', precision is 0.62, indicating that among instances predicted as 'Yes', 62% are actually 'Yes'.
- Recall (Sensitivity): It measures the proportion of actual positive instances that were correctly predicted. For the class 'No', recall is 0.97, meaning 97% of 'No' instances were correctly predicted. For the class 'Yes', recall is 0.33, indicating that only 33% of actual 'Yes' instances were predicted correctly.
- F1-score: It is the harmonic mean of precision and recall. It gives a balance between precision and recall. For the class 'No', the F1-score is 0.94, and for the class 'Yes', it is 0.43.
- Support: Indicates the number of actual occurrences of each class in the test dataset. There were 255 instances of 'No' and 39 instances of 'Yes'.
- Accuracy: Overall accuracy of the model on the test set is 0.88, meaning 88% of all predictions made by the model were correct.
- Macro Avg: It's the average of precision, recall, and F1-score across all classes, giving each class equal weight. In this case, it's 0.76 for precision, 0.65 for recall, and 0.68 for the F1-score.
- Weighted Avg: It's the weighted average of precision, recall, and F1-score, where each class's contribution is weighted by its support. For precision, recall, and F1-score, the weighted averages are 0.87, 0.88, and 0.87, respectively.

  Considering these metrics, the model might not be optimal, especially if correctly identifying employees who might leave ('Yes') is crucial for the business.

## Random Forest Model
Random Forest is a machine learning method that builds multiple decision trees and merges their predictions to make more accurate and robust conclusions.
It uses randomness and ensemble learning to improve accuracy and understand feature importance in the data.

- Feature Importance Using RF
![image](https://github.com/mrnightmare666/IBM_HR_Analytics/assets/53763049/976ee0fd-ce1b-4038-a5cb-99370d38bf10)



