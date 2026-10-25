# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Input matrix dimensions and initialize augmented matrix and solution vector. 
2. Populate the augmented matrix with user inputs.
3. Perform Gaussian elimination to reduce the matrix to upper triangular form, ensuring no division by zero.
4. Back substitute to compute solution values for the variables.
5. Print the solution vector formatted to two decimal places

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 
RegisterNumber: 
*/
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range (n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range (n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
X[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range (n-2,-1,-1):
    X[i]=a[i][n]
    for j in range(i+1,n):
        X[i]=X[i]-a[i][j]*X[j]
    X[i]=X[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f ' %(i,X[i]),end= '')
```

## Output:
![gaussian elimination]()
<img width="1441" height="867" alt="Screenshot 2026-10-25 163033" src="https://github.com/user-attachments/assets/b69d652c-e7a4-49cc-b2c0-f285696fd7fe" />
<img width="1327" height="385" alt="Screenshot 2026-10-25 163059" src="https://github.com/user-attachments/assets/4e97c5fe-e476-427e-954d-ae8d516bd2e4" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

