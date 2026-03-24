# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by




## Program:
### Gram-Schmidt Method
```
import numpy as np
def QR_Decomposition(a):
    n,m=a.shape
    q=np.empty((n,m))
    u=np.empty((n,m))
    r=np.zeros((n,m))
    u[:,0]=a[:,0]
    q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=a[:,i]
        for j in range(n):
            u[:,i]-=(a[:,i]@q[:,j])*q[:,j]
        q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    for i in range(n):
        for j in range(i,m):
            r[i,j]=a[:,j]@q[:,i]
    print(f"The Q Matrix is\n {q}")
    print(f"The R Matrix is\n {r}")

a = np.array(eval(input()))
QR_Decomposition(a)
```








## Output
```
<img width="1285" height="632" alt="image" src="https://github.com/user-attachments/assets/008578bb-2a93-42d2-97fb-f639b2d71887" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
