# ECE-2112-PA2

Ricohermoso, Mary Loren P. | 2ECE-B

This repository contains the Programming Assignment 2 for "Advance Computer Programming" this A.Y. 2026-2027. This covers three python problems referring to Module 2- Numpy. The problems focus on creating and reshaping NumPy arrays, performing vectorized numerical operations, using Boolean conditions for filtering, computing array statistics, and saving NumPy arrays as .npy files. 

## A. Reproducible Normalization Problem

Create a reproducible random 5 × 5 integer NumPy array named X. The array is normalized using its mean and population standard deviation. The resulting normalized array is stored in X_normalized. 

The following functions and methods were used in this problem:

`• np.random.seed()` – sets the seed for NumPy's random number generator. This makes the generated random values reproducible, meaning the same values will be generated every time the code is executed with the same seed.

Example: 

 `np.random.seed(2112)`

`• np.random.randint()` – generates random integers within a specified range. In this problem, integers from 10 to 100 are generated and arranged into a 5 × 5 array.

Example: 

 `X = np.random.randint(10, 101, size=(5, 5))`

`• .mean()` – calculates the arithmetic mean of all the elements in the array.

Example: 

 `mean = float(X.mean()) ---> 46.36`

`• .std()` – calculates the standard deviation of the array. The default std() calculation is used, which gives the population standard deviation required by the problem.

Example: 

 `std = float (X.std()) ---> 25.8640`

The Normalization formula was then applied to every element of the array. The mean is substracted from each value of x, and the result is divided by the standard deviation

Example: 

 `X_normalized = (X - X_mean()) / X_std()`


The resulting array is stored in the variable `X_normalized`. This uses NumPy's vectorized array operations, allowing the calculation to be performed on all elements without using a Python loop. 


The normalized mean and standard deviation were then checked using `.mean()` and `.std()` :

Example:

  `print ("Normalized mean: ", X_normalized.mean()) ---> Normalized Mean: 0.0
          print ("Normalized Standard Deviation: ", X_normalized.std())`


`•np.save` - used to save the normalized array as a NumPy `.npy` file. The required filename for this problem is `X_normalized.npy`.

Example:

 `np.save("X_normalized.npy", X_normalized)`

Combining all these operations, the code used for this is: 

```python
import numpy as np

np.random.seed(2112)

X = np.random.randint(10, 101, size=(5, 5))

X_mean = np.mean(X)
X_std = np.std(X)

X_normalized = (X - X_mean) / X_std

print("X:")
print(X)

print("\nX_normalized:")
print(X_normalized)

print("\nMean:", np.mean(X_normalized))
print("Standard Deviation:", np.std(X_normalized))

np.save("X_normalized.npy", X_normalized)
```


## B. Cubes Divisible by 4 Problem

Create an array containing the first 100 positive integers, cube every element, and reshape the result into a 10 × 10 NumPy array named C. A Boolean condition is then used to select every cubed value that is divisible by 4. The selected values are stored in div_by_4. 

The following functions and methods were used in this problem:

`• np.arange()` – function used to create a sequence of numbers. np.arange(1,101) generates the integers from 1 to 100 because the ending value 101 is not included.

Example: 

          `integers = np.arange(1,101)`
          

`• ** 3` – the exponentiation operator was used to cube every element of the integers array.

          `cubes = integers ** 3`


`• .reshape()` – an array method used to change the shape of an array. The 100 cubed values were reshaped into a 10 × 10 array named C.

Example: 

          `C = cubes.reshape(10, 10)
          print("Shape of C:", C.shape) --->
          Shape of C: (10, 10)`

`• Boolean indexing` – was used to filter the array and select only the values divisible by 4. The modulo operator % determines the remainder after division. Therefore, C % 4 == 0 identifies the elements whose remainder is zero when divided by 4.

Example: 

          `div_by_4 = C[C % 4 == 0]
          print("Selected array div by 4:\n", div_by_4) --->
          starts with 8 and ends with 1000000`

          
`• np.save()` -   used to save the selected values as div_by_4.npy.

          `np.save("div_by_4.npy", div_by_4)`

These operations were combined to construct the function:

```Phython
integers = np.arange (1,101)
integers

cubes = integers ** 3
C = cubes.reshape (10, 10)
print ("Shape of C:", C.shape)

div_by_4 = C[C % 4 == 0]

print ("Selected array div by 4:\n", div_by_4)
np.save("div_by_4.npy",div_by_4)
```

## C. Above-Mean Squares Problem


