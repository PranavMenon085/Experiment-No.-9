Experiment No. 9

Name: Pranav Menon

PRN No.: 25070123085

Batch: ENTC - B1

Aim: To study NumPy tool in Python and understand array creation, properties, built-in functions, and their applications.

────────────────────────────────────────────────────────────────

THEORY

────────────────────────────────────────────────────────────────

1) Introduction to NumPy

NumPy (Numerical Python) is a powerful open-source library for numerical computing in Python.
It provides support for multi-dimensional arrays and a wide range of mathematical operations.
Compared to regular Python lists, NumPy arrays are significantly faster in execution and more
efficient in memory usage, making it the preferred choice for scientific and data-related
computing tasks.

NumPy is widely used in fields such as data science, machine learning, signal processing,
image processing, and scientific simulations. It serves as the foundation for many other
Python libraries including Pandas, SciPy, Matplotlib, and TensorFlow.

Import Statement:
    import numpy as np

────────────────────────────────────────────────────────────────

Key Characteristics:

  - Homogeneous: All elements in a NumPy array must belong to the same data type, such
    as all integers or all floats. This uniformity enables efficient storage in memory.

  - Multi-dimensional: NumPy supports arrays of any dimension, including 1D (vectors),
    2D (matrices), 3D tensors, and higher-dimensional arrays, making it versatile for
    complex numerical applications.

  - Vectorized: Mathematical operations are applied directly to entire arrays at once,
    eliminating the need for explicit Python loops. This vectorization makes computations
    much faster and the code more readable and concise.

  - Rich Built-in Functions: NumPy includes a large collection of built-in functions for
    statistical analysis, linear algebra, Fourier transforms, random number generation,
    array manipulation, and more.

  - Memory Efficiency: Unlike Python lists, NumPy arrays store data in contiguous blocks
    of memory with a fixed data type, which reduces overhead and speeds up access.

  - Interoperability: NumPy arrays integrate seamlessly with other scientific libraries,
    databases, and file formats such as CSV, HDF5, and binary files.

────────────────────────────────────────────────────────────────

2) Array Creation

NumPy arrays are created using the np.array() function by passing a Python list or a
nested list as input. Arrays can also be created using a variety of built-in functions
that generate arrays with specific patterns or values.

  a) 1D Array:
     A one-dimensional array is created by passing a simple flat list.
     Example:
         a = np.array([1, 10, 20, 30, 40, 50, 500])
     This creates a single-dimensional array containing seven integer elements.
     It behaves like a mathematical vector.

  b) 2D Array:
     A two-dimensional array is created by passing a nested list, where each inner
     list represents one row.
     Example:
         b = np.array([[1, 2, 3],
                       [4, 5, 6],
                       [7, 8, 9]])
     This creates a 3×3 matrix-like structure with three rows and three columns.

  c) 3D Array:
     A three-dimensional array can be created by nesting lists to another level.
     Example:
         c = np.array([[[1, 2], [3, 4]],
                       [[5, 6], [7, 8]]])
     This creates a 2×2×2 array, commonly used in image processing and tensor
     operations.

Both 1D and 2D arrays can be displayed on the console using Python's print() function.

────────────────────────────────────────────────────────────────

3) Array Properties

Every NumPy array has a set of built-in attributes that provide information about its
structure and content. These properties are accessed using dot notation on the array object.

  - ndim:
    Returns the number of dimensions of the array.
    A 1D array returns 1, a 2D array returns 2, and so on.
    Usage: a.ndim, b.ndim
    Example output: 1 (for array a), 2 (for array b)

  - size:
    Returns the total number of elements present in the array, regardless of shape.
    For example, a 3×3 array has a size of 9.
    Usage: a.size, b.size

  - shape:
    Returns a tuple that describes the structure of the array in terms of rows and
    columns (and further dimensions if applicable).
    For example, a 3×3 array returns (3, 3). A 1D array of 7 elements returns (7,).
    Usage: a.shape, b.shape

  - dtype:
    Returns the data type of the elements stored in the array, such as int64 or float64.
    If all elements are integers, the dtype is int64. However, if even one element is a
    decimal value (e.g., 30.5), NumPy automatically upgrades the dtype of the entire
    array to float64. This is called type promotion.
    Usage: a.dtype, b.dtype

  - itemsize:
    Returns the size in bytes of each element in the array.
    For int64, itemsize = 8 bytes. For float32, itemsize = 4 bytes.
    Usage: a.itemsize

  - nbytes:
    Returns the total number of bytes consumed by all elements in the array.
    It equals size × itemsize.
    Usage: a.nbytes

────────────────────────────────────────────────────────────────

4) Built-in Array Creation Functions

NumPy provides several ready-made functions to create arrays with standard values or
patterns. These are especially useful in mathematical, scientific, and engineering
computations where specific initial arrays are required.

  - np.zeros((r, c)):
    Creates an array of shape (r × c) where every element is 0.0.
    Example: np.zeros((2, 3)) creates a 2-row, 3-column array filled with zeros.
    Use case: Initializing weight matrices in machine learning.

  - np.ones((r, c)):
    Creates an array of shape (r × c) where every element is 1.0.
    Example: np.ones((2, 3)) creates a 2-row, 3-column array filled with ones.
    Use case: Creating mask arrays or bias initialization.

  - np.eye(n):
    Creates an n×n identity matrix, where diagonal elements are 1 and all others are 0.
    Example: np.eye(3) creates a 3×3 identity matrix.
    Use case: Linear algebra operations and solving systems of equations.

  - np.full((r, c), value):
    Creates an array of shape (r × c) filled entirely with a specified constant value.
    Example: np.full((3, 3), 7) creates a 3×3 matrix filled with 7.

  - np.arange(start, stop, step):
    Generates an array of evenly spaced values starting from 'start' up to (but not
    including) 'stop', with a gap of 'step' between values.
    Example: np.arange(1, 10, 2) produces [1, 3, 5, 7, 9].
    Use case: Generating index arrays or iteration sequences.

  - np.linspace(start, stop, n):
    Generates an array of exactly n evenly spaced values between 'start' and 'stop',
    including both endpoints.
    Example: np.linspace(0, 1, 5) produces [0.0, 0.25, 0.5, 0.75, 1.0].
    Use case: Generating smooth intervals for plotting graphs or simulations.

  - np.random.rand(r, c):
    Creates an array of shape (r × c) filled with random float values between 0 and 1,
    sampled from a uniform distribution.
    Example: np.random.rand(2, 3) generates a 2×3 matrix of random values.

  - np.random.randint(low, high, size):
    Creates an array of given size with random integers in the range [low, high).
    Example: np.random.randint(1, 100, (3, 3)) generates a 3×3 matrix of random integers.

────────────────────────────────────────────────────────────────

5) Array Arithmetic Operations

NumPy supports element-wise arithmetic operations directly on arrays through operator
overloading. Mathematical operators like +, -, *, and / work on every element of the
array simultaneously, without the need for any explicit loop.

Examples:
    b * 2     → Multiplies every element of array b by 2.
    a + 5     → Adds 5 to every element of array a.
    a - 3     → Subtracts 3 from every element.
    b / 2     → Divides every element by 2.
    b ** 2    → Raises every element to the power of 2.
    b % 3     → Returns the remainder when each element is divided by 3.


────────────────────────────────────────────────────────────────

6) Array Indexing and Slicing

NumPy arrays support both indexing (accessing a single element) and slicing (accessing
a range of elements).

  - 1D Indexing:     a[0] returns the first element; a[-1] returns the last.
  - 1D Slicing:      a[1:4] returns elements from index 1 to 3 (inclusive).
  - 2D Indexing:     b[1][2] or b[1, 2] accesses row 1, column 2.
  - 2D Slicing:      b[0:2, 1:3] returns a submatrix of rows 0-1 and columns 1-2.

────────────────────────────────────────────────────────────────

7) Array Manipulation Functions

NumPy provides functions to reshape, flatten, transpose, and combine arrays.

  - np.reshape(a, (r, c)):  Changes the shape of an array without altering its data.
  - np.flatten():           Converts a multi-dimensional array into a 1D array.
  - np.transpose(b):        Swaps rows and columns of a 2D array (matrix transpose).
  - np.concatenate():       Joins two or more arrays along an existing axis.
  - np.sort(a):             Returns a sorted copy of the array in ascending order.

────────────────────────────────────────────────────────────────

8) Statistical Functions

NumPy provides a set of built-in statistical functions that allow quick analysis of
data stored in arrays. These are heavily used in data analysis and scientific computing.

  - np.mean(a):    Calculates and returns the arithmetic mean (average) of all elements.
  - np.median(a):  Returns the median value (middle value when elements are sorted).
  - np.max(a):     Returns the largest element present in the array.
  - np.min(a):     Returns the smallest element present in the array.
  - np.sum(a):     Returns the total sum of all elements in the array.
  - np.std(a):     Returns the standard deviation, measuring spread of values.
  - np.var(a):     Returns the variance of the array elements.

────────────────────────────────────────────────────────────────

9) Linear Algebra with NumPy

NumPy includes the np.linalg module for performing linear algebra operations.

  - np.dot(a, b):            Computes the dot product of two arrays/matrices.
  - np.linalg.det(b):        Computes the determinant of a square matrix.
  - np.linalg.inv(b):        Computes the inverse of a square matrix.
  - np.linalg.eig(b):        Returns the eigenvalues and eigenvectors of a matrix.
  - np.linalg.norm(a):       Returns the Euclidean norm (magnitude) of a vector.
  - np.linalg.solve(A, b):   Solves the linear equation Ax = b for x.

────────────────────────────────────────────────────────────────

10) Practical Applications of NumPy

  - Data Analysis: NumPy arrays serve as the core data structure for analyzing large
    datasets, computing statistics, and preparing data for visualization.

  - Image Processing: Digital images are stored as 2D or 3D NumPy arrays (height ×
    width × color channels). Filters, transformations, and augmentations are applied
    using array operations.

  - Machine Learning: Feature matrices, weight vectors, activation functions, and
    gradient computations in neural networks are all handled with NumPy operations.

  - Signal Processing: Sensor data, audio waveforms, and time-series signals are
    represented as 1D NumPy arrays and processed using FFT and filtering functions.

  - Scientific Simulations: Physical simulations involving differential equations,
    particle systems, and numerical integration rely heavily on NumPy's speed and
    mathematical capabilities.

────────────────────────────────────────────────────────────────

CONCLUSION

The study of the NumPy tool in Python was successfully completed. Various concepts
including array creation (1D, 2D, 3D), array properties (ndim, size, shape, dtype,
itemsize, nbytes), built-in creation functions (zeros, ones, eye, arange, linspace,
full, random), arithmetic operations, broadcasting, array indexing and slicing,
array manipulation, statistical functions, and linear algebra operations were
thoroughly understood and implemented.

NumPy proves to be an essential and highly efficient library for numerical computing.
Its vectorized operations, memory-efficient storage, and rich mathematical functions
make it far superior to standard Python lists for scientific and engineering tasks.
The knowledge gained through this experiment forms the foundation for further work
in data science, machine learning, and scientific computing using Python.
