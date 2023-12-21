# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of equations n.
Initialize matrix matrix and solution vector x.

2. Use nested loops to input coefficients into the augmented matrix.

3. For each pivot row, eliminate coefficients below the diagonal by subtracting a multiple of the pivot row.

4. Starting from the last row, solve for variables backward using the updated matrix.

5. Print the solution vector x with a formatted message for each variable.
## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: T.Ajay
RegisterNumber: 23007325
'''

import numpy as np
import sys
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
    if matrix[i][j]==0.0:
        sys.exit("Divide by zero error")
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")

```

## Output:
![image](https://github.com/Ajayreddy-2006/Gaussian/assets/145742508/5b976a7d-4073-4adb-9232-d70b3d63cd57)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

