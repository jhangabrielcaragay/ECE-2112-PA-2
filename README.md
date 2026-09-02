# ECE-2112-PA-2

Jhan Gabriel V. Caragay | 2ECE-D

This programming assignment uses Numerical Python (NumPy) and consists of three problems that demonstrate different numerical operations and array manipulation techniques.

We first import the Numerical Python library ```numpy```:

```python
import numpy as np
```
> We rename it as ```np``` to make it shorter and more efficient.

This should be done first because the remaining code in all three problems relies on functions and operations provided by the numpy library.

# A. REPRODUCIBLE NORMALIZATION PROBLEM

### **OBJECTIVE**

The first problem requires creating a reproducible 5 × 5 integer array, **X**, using a fixed random seed, then normalizing all 25 elements using their mean and population standard deviation. The normalized array is stored as X_normalized and saved as a .npy file.

### **DISCUSSION**

We first insert the following two statements before performing any calculation:

```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```
> This creates a random 5x5 array that will be used later in part A.

Calling the array will yield this result:
```python
X
array([[48, 11, 15, 67, 21],
       [11, 41, 13, 66, 24],
       [71, 79, 53, 67, 70],
       [77, 35, 91, 19, 96],
       [35, 54, 37, 41, 17]])
```

The **Standard Deviation**  of ```array X``` will next be computed using the following code:
```python
S = (np.std(X))
print(S)
```
> We assign ```S``` the value of the standard deviation calculated from ```array X```.


This will then yield:
```python
25.864075471588002
```


The **Mean** of ```array X``` will next be computed using the following code:
```python
M = (X.mean())
print(M)
```
> We assign ```M``` the value of the Mean calculated from ```array X```.

This will then yield:
```python
46.36
```

We now combine our gathered data to solve for the ```X_normalized``` using the following code:
```
X_normalized = (X-M)/S
```
> Where ```X``` represents the 5 × 5 random integer ndarray, ```M``` represents the **Mean**, and ```S``` represents the **Standard Deviation**.

Entering ```X_normalized``` will yield this result:
```python
array([[ 0.06340841, -1.36714726, -1.2124926 ,  0.79801809, -0.98051059],
       [-1.36714726, -0.20723725, -1.28981993,  0.75935442, -0.86451959],
       [ 0.95267275,  1.26198209,  0.25672675,  0.79801809,  0.91400909],
       [ 1.18465476, -0.43921926,  1.72594609, -1.05783793,  1.91926443],
       [-0.43921926,  0.29539042, -0.36189192, -0.20723725, -1.13516526]])
```

With the data above, we then compute the ```normalized_mean``` using the code:
```python
normalized_mean = np.mean(X_normalized)
print(normalized_mean)
```
> This line of code gets the **mean** of the ```x_normalized```.

```python print(normalized_mean)``` yields the result:
```python
0.0
```
> This is in line with the programming assignment's requirement that the normalized mean **must** be ```0```.

Next, we compute for the ```normalized_std``` using the code:
```python
normalized_mean = np.mean(X_normalized)
print(normalized_mean)
```
> This line of code gets the **Standard Deviation** of the ```x_normalized```.

```print(normalized_std)``` yields the result:
```python
0.9999999999999999
```
> This is in line with the programming assignment's requirement that the normalised Standard Deviation **must** be ```1```.

Lastly, we save the normalized array as ```X_normalized.npy``` using the code:
```python
np.save("X_normalized.npy", X_normalized)
```
> It is saved under the filename X_normalized.npy.

### **OVERALL STRUCTURE**

```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
X

array([[48, 11, 15, 67, 21],
       [11, 41, 13, 66, 24],
       [71, 79, 53, 67, 70],
       [77, 35, 91, 19, 96],
       [35, 54, 37, 41, 17]])
```
```python
S = (np.std(X))
print(S)

25.864075471588002
```

```python
M = (X.mean())
print(M)

46.36
```

```python
X_normalized = (X-M)/S
X_normalized

array([[ 0.06340841, -1.36714726, -1.2124926 ,  0.79801809, -0.98051059],
       [-1.36714726, -0.20723725, -1.28981993,  0.75935442, -0.86451959],
       [ 0.95267275,  1.26198209,  0.25672675,  0.79801809,  0.91400909],
       [ 1.18465476, -0.43921926,  1.72594609, -1.05783793,  1.91926443],
       [-0.43921926,  0.29539042, -0.36189192, -0.20723725, -1.13516526]])
```

```python
normalized_mean = np.mean(X_normalized)
print(normalized_mean)

0.0
```

```python
normalized_std = np.std(X_normalized)
print(normalized_std)

0.9999999999999999

```

```python
np.save("X_normalized.npy", X_normalized)
```


# B. CUBES DIVISIBLE BY 4 PROBLEM

### **OBJECTIVE**

The second problem requires creating a **10 × 10 NumPy array** containing the cubes of the first **100 positive** integers. A Boolean condition is then used to select all cubed values divisible by ```4```, which are stored in ```div_by_4``` and saved as a ```.npy``` file.

### **DISCUSSION**

We first create an array containing the first **100 positive integers**, reshape it into a **10 × 10 array**, and cube each value using the following code:

```python
C = np.arange(1,101).reshape(10,10) ** 3
```

```python
np.arange(1,101)
```

> This was used to generate the integers from 1 up to 100.

```python
.reshape(10,10)
```

> This was used to reshape the values into a 10 × 10 array.

```python
** 3
```

> This was used to **cube** each value in the array.

In order to make the array fit inside the 10x10 requirement, it used the code:

```python
np.set_printoptions(linewidth=300)
```
> This was used to expand the print width so that the ```10 × 10 array``` can be displayed more neatly without unnecessary line breaks. 

Printing the value for ```C``` will yield the result:

```python
[[      1       8      27      64     125     216     343     512     729    1000]
 [   1331    1728    2197    2744    3375    4096    4913    5832    6859    8000]
 [   9261   10648   12167   13824   15625   17576   19683   21952   24389   27000]
 [  29791   32768   35937   39304   42875   46656   50653   54872   59319   64000]
 [  68921   74088   79507   85184   91125   97336  103823  110592  117649  125000]
 [ 132651  140608  148877  157464  166375  175616  185193  195112  205379  216000]
 [ 226981  238328  250047  262144  274625  287496  300763  314432  328509  343000]
 [ 357911  373248  389017  405224  421875  438976  456533  474552  493039  512000]
 [ 531441  551368  571787  592704  614125  636056  658503  681472  704969  729000]
 [ 753571  778688  804357  830584  857375  884736  912673  941192  970299 1000000]]

```
Next, in order to get the size of the array's dimension, it used the code:

```python
C.shape
```
Which yields the result:
```python
(10, 10)
```
Next, we let ```div_by_4``` use a Boolean condition on ```C``` to select every cubed value that is divisible by ```4```. The selected values are kept in NumPy's normal row-major order. 
```python
div_by_4 = C[C % 4 == 0]
```
```python
[C % 4 == 0]
```
> ```C % 4``` gets the remainder when each value is divided by ```4```, while ```== 0``` checks if the remainder is **zero**. This selects only the values in ```C``` that are divisible by ```4```. 

```python
C
```
> ```C``` was placed before the Boolean condition to apply the condition to every element in the array and select the values that satisfy it.

Entering ```div_by_4``` will yield out:

```python
array([      8,      64,     216,     512,    1000,    1728,    2744,    4096,    5832,    8000,   10648,   13824,   17576,   21952,   27000,   32768,   39304,   46656,   54872,   64000,   74088,   85184,   97336,  110592,  125000,  140608,  157464,  175616,  195112,  216000,  238328,  262144,
        287496,  314432,  343000,  373248,  405224,  438976,  474552,  512000,  551368,  592704,  636056,  681472,  729000,  778688,  830584,  884736,  941192, 1000000])
```
> This is in line with the programming assignment's requirement that the first number is ```8``` and the last is `1,000,000`.

Next, we will check for the number of elements inside the array using the code:
```python
div_by_4.size
```
This yields out:
```python
50
```
> This is in line with the programming assignment's requirement that the it should have a result of `50` solutions.

Lastly, we save the array as ```div_by_4.npy``` using the code:
```python
np.save("div_by_4", div_by_4)
```
> It is saved under the filename `div_by_4.npy`.


### **OVERALL STRUCTURE**
```python
C = np.arange(1,101).reshape(10,10) ** 3
np.set_printoptions(linewidth=300)
print(C)

[[      1       8      27      64     125     216     343     512     729    1000]
 [   1331    1728    2197    2744    3375    4096    4913    5832    6859    8000]
 [   9261   10648   12167   13824   15625   17576   19683   21952   24389   27000]
 [  29791   32768   35937   39304   42875   46656   50653   54872   59319   64000]
 [  68921   74088   79507   85184   91125   97336  103823  110592  117649  125000]
 [ 132651  140608  148877  157464  166375  175616  185193  195112  205379  216000]
 [ 226981  238328  250047  262144  274625  287496  300763  314432  328509  343000]
 [ 357911  373248  389017  405224  421875  438976  456533  474552  493039  512000]
 [ 531441  551368  571787  592704  614125  636056  658503  681472  704969  729000]
 [ 753571  778688  804357  830584  857375  884736  912673  941192  970299 1000000]]

```
```python
C.shape

(10, 10)
```
```python
div_by_4 = C[C % 4 == 0]
div_by_4

array([      8,      64,     216,     512,    1000,    1728,    2744,    4096,    5832,    8000,   10648,   13824,   17576,   21952,   27000,   32768,   39304,   46656,   54872,   64000,   74088,   85184,   97336,  110592,  125000,  140608,  157464,  175616,  195112,  216000,  238328,  262144,
        287496,  314432,  343000,  373248,  405224,  438976,  474552,  512000,  551368,  592704,  636056,  681472,  729000,  778688,  830584,  884736,  941192, 1000000])
```
```python
div_by_4.size

50
```
```python
np.save("div_by_4", div_by_4)
```

# C. ABOVE-MEAN SQUARES PROBLEM

### **OBJECTIVE**

The third problem requires creating a **6 × 6 NumPy array** containing the squares of the first **36 positive** integers. The mean of the array is then calculated and used as a Boolean condition to select only the values strictly greater than the mean. These values are stored in ```above_mean``` and saved as a ```.npy``` file.

### **DISCUSSION**

We first started by creating a ```6 x 6 ndarray``` named ```S``` that lists the first `36 positive integers` using the code:

```python
S = np.arange(1,37).reshape(6,6) ** 2
```
```python
np.arange(1,37)
```
> This is used to generate the integers from `1` up to `36`.

```python
.reshape(6,6)
```
> This is used to reshape the values into a `6 × 6 array`.
```python
** 2
```
> This is used to `square` each value in the array.

Next, we need to compute the `mean` of all the values in `S` and assign the result to `S_mean`.

```python
S_mean = (S.mean())
```
In order to see the result, we print it using the code:
```python
print(S_mean)
```
This code yields the result:
```python
450.1666666666667
```

Next, we let `above_mean` have the values in `S` that are strictly greater than `S_mean` using the code:
```python
above_mean = S[S > S_mean]
```
> The condition `S > S_mean` checks which values in `S` are greater than the calculated mean and selects only those values.

In order to see the results, we print them out using the code:
```python
print(above_mean)
```
Which yields the result:
```python
[ 484  529  576  625  676  729  784  841  900  961 1024 1089 1156 1225 1296]
```
> This is in line with the programming assignment's requirement that the first is `484` and the last is `1296`. 


Next, we check for the number of elements of the `mean` using the code:
```python
above_mean.size
```

This yields:
```python
15
```

Lastly, we save the array as ```above_mean.npy``` using the code:
```python
np.save("above_mean.npy",above_mean)
```
> It is saved under the filename `above_mean.npy`.


### **OVERALL STRUCTURE**
```python
S = np.arange(1,37).reshape(6,6) ** 2
S

array([[   1,    4,    9,   16,   25,   36],
       [  49,   64,   81,  100,  121,  144],
       [ 169,  196,  225,  256,  289,  324],
       [ 361,  400,  441,  484,  529,  576],
       [ 625,  676,  729,  784,  841,  900],
       [ 961, 1024, 1089, 1156, 1225, 1296]])
```
```python
S_mean = (S.mean())
print(S_mean)

450.1666666666667
```
```python
above_mean = S[S > S_mean]
print(above_mean)

[ 484  529  576  625  676  729  784  841  900  961 1024 1089 1156 1225 1296]
```
```python
above_mean.size

15
```

```python
np.save("above_mean.npy",above_mean)
```


## **HISTORY**

**September 2, 2026** - Beautified the README.md file.

**August 31, 2026** - Finalized the README.md file.

**August 30, 2026** - Submitted the required .ipynb and .npy files.

**August 27, 2026** - Started the Readme file.
 
