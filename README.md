Experiment No. 9

Name: Pranav Menon

PRN No.: 25070123085

Batch: ENTC - B1

Aim: To study NumPy tool in Python and understand array creation, properties, built-in functions, and their applications.

THEORY:

1) Introduction to NumPy

NumPy (Numerical Python) is a library for numerical computing providing support for multi-dimensional arrays and mathematical operations. It is faster and more memory-efficient than Python lists.
Key Characteristics:
• Homogeneous – All elements must be of the same data type
• Multi-dimensional – Supports 1D, 2D, and nD arrays
• Vectorized – Operations apply to entire arrays without loops
• Rich Functions – Built-in statistical, algebraic, and array functions
Import: import numpy as np

2) Array Creation

Arrays are created using np.array() by passing a list or nested list.
- 1D Array: np.array([1,10,20,30]) → single-dimensional
- 2D Array: np.array([[1,2,3],[4,5,6]]) → matrix-like structure
Example: a = np.array([1,10,20,30,40,50,500]) | b = np.array([[1,2,3],[4,5,6],[7,8,9]])

3) Array Properties

- ndim – Number of dimensions (1 for 1D, 2 for 2D array)
- size – Total number of elements in the array
- shape – Tuple representing (rows, columns); e.g. (3,3) for a 3×3 array
- dtype – Data type of elements (int64, float64, etc.); float if any element is float

4) Built-in Array Creation Functions

- np.zeros((r,c)) – Array of all zeros with shape (r,c)
- np.ones((r,c)) – Array of all ones with shape (r,c)
- np.eye(n) – n×n identity matrix (1s on diagonal, 0s elsewhere)
- np.arange(start,stop,step) – Array of evenly spaced values (like range())
- np.linspace(start,stop,n) – Array of n evenly spaced values between start and stop

5) Array Arithmetic Operations

NumPy supports element-wise arithmetic directly on arrays without loops.
- Array + scalar: adds scalar to every element
- Array * scalar: multiplies every element by scalar
Example: a+5 → each element of a incremented by 5 | b*2 → each element doubled

6) Statistical Functions

NumPy provides built-in functions for statistical analysis on arrays:
- np.mean(a) – Arithmetic mean of all elements
- np.median(a) – Median value of the array
- np.max(a) – Maximum element
- np.min(a) – Minimum element
- np.sum(a) – Sum of all elements

ALGORITHMS

Algorithm 1: Declare and Display 1D and 2D Arrays
Step 1: Start
Step 2: Import NumPy
   - Command: import numpy as np
   - Function: import - imports the NumPy library
   - Source: NumPy library (pip install numpy / pre-installed in Colab)
Step 3: Create 1D array
   - Command: a = np.array([1,10,20,30,40,50,500])
   - Function: np.array() - Creates a NumPy array from a list
   - Source: NumPy library function (import numpy as np)
Step 4: Create 2D array
   - Command: b = np.array([[1,2,3],[4,5,6],[7,8,9]])
   - Function: np.array() - Creates a 2D NumPy array from nested list
   - Source: NumPy library function (import numpy as np)
Step 5: Display both arrays
   - Command: print(a) ; print(b)
   - Function: print() - Built-in function for console output
   - Source: Built-in Python function (no import required)
Step 6: Stop

Algorithm 2: Determine Dimensions of Arrays
Step 1: Start
Step 2: Print dimensions of 1D and 2D arrays
   - Command: print(a.ndim) ; print(b.ndim)
   - Function: .ndim - Array attribute returning number of dimensions
   - Source: NumPy array attribute (import numpy as np)
Step 3: Stop

Algorithm 3: Determine Size of Arrays
Step 1: Start
Step 2: Print total number of elements
   - Command: print(a.size) ; print(b.size)
   - Function: .size - Array attribute returning total number of elements
   - Source: NumPy array attribute (import numpy as np)
Step 3: Stop

Algorithm 4: Determine Shape of Arrays
Step 1: Start
Step 2: Print shape tuple of both arrays
   - Command: print(a.shape) ; print(b.shape)
   - Function: .shape - Array attribute returning (rows,cols) tuple
   - Source: NumPy array attribute (import numpy as np)
Step 3: Stop

Algorithm 5: Determine Data Type of Arrays
Step 1: Start
Step 2: Print dtype of integer arrays
   - Command: print(a.dtype) ; print(b.dtype)
   - Function: .dtype - Array attribute returning element data type
   - Source: NumPy array attribute (import numpy as np)
Step 3: Recreate array with a float element
   - Command: a = np.array([1,10,20,30.5,40,50,500])
   - Function: np.array() - float element causes entire array to be float64
   - Source: NumPy library function (import numpy as np)
Step 4: Print updated dtype
   - Command: print(a.dtype) ; print(b.dtype)
   - Function: .dtype - Returns float64 for a, int64 for b
   - Source: NumPy array attribute (import numpy as np)
Step 5: Stop

Algorithm 6: Built-in Array Creation Functions (zeros, ones, eye)
Step 1: Start
Step 2: Create and display 2x3 zeros array
   - Command: print(np.zeros((2,3)))
   - Function: np.zeros() - Creates array filled with 0.0
   - Source: NumPy library function (import numpy as np)
Step 3: Create and display 2x3 ones array
   - Command: print(np.ones((2,3)))
   - Function: np.ones() - Creates array filled with 1.0
   - Source: NumPy library function (import numpy as np)
Step 4: Create and display 3x3 identity matrix
   - Command: print(np.eye(3))
   - Function: np.eye() - Creates identity matrix with 1s on diagonal
   - Source: NumPy library function (import numpy as np)
Step 5: Stop

Algorithm 7: Built-in Functions (arange, linspace, arithmetic)
Step 1: Start
Step 2: Display arange sequences
   - Command: print(np.arange(1,10,2)) ; print(np.arange(1,11,2))
   - Function: np.arange(start,stop,step) - Generates evenly spaced values
   - Source: NumPy library function (import numpy as np)
Step 3: Display linspace sequence
   - Command: print(np.linspace(0,1,4))
   - Function: np.linspace(start,stop,n) - n evenly spaced values
   - Source: NumPy library function (import numpy as np)
Step 4: Scalar multiplication and addition on arrays
   - Command: print(b*2) ; print(a+5)
   - Function: * and + - Element-wise arithmetic operators on NumPy arrays
   - Source: NumPy operator overloading (import numpy as np)
Step 5: Stop

Algorithm 8: Statistical Functions on Arrays
Step 1: Start
Step 2: Calculate and display mean
   - Command: print(np.mean(a))
   - Function: np.mean() - Returns arithmetic mean of array elements
   - Source: NumPy library function (import numpy as np)
Step 3: Calculate and display median
   - Command: print(np.median(a))
   - Function: np.median() - Returns median value of array
   - Source: NumPy library function (import numpy as np)
Step 4: Calculate and display max and min
   - Command: print(np.max(a)) ; print(np.min(a))
   - Function: np.max() / np.min() - Returns maximum/minimum element
   - Source: NumPy library functions (import numpy as np)
Step 5: Calculate and display sum
   - Command: print(np.sum(a))
   - Function: np.sum() - Returns sum of all array elements
   - Source: NumPy library function (import numpy as np)
Step 6: Stop

CONCLUSION

The study of NumPy tool in Python was successfully completed.
