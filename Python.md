# UNIT 1

## Python Syntax

For syntax you can go to **Python Cheatsheet** [(link)](https://www.pythoncheatsheet.org/cheatsheet/basics), it has every possible python syntax. Adding syntax to the notes was a bit irrelevant to me as it can be read anywhere.

## Important Data Structures

### List
Mutable, **flexible** data structure. Data in it can be changed, hence its flexibility.

    [1, 2, 3, 4]
    
### Tuple
**Immutable** data structure used to represent fixed data. Once they are created, the data in a tuple can't be changed. A new tuple is needed in that case.

    (2, 4, 6, 8, 10)
    
### Dictionary
Unordered, **Key-Value paired**, Mutable data structure. Used to store data based on a key-value pair, and retrieval of value is done using its key. Keys are *unique*.

    {
    "John Doe" : 001,
    "Jane Smith" : 002,
    "Lorem Ipsum" : 003,
    }
    
### Set
Unordered, Mutable list of **Unique** elements. Used for storage of non-repeating data.

    {1, 2, 3, 4, 5}

## Important Libraries

### NumPy
Provides support for multidimensional arrays, mathematical functions, linear algebra operations, and random number generation.
    
### SciPy
Builds upon NumPy by offering additional functionality for optimization, interpolation, signal processing, statistical analysis, and more, making it a comprehensive library for scientific computing tasks.


## Root Finding Methods

### 1. Bisection Method
A numerical technique for finding roots of a continuous function within a given interval.

- The bisection method operates on the principle of narrowing down the search space for the root by iteratively halving the interval in which the root lies.
- It starts with an initial interval where the function changes sign, indicating that the root is somewhere within that interval.
- By repeatedly halving the interval and selecting the subinterval where the function changes sign, the method narrows down the search space until the width of the interval becomes sufficiently small.


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

- It starts with an initial guess for the root and then computes the slope of the tangent line to the function at that point.
- The method then finds the point where this tangent line intersects the x-axis, which provides a new, hopefully more accurate, estimate of the root.
- By iteratively updating the estimate using this process, the method converges towards the root.

**Process:**
1. **Initialization:** Start with an initial guess `x₀` for the root.

2. **Iteration:**
    - Compute the next approximation `xₙ₊₁` using the formula:

        `xₙ₊₁ = xₙ - { f(xₙ) / f'(xₙ) }`

        where `f'(xₙ)` is the derivative of the function evaluated at `xₙ`.
    
    - What actually happens here is we draw a tangent on the curve at `x = x₀`, and move on to the intersection of the tangent and the x-axis. Then we continue with the new point.

    - Repeat this process until we reach the desired level of accuracy.

3. **Termination:** Stop iterating when the difference between successive approximations is smaller than a specified tolerance or after a maximum number of iterations.

### 3. Secant Method
Another iterative numerical technique for finding roots of a function. Unlike the Newton-Raphson method, the secant method does not require knowledge of the derivative of the function and approximates it using finite differences.

**Algorithm**

- You start with two initial guesses, let's call them `x₀` and `x₁`.
- You calculate the slope of the line between the points `(x₀, f(x₀))` and `(x₁, f(x₁))`.
- You extend that line until it intersects the x-axis, giving you a new guess `x₂` for the root.
- Then you repeat the process with the new guess and the last guess (so, `x₁` becomes the old guess, and you calculate a new guess based on `x₂` and `x₁`).

**Process:**
1. **Initialization:** Start with two initial guesses `x₀` and `x₁` for the root.

2. **Iteration:**
    - Compute the next approximation `xₙ₊₁` using the formula:

        `xₙ₊₁ = xₙ - { f(xₙ) * (xₙ - xₙ₋₁) / (f(xₙ) - f(xₙ₋₁)) }`

    - What happens here is we take two initial guesses, and draw a line between the two points where these two guesses intersect the curve respectively. Then we extend that line to intersect the x-axis. That becomes our new point.

    - Repeat this process until we reach the desired level of accuracy.

3. **Termination:** Stop iterating when the difference between successive approximations is smaller than a specified tolerance or after a maximum number of iterations.

---

