# Algorithm for QR Decomposition

## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.

## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner.

## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)

## Program:
### Gram-Schmidt Method
```
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    
    Q= np.empty((n, n))
    u= np.empty((n, n))
    
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
            a
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
        
    R = np.zeros((n,m))    
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print("The Q matrix is \n",Q)
    print("The R matrix is \n",R)
a = np.array(eval(input()))
QR_Decomposition(a)
```
```
Program developed by Vignesh J and Register Number : 212225230297
```

## Output
```
 ([[1,1,0],[1,0,1],[0,1,1]])
The Q matrix is 
 [[ 0.70710678  0.40824829 -0.57735027]
 [ 0.70710678 -0.40824829  0.57735027]
 [ 0.          0.81649658  0.57735027]]
The R matrix is 
 [[1.41421356 0.70710678 0.70710678]
 [0.         1.22474487 0.40824829]
 [0.         0.         1.15470054]]
```
<img width="1203" height="914" alt="Screenshot 2026-03-23 212710" src="https://github.com/user-attachments/assets/08f89cbf-3a37-4704-85e8-4449c73016c0" />

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
