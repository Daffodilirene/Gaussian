# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Enter the number of equations and the matrix values.
2. Make all values below the main diagonal equal to 0.
3. Find the values of the variables from the last equation to the first equation.
4. Print the values of all variables. 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Daffodil Irene S
RegisterNumber: 212225100006
*/

import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n=int(input())
a=np.zeros((n,n+1))
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio * a[i][k]
x=np.zeros(n)
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f" % (i,x[i]),end=" ")
```

## Output:
<img width="583" height="335" alt="600588602-004def7f-43bc-499c-91de-c95c5879da93" src="https://github.com/user-attachments/assets/2d53c19b-feb4-46ff-83e5-3775329482c9" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

