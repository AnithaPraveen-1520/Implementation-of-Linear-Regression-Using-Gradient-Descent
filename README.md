# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1. **Start** and import the required libraries: Pandas, NumPy, and Matplotlib.
2. Load the `50_Startups.csv` dataset and extract the **R&D Spend** and **Profit** columns.
3. Normalize the input and output data by calculating their mean and standard deviation.
4. Initialize slope, intercept, learning rate, and epochs, then calculate gradients and update the slope and intercept using **Gradient Descent**.
5. Calculate the final slope and intercept, and predict the profit for an R&D expenditure of 100000.
6. Display the slope, intercept, and predicted profit, plot the regression line with actual data points, and **stop**.

## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by:  Anitha P
RegisterNumber: 212225040022

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt


data = pd.read_csv('50_Startups.csv')


X = data['R&D Spend'].values
Y = data['Profit'].values

X_mean, X_std = X.mean(), X.std()
Y_mean, Y_std = Y.mean(), Y.std()

X = (X - X_mean) / X_std
Y = (Y - Y_mean) / Y_std


m = 0
c = 0
lr = 0.01
epochs = 10000
n = len(X)

# Gradient Descent
for i in range(epochs):
    Y_pred = m * X + c

    dm = (-2/n) * np.sum(X * (Y - Y_pred))
    dc = (-2/n) * np.sum(Y - Y_pred)

    m = m - lr * dm
    c = c - lr * dc

slope = m * Y_std / X_std
intercept = Y_mean + c * Y_std - slope * X_mean

spend = 100000
profit = slope * spend + intercept

print("Slope:", round(slope, 2))
print("Intercept:", round(intercept, 2))
print("Predicted Profit:", round(profit, 2))


plt.scatter(data['R&D Spend'], data['Profit'], label='Actual Profit')
plt.plot(data['R&D Spend'],
         slope * data['R&D Spend'] + intercept,
         color='red', label='Regression Line')

plt.xlabel('R&D Spend')
plt.ylabel('Profit')
plt.title('Simple Linear Regression using Gradient Descent')
plt.legend()
plt.show()



*/
```

## Output:
<img width="1723" height="588" alt="image" src="https://github.com/user-attachments/assets/535ac505-6042-427f-860f-756544d8d1db" />



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
