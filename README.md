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

## Results
- PowerBI Dashboard for exploratary analysis
![image](https://github.com/mrnightmare666/IBM_HR_Analytics/assets/53763049/e6a824c1-011a-4954-9f51-2dd4c57e284d)

- Classification Report ( precision, recall, f1-score, support )
-   ![image](https://github.com/mrnightmare666/IBM_HR_Analytics/assets/53763049/6d4eff5e-77cb-4fdb-9c24-0184ca2ea7e9)




- Feature Importance Using RF
![image](https://github.com/mrnightmare666/IBM_HR_Analytics/assets/53763049/976ee0fd-ce1b-4038-a5cb-99370d38bf10)



