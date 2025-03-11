# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import the standard Libraries.
2.Set variables for assigning dataset values.
3.Import linear regression from sklearn.
4.Assign the points for representing in the graph.
5.Predict the regression for marks by using the representation of the graph.
6.Compare the graphs and hence we obtained the linear regression for the given datas.
```
## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: R.Priyanga
RegisterNumber:  212223230161
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error,mean_squared_error
df=pd.read_csv('student_scores.csv')
print(df)
df.head(0)
df.tail(0)
print(df.head())
print(df.tail())
x = df.iloc[:,:-1].values
print(x)
y = df.iloc[:,1].values
print(y)
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(x_train,y_train)
y_pred = regressor.predict(x_test)
print(y_pred)
print(y_test)
#Graph plot for training data
plt.scatter(x_train,y_train,color='black')
plt.plot(x_train,regressor.predict(x_train),color='blue')
plt.title("Hours vs Scores(Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
#Graph plot for test data
plt.scatter(x_test,y_test,color='black')
plt.plot(x_train,regressor.predict(x_train),color='red')
plt.title("Hours vs Scores(Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
mse=mean_absolute_error(y_test,y_pred)
print('MSE = ',mse)
mae=mean_absolute_error(y_test,y_pred)
print('MAE = ',mae)
rmse=np.sqrt(mse)
print("RMSE= ",rmse)
```

## Output:

DATA SET
![image](https://github.com/user-attachments/assets/b044d2ed-ea03-4601-a2a9-8e42a7f030b8)
HEAD SET
![image](https://github.com/user-attachments/assets/35b77e54-0550-448e-a54a-eb42c0567c70)
TAIL VALUES
![image](https://github.com/user-attachments/assets/be8bd8c9-7ebe-4206-b509-654db186b002)
X AND Y VALUES
![image](https://github.com/user-attachments/assets/6444e10b-b710-42e3-8589-aa7b70bfa1cd)
Prediction values of X and Y
![image](https://github.com/user-attachments/assets/631ee3e7-dafa-47f1-aed7-da8b98c53be7)
MSE,MAE and RMSE
![image](https://github.com/user-attachments/assets/4e4cb48b-0c3e-44f5-8d0f-4b268c2349f8)
Training set
![image](https://github.com/user-attachments/assets/e4b32180-baf3-4826-98ce-55cc603d04d2)
Testing set
![image](https://github.com/user-attachments/assets/6cf0486a-0dbe-47be-9e24-98f5e6c0143d)

## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
