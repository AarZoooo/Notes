# UNIT 1

## Important Data Structures

### List
Mutable, flexible data structure. Data in it can be changed, hence its flexibility.

    [1, 2, 3, 4]
    
### Tuple
Immutable data structure used to represent fixed data. Once they are created, the data in a tuple can't be changed. A new tuple is needed in that case.

    (2, 4, 6, 8, 10)
    
### Dictionary
Unordered, Key-Value paired, Mutable data structure. Used to store data based on a key-value pair, and retrieval of value is done using its key. Keys are *unique*.

    {
    "John Doe" : 001,
    "Jane Smith" : 002,
    "Lorem Ipsum" : 003,
    }
    
### Set
Unordered, Mutable list of *Unique* elements. Used for storage of non-repeating data.

    {1, 2, 3, 4, 5}

## Important Libraries

### NumPy
Provides support for multidimensional arrays, mathematical functions, linear algebra operations, and random number generation.
    
### SciPy
Builds upon NumPy by offering additional functionality for optimization, interpolation, signal processing, statistical analysis, and more, making it a comprehensive library for scientific computing tasks.


## Root Finding Methods

### 1. Bisection Method
A numerical technique for finding roots of a continuous function within a given interval.

- The bisection method operates on the principle of repeatedly halving the interval containing the root until the interval becomes sufficiently small.
- It requires that the function changes sign over the interval, ensuring that a root exists within that interval.
- The method is guaranteed to converge to a root of the function as long as the function is continuous and changes sign over the interval.

**Process:**
1. **Initialization:** Start with an interval `[a, b]` where the function changes sign, i.e. `f(a) . f(b) < 0`

2. **Iteration:**
    - Compute the midpoint \(c\) of the interval: `c = (a + b) / 2.`
    - Evaluate the function `f(c)`
    - Update the interval:
        - If `f(c) = 0` or the width of the interval becomes smaller than a specified tolerance, consider `c` as the root.
        - If `f(c)` has the same sign as `f(a)`, update `a = c`.
        - If `f(c)` has the same sign as `f(b)`, update `b = c`.

3. **Termination:** Repeat the iteration until the desired level of accuracy is achieved or until a maximum number of iterations is reached.


### 2. Newton-Raphson Method
An iterative numerical technique for finding roots of a differentiable function. The method uses linear approximation to iteratively refine the estimate of the root until convergence is achieved.

- The Newton-Raphson method uses the derivative of the function to iteratively update the current estimate of the root.
- It typically converges faster than the bisection method by calculating tangent at a certain point on the curve, and moving on to intersection of the tangent and x-axis.
- However, the method may fail to converge, or may converge to a local minimum if the initial guess is far from the true root or if the function has complex behavior near the root.

**Process:**
1. **Initialization:** Start with an initial guess `x₀` for the root.

2. **Iteration:**
    - Compute the next approximation `xₙ₊₁` using the formula:

        `xₙ₊₁ = xₙ - (f(xₙ) / f'(xₙ))`

        where `f'(xₙ)` is the derivative of the function evaluated at `xₙ`.
    
    - What actually happens here is we draw a tangent on the curve at `x = x₀`, and move on to the intersection of the tangent and the x-axis.

    - Repeat this process until we reach the desired level of accuracy.

3. **Termination:** Stop iterating when the difference between successive approximations is smaller than a specified tolerance or after a maximum number of iterations.

### 3. Secant Method
Another iterative numerical technique for finding roots of a function. Unlike the Newton-Raphson method, the secant method does not require knowledge of the derivative of the function and approximates it using finite differences.

- The secant method uses two initial guesses to approximate the derivative of the function using finite differences.
- It iteratively updates the current estimate of the root based on the secant line connecting the function values at the two previous points.
- Like the Newton-Raphson method, the secant method may fail to converge if the initial guesses are poorly chosen or if the function has complex behavior near the root.

**Process:**
1. **Initialization:** Start with two initial guesses `x₀` and `x₁` for the root.

2. **Iteration:**
    - Compute the next approximation `xₙ₊₁` using the formula:

        `xₙ₊₁ = xₙ - f(xₙ) * (xₙ - xₙ₋₁) / (f(xₙ) - f(xₙ₋₁))`

    - Repeat this process until we reach the desired level of accuracy.

3. **Termination:** Stop iterating when the difference between successive approximations is smaller than a specified tolerance or after a maximum number of iterations.

