# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the necessary libraries and get input from the user
2. Use nested loops to iterate over each element of the matrix
3. Perform Gaussian elimination to solve the system of linear equations.
4. Use back Substitution and Print the output

## Program:
```python
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 
RegisterNumber: 
*/
import numpy as np
import sys
#Reading number of unknowns
n = int(input())

#Making numpy array of n x n+1 size and initializing
#to zero for storing augmented matrix
a = np.zeros((n,n+1))

#Making numpy array of n size and initializing
#to zero for storing solution matrix
x = np.zeros(n)

# Reading augmented matrix coefficients
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())

# Applying Gauss Elimination
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by Zero detected!')
    
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
            
# Back substitution
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    
    x[i] = x[i]/a[i][i]

# Displaying solution
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end = ' ')
```

## Output:
![Screenshot 2023-09-25 224826](https://github.com/S-ARVIND01/Gaussian/assets/118707337/3f68da1a-500d-45bb-9be2-8f34fb161599)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

