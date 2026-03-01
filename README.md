Experiment No. 9

Name: Pranav Menon

PRN No.: 25070123085

Batch: ENTC - B1

Aim:

To study the NumPy library in Python and understand array creation, attributes,
built-in functions, and their practical applications.

THEORY

1) Introduction to NumPy

NumPy, short for Numerical Python, is a powerful open-source library used for
numerical and scientific computing in Python. It provides support for
multi-dimensional arrays and matrices, along with a large collection of
mathematical functions to operate on them efficiently.

NumPy arrays are significantly faster and more memory-efficient than standard
Python lists. This is because all NumPy operations are executed in compiled C
code rather than interpreted Python, eliminating the overhead of Python loops
for element-wise operations. NumPy serves as the foundation for many other
scientific Python libraries including Pandas, SciPy, and Matplotlib.

NumPy must be imported before use. It is conventionally imported with the alias
np, which is a widely accepted and standard convention in the Python scientific
community.

Why use NumPy over Python Lists?

Python lists are general-purpose containers that can hold elements of different
types. This flexibility comes at the cost of speed and memory. NumPy arrays
are restricted to a single data type (homogeneous), which allows NumPy to store
and process data in a much more compact and efficient format using fixed-type
memory blocks. For large-scale numerical computation, the performance difference
between Python lists and NumPy arrays can be dramatic — often 10x to 100x faster.

Additionally, Python lists require explicit loops to perform element-wise
operations, while NumPy supports vectorized operations that work directly on the
entire array in a single command, making code concise and readable.

Key Characteristics:
• Homogeneous – All elements in a NumPy array must be of the same data type.
• Multi-dimensional – Supports 1D, 2D, and higher-dimensional arrays (ndarrays).
• Fast – Operations are performed in compiled C code, much faster than loops.
• Vectorized – Arithmetic operations apply to entire arrays without explicit loops.
• Memory Efficient – Uses less memory compared to Python lists for large datasets.
• Broadcasting – Scalar or smaller arrays are automatically expanded to match shape.
• Imported as: import numpy as np

Syntax:
import numpy as np
a = np.array([1, 2, 3])           # Creates a 1D array
b = np.array([[1,2,3],[4,5,6]])   # Creates a 2D array

Example:
a = np.array([1, 10, 20, 30, 40, 50, 500])
b = np.array([[1,2,3],[4,5,6],[7,8,9]])
print(a)   # Output: [  1  10  20  30  40  50 500]
print(b)   # Output: [[1 2 3] [4 5 6] [7 8 9]]

2) Array Attributes

Once a NumPy array is created, several built-in attributes allow inspection of
its structure and content without calling any function. These attributes are
properties of the ndarray object and are accessed using dot (.) notation
directly on the array variable.

a) ndim

Returns the number of dimensions of the array.
A 1D array has ndim = 1, a 2D array has ndim = 2, and so on.

Command: array.ndim
Example:
a.ndim → 1
b.ndim → 2

b) size

Returns the total number of elements in the array, regardless of its shape.
For a 3×3 array, size = 9. For a 1D array of 7 elements, size = 7.

Command: array.size
Example:
a.size → 7
b.size → 9

c) shape

Returns a tuple representing the dimensions of the array.
For a 2D array with 3 rows and 3 columns, shape = (3, 3).
For a 1D array with 7 elements, shape = (7,).

Command: array.shape
Example:
a.shape → (7,)
b.shape → (3, 3)

d) dtype

Returns the data type of the elements stored in the array.
Common types are int64 (for integer arrays) and float64 (for float arrays).
NumPy automatically infers dtype from input data and promotes to float64
if any element is a decimal/float value.

Command: array.dtype
Example:
a = np.array([1, 10, 20, 30])       → a.dtype = int64
a = np.array([1, 10, 20, 30.5])     → a.dtype = float64

3) Array Creation Functions

NumPy provides several built-in functions to create arrays with predefined
values or patterns. These eliminate the need to manually specify every element
and are especially useful for initialising arrays for computations.

a) np.zeros((r, c))

Creates an array of shape (r, c) filled entirely with 0.0.
Commonly used to initialise arrays before filling them with computed values.

Command: np.zeros((2, 3))
Output:
[[0. 0. 0.]
 [0. 0. 0.]]

b) np.ones((r, c))

Creates an array of shape (r, c) filled entirely with 1.0.
Used in operations that require a starting value of 1, such as scaling.

Command: np.ones((2, 3))
Output:
[[1. 1. 1.]
 [1. 1. 1.]]

c) np.eye(n)

Creates an n×n square identity matrix where diagonal elements are 1.0
and all other elements are 0.0. Identity matrices are fundamental in
linear algebra and matrix operations.

Command: np.eye(3)
Output:
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]

d) np.arange(start, stop, step)

Creates a 1D array with values from start up to (but not including) stop,
incremented by step. Similar to Python's built-in range() function but
returns a NumPy array instead of a list.

Command: np.arange(1, 10, 2)
Output: [1 3 5 7 9]

e) np.linspace(start, stop, n)

Creates a 1D array of n evenly spaced values between start and stop
(both inclusive). Unlike arange, linspace controls the number of points
rather than the step size. Ideal for generating smooth value ranges for
mathematical plotting and calculations.

Command: np.linspace(0, 1, 4)
Output: [0.         0.33333333 0.66666667 1.        ]

4) Vectorized Arithmetic Operations

One of NumPy's most powerful features is vectorization — the ability to apply
arithmetic operations directly to entire arrays element-by-element without
writing any explicit loops. This makes code cleaner, shorter, and significantly
faster for large datasets.

Standard Python arithmetic operators (+, -, *, /) work element-wise on
NumPy arrays. When an operation is performed between an array and a single
scalar value, the scalar is automatically stretched to match the shape of the
array. This mechanism is called broadcasting.

Broadcasting Rules:
- If a scalar is used with an array, the scalar is applied to every element.
- If two arrays of compatible shapes are used, the operation is done element-wise.
- This avoids the need to write any loops for standard mathematical operations.

Example:
a = np.array([1, 10, 20, 30, 40, 50, 500])
b = np.array([[1,2,3],[4,5,6]])

a + 5  → [  6  15  25  35  45  55 505]   (5 added to every element)
b * 2  → [[ 2  4  6][ 8 10 12]]           (every element multiplied by 2)

Other operations:
a - 1  → [  0   9  19  29  39  49 499]
b / 2  → [[0.5 1.0 1.5][2.0 2.5 3.0]]

5) Statistical Functions

NumPy provides a set of built-in statistical functions that operate across
all elements of an array. These functions enable quick descriptive analysis
of data directly within NumPy without requiring any additional libraries.
They accept the array as an argument and return a single computed value.

a) np.mean(a)
Returns the arithmetic mean (average) of all elements in the array.
Calculated as: sum of all elements divided by the total count of elements.

Example: np.mean([1,10,20,30,40,50,500]) → 93.0

b) np.median(a)
Returns the median value — the middle element when all values are arranged
in sorted order. For an even number of elements, it returns the average of
the two middle values. The median is useful as it is not affected by outliers.

Example: np.median([1,10,20,30,40,50,500]) → 30.0

c) np.max(a)
Returns the largest element present in the array.
Does not require the array to be sorted.

Example: np.max([1,10,20,30,40,50,500]) → 500

d) np.min(a)
Returns the smallest element present in the array.
Does not require the array to be sorted.

Example: np.min([1,10,20,30,40,50,500]) → 1

e) np.sum(a)
Returns the total sum of all elements in the array.
For multi-dimensional arrays, sums all elements across all axes by default.

Example: np.sum([1,10,20,30,40,50,500]) → 651

Summary Table:
Function       | Description                | Result (for array a)
np.mean(a)     | Arithmetic average         | 93.0
np.median(a)   | Middle value when sorted   | 30.0
np.max(a)      | Largest element            | 500
np.min(a)      | Smallest element           | 1
np.sum(a)      | Total of all elements      | 651

6) NumPy Data Types (dtype)

Every NumPy array has an associated data type (dtype) that determines how
each element is stored in memory. NumPy supports a wider range of data types
compared to standard Python. The most commonly encountered types are:

- int64   – 64-bit integer. Default type for arrays created from whole numbers.
- float64 – 64-bit floating point. Default type when any element is a decimal.
- bool    – Boolean type storing True or False values.
- complex – Complex numbers with real and imaginary parts.
- object  – Stores Python objects (used when elements are of mixed type).

NumPy automatically selects the most appropriate dtype when an array is
created. However, a specific dtype can also be specified manually using the
dtype parameter.

Example:
a = np.array([1, 2, 3])            → dtype = int64
b = np.array([1.0, 2.5, 3.7])      → dtype = float64
c = np.array([1, 2, 3.5])          → dtype = float64  (auto-promoted)
d = np.array([True, False, True])  → dtype = bool

Specifying dtype manually:
a = np.array([1, 2, 3], dtype=float64)   → dtype = float64

7) Array Indexing and Slicing

NumPy arrays support standard indexing and slicing similar to Python lists,
but extended to multiple dimensions.

1D Array Indexing:
a = np.array([1, 10, 20, 30, 40, 50, 500])
a[0]    → 1        (first element)
a[-1]   → 500      (last element)
a[1:4]  → [10, 20, 30]   (slice from index 1 to 3)
a[::2]  → [1, 20, 40, 500]  (every second element)

2D Array Indexing:
b = np.array([[1,2,3],[4,5,6],[7,8,9]])
b[0]       → [1, 2, 3]    (first row)
b[1][2]    → 6            (row 1, column 2)
b[0, 1]    → 2            (row 0, column 1 — shorthand notation)
b[:, 1]    → [2, 5, 8]    (all rows, column 1)
b[0:2, :]  → [[1,2,3],[4,5,6]]   (rows 0 and 1, all columns)

Understanding indexing is essential for accessing, modifying, and filtering
specific elements or sub-arrays within larger datasets.

Note on Negative Indexing:
NumPy supports negative indexing just like Python lists.
a[-1] returns the last element, a[-2] returns the second-to-last, and so on.
This is useful when the length of the array is not known in advance.

Note on Slicing:
Slicing in NumPy returns a view of the original array, not a copy.
This means modifying a slice will also modify the original array.
To create an independent copy, use array.copy().

Example:
a = np.array([1, 10, 20, 30, 40])
s = a[1:3]      # s = [10, 20] — this is a view
s[0] = 99       # modifies a as well → a = [1, 99, 20, 30, 40]
c = a[1:3].copy()   # c is an independent copy

8) Comparison of Python List vs NumPy Array

Feature              | Python List          | NumPy Array
---------------------|----------------------|----------------------
Data types           | Mixed allowed        | Homogeneous only
Speed                | Slower (interpreted) | Faster (compiled C)
Memory usage         | Higher               | Lower
Element-wise ops     | Requires loops       | Vectorized directly
Mathematical funcs   | Not built-in         | Fully built-in
Multi-dimensional    | Not native           | 1D, 2D, nD supported
Import required      | No                   | Yes (import numpy)

This makes NumPy the preferred choice for any numerical, scientific,
or data-heavy computation in Python.



ALGORITHMS

Algorithm 1: Array Declaration and Display

Step 1: Start
   - Begin array creation and display

Step 2: Import NumPy library
   - Command: import numpy as np
   - Function: import - Python keyword to load external module
   - Source: numpy library (import required)

Step 3: Create a 1D array
   - Command: a = np.array([1,10,20,30,40,50,500])
   - Function: np.array() - Creates a NumPy array from a list
   - Source: numpy library (import required)

Step 4: Create a 2D array
   - Command: b = np.array([[1,2,3],[4,5,6],[7,8,9]])
   - Function: np.array() - Creates a 2D NumPy array from nested lists
   - Source: numpy library (import required)

Step 5: Display both arrays
   - Command: print(a) ; print(b)
   - Function: print() - Built-in function for console output
   - Source: Built-in Python function (no import required)

Step 6: Stop
   - End the algorithm

Algorithm 2: Display Array Attributes

Step 1: Start
   - Begin attribute inspection

Step 2: Display number of dimensions
   - Command: print(a.ndim) ; print(b.ndim)
   - Function: .ndim - Attribute returning the number of array dimensions
   - Source: numpy ndarray attribute (import required)

Step 3: Display total number of elements
   - Command: print(a.size) ; print(b.size)
   - Function: .size - Attribute returning total element count
   - Source: numpy ndarray attribute (import required)

Step 4: Display shape of arrays
   - Command: print(a.shape) ; print(b.shape)
   - Function: .shape - Attribute returning tuple of array dimensions
   - Source: numpy ndarray attribute (import required)

Step 5: Display data type of array elements
   - Command: print(a.dtype) ; print(b.dtype)
   - Function: .dtype - Attribute returning element data type
   - Source: numpy ndarray attribute (import required)

Step 6: Stop
   - End the algorithm

Algorithm 3: Built-in Array Creation Functions

Step 1: Start
   - Begin demonstrating array creation functions

Step 2: Create a zero-filled array
   - Command: print(np.zeros((2,3)))
   - Function: np.zeros() - Creates array filled with 0.0
   - Source: numpy library (import required)

Step 3: Create a one-filled array
   - Command: print(np.ones((2,3)))
   - Function: np.ones() - Creates array filled with 1.0
   - Source: numpy library (import required)

Step 4: Create an identity matrix
   - Command: print(np.eye(3))
   - Function: np.eye() - Creates an identity matrix of given size
   - Source: numpy library (import required)

Step 5: Create arrays using arange and linspace
   - Command: print(np.arange(1,10,2)) ; print(np.linspace(0,1,4))
   - Function: np.arange() - Evenly spaced values by step
   - Function: np.linspace() - Evenly spaced values by count
   - Source: numpy library (import required)

Step 6: Stop
   - End the algorithm

Algorithm 4: Statistical Operations on Arrays

Step 1: Start
   - Begin statistical analysis on array

Step 2: Calculate mean of the array
   - Command: print(np.mean(a))
   - Function: np.mean() - Returns arithmetic mean of array elements
   - Source: numpy library (import required)

Step 3: Calculate median of the array
   - Command: print(np.median(a))
   - Function: np.median() - Returns median value of array elements
   - Source: numpy library (import required)

Step 4: Find maximum value
   - Command: print(np.max(a))
   - Function: np.max() - Returns the maximum element
   - Source: numpy library (import required)

Step 5: Find minimum value
   - Command: print(np.min(a))
   - Function: np.min() - Returns the minimum element
   - Source: numpy library (import required)

Step 6: Calculate sum of all elements
   - Command: print(np.sum(a))
   - Function: np.sum() - Returns the sum of all elements
   - Source: numpy library (import required)

Step 7: Stop
   - End the algorithm

Conclusion:

The study of the NumPy library in Python was successfully completed.
