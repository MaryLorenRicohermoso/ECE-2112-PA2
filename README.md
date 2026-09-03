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

`• np.mean()` – calculates the arithmetic mean of all the elements in the array.

Example: 

          `X_mean = np.mean(X)`

`• np.std()` – calculates the standard deviation of the array. The default std() calculation is used, which gives the population standard deviation required by the problem.

Example: 

          `X_std = np.std(X)`

The mean is subtracted from every element of X, and the result is divided by the standard deviation. NumPy performs these operations directly on the entire array without using a loop.

Example: 

          `X_normalized = (X - X_mean) / X_std`

The complete code for this problem is:

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

The normalized array should have a mean approximately equal to 0 and a standard deviation approximately equal to 1, with small differences possible because of floating-point rounding. 


---
