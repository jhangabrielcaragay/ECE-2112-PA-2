# ECE-2112-PA-2

Jhan Gabriel V. Caragay | 2ECE-D

This programming assignment uses Numerical Python (NumPy) and consists of three problems that demonstrate different numerical operations and array manipulation techniques.

We first import the Numerical Python library ```numpy```:

``` import numpy as np ```
> We rename it as ```np``` to make it shorter and more efficient.

This should be done first because the remaining code in all three problems relies on functions and operations provided by the numpy library.

# A. REPRODUCIBLE NORMALIZATION PROBLEM

### **OBJECTIVE**

The first problem requires creating a reproducible 5 × 5 integer array, **X**, using a fixed random seed, then normalizing all 25 elements using their mean and population standard deviation. The normalized array is stored as X_normalized and saved as a .npy file.

### **DISCUSSION**

We first insert the following two statements before performing any calculation:

```
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```
> This creates a random 5x5 array that will be used later in part A.

Calling the array will yield this result:
```
X
array([[48, 11, 15, 67, 21],
       [11, 41, 13, 66, 24],
       [71, 79, 53, 67, 70],
       [77, 35, 91, 19, 96],
       [35, 54, 37, 41, 17]])
```

The **Standard Deviation**  of ```array X``` will next be computed using the following code:
```
S = (np.std(X))
print(S)
```
> We assign ```S``` the value of the standard deviation calculated from ```array X```.


This will then yield:
```
25.864075471588002
```


The **Mean** of ```array X``` will next be computed using the following code:
```
M = (X.mean())
print(M)
```
> We assign ```M``` the value of the Mean calculated from ```array X```.

This will then yield:
```
46.36
```

We now combine our gathered data to solve for the ```X_normalized``` using the following code:
```
X_normalized = (X-M)/S
```
> Where ```X``` represents the 5 × 5 random integer ndarray, ```M``` represents the **Mean**, and ```S``` represents the **Standard Deviation**.

Entering ```X_normalized``` will yield this result:
```
array([[ 0.06340841, -1.36714726, -1.2124926 ,  0.79801809, -0.98051059],
       [-1.36714726, -0.20723725, -1.28981993,  0.75935442, -0.86451959],
       [ 0.95267275,  1.26198209,  0.25672675,  0.79801809,  0.91400909],
       [ 1.18465476, -0.43921926,  1.72594609, -1.05783793,  1.91926443],
       [-0.43921926,  0.29539042, -0.36189192, -0.20723725, -1.13516526]])
```

With the data above, we then compute the ```normalized_mean``` using the code:
```
normalized_mean = np.mean(X_normalized)
print(normalized_mean)
```
> This line of code gets the **mean** of the ```x_normalized```.

```print(normalized_mean)``` yields the result:
```
0.0
```
> This is in line with the programming assignment's requirement that the normalized mean **must** be ```0```.

Next, we compute for the ```normalized_std``` using the code:
```
normalized_mean = np.mean(X_normalized)
print(normalized_mean)
```
> This line of code gets the **Standard Deviation** of the ```x_normalized```.

```print(normalized_std)``` yields the result:
```
0.9999999999999999
```
> This is in line with the programming assignment's requirement that the normalised Standard Deviation **must** be ```1```.

Lastly, we save the normalized array as ```X_normalized.npy``` using the code:
```
np.save("X_normalized.npy", X_normalized)
```
> It is saved under the filename X_normalized.npy.

### **OVERALL STRUCTURE**

```
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
X

array([[48, 11, 15, 67, 21],
       [11, 41, 13, 66, 24],
       [71, 79, 53, 67, 70],
       [77, 35, 91, 19, 96],
       [35, 54, 37, 41, 17]])
```
```
S = (np.std(X))
print(S)

25.864075471588002
```

```
M = (X.mean())
print(M)

46.36
```

```
X_normalized = (X-M)/S
X_normalized

array([[ 0.06340841, -1.36714726, -1.2124926 ,  0.79801809, -0.98051059],
       [-1.36714726, -0.20723725, -1.28981993,  0.75935442, -0.86451959],
       [ 0.95267275,  1.26198209,  0.25672675,  0.79801809,  0.91400909],
       [ 1.18465476, -0.43921926,  1.72594609, -1.05783793,  1.91926443],
       [-0.43921926,  0.29539042, -0.36189192, -0.20723725, -1.13516526]])
```

```
normalized_mean = np.mean(X_normalized)
print(normalized_mean)

0.0
```

```
normalized_std = np.std(X_normalized)
print(normalized_std)

0.9999999999999999

```

```
np.save("X_normalized.npy", X_normalized)
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
 
