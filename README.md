# ECE-2112-PA-2

Jhan Gabriel V. Caragay | 2ECE-D

# A. REPRODUCIBLE NORMALIZATION PROBLEM

### **OBJECTIVE**



### **DISCUSSION**

We first import the Numerical Python library ```numpy```:

``` import numpy as np ```
> We rename it as ```np``` to make it shorter and more efficient.


### **OVERALL STRUCTURE**

```
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
X
```
```
array([[48, 11, 15, 67, 21],
       [11, 41, 13, 66, 24],
       [71, 79, 53, 67, 70],
       [77, 35, 91, 19, 96],
       [35, 54, 37, 41, 17]])
```
```
S = (np.std(X))
print(S)
```
```
25.864075471588002
```

```
M = (X.mean())
print(M)
```
```
46.36
```
```
X_normalized = (X-M)/S
X_normalized
```
```
array([[ 0.06340841, -1.36714726, -1.2124926 ,  0.79801809, -0.98051059],
       [-1.36714726, -0.20723725, -1.28981993,  0.75935442, -0.86451959],
       [ 0.95267275,  1.26198209,  0.25672675,  0.79801809,  0.91400909],
       [ 1.18465476, -0.43921926,  1.72594609, -1.05783793,  1.91926443],
       [-0.43921926,  0.29539042, -0.36189192, -0.20723725, -1.13516526]])
```
```
normalized_mean = np.mean(X_normalized)
print(normalized_mean)
```
```
0.0
```
```
normalized_std = np.std(X_normalized)
print(normalized_std)
```
```
0.9999999999999999
```






# B. CUBES DIVISIBLE BY 4 PROBLEM

### **OBJECTIVE**


### **DISCUSSION**


### **OVERALL STRUCTURE**



### **SAMPLE OUTPUT**

# C. ABOVE-MEAN SQUARES PROBLEM

### **OBJECTIVE**


### **DISCUSSION**


### **OVERALL STRUCTURE**



### **SAMPLE OUTPUT**

## **HISTORY**
**August 30, 2026** - Submitted the required .ipynb and .npy files.

**August 27, 2026** - Started the Readme file.
 
