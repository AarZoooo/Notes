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
    - Compute the midpoint of the interval: `c = (a + b) / 2.`
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

<br>

# UNIT 2

## Interpolation and Curve Fitting

**Interpolation:**  We construct a curve through the given data points. In doing so, we make the implicit assumption that the data points are accurate and distinct.

**Curve Fitting:**  It is applied to data that contain scatter (noise), usually caused by measurement errors. Here we want to find a smooth curve that approximates the data in some sense. Thus the curve does not necessarily hit the data points.

<img src = "https://image.slidesharecdn.com/me4010ch5curvefitting-200910162259/85/numerical-methods-curve-fitting-and-interpolation-2-320.jpg?cb=1668102346" height = 300>

This image illustrates the difference between the two terms.

## Polynomial Interpolation

### For data in Equal Intervals

#### Newton Forward

$p = \frac{x - x_0}{h}$

$y(x) = y_0 + \frac{p}{1!} . \Delta ^1 y_0 + \frac{p(p - 1)}{2!} . \Delta ^2 y_0 + \frac{p(p - 1)(p - 2)}{3!} . \Delta ^3 y_0 + ...$

<br>

>**Question:** Find $y$ for $x = 1895$ using Newton's Forward Difference formula for the given table:

<table>
<tr>
<th>x</th>
<th>f(x)</th>
</tr>
<tr>
<td>1891</td>
<td>46</td>
</tr>
</tr>
<tr>
<td>1901</td>
<td>66</td>
</tr>
</tr>
<tr>
<td>1911</td>
<td>81</td>
</tr>
</tr>
<tr>
<td>1921</td>
<td>93</td>
</tr>
</tr>
<tr>
<td>1931</td>
<td>101</td>
</tr>
</table>

**Solution:** To solve, we need to calculate the Newton's forward difference table.

<img src = "https://qph.cf2.quoracdn.net/main-qimg-a0f3262e4e343da05b76ed7a9ea35763">

Now, $h = x_1 - x_0 = 10$

$p = \frac{x - x_0}{h} = \frac{1895 - 1891}{10} = 0.4$

Now, we know $y(x) = y_0 + \frac{p}{1!} . \Delta ^1 y_0 + \frac{p(p - 1)}{2!} . \Delta ^2 y_0 + \frac{p(p - 1)(p - 2)}{3!} . \Delta ^3 y_0 + ...$

$y(1895) = 46 + 0.4 (20) + \frac{0.4(0.4 - 1)}{2} (-5) + \frac{0.4(0.4 - 1)(0.4 - 2)}{6} (2) + \frac{0.4(0.4 - 1)(0.4 - 2)(0.4 - 3)}{24} (-3)$

$y(1895) = 46 + 8 + 0.6 + 0.128 + 0.1248 = 54.8528$ (Answer)

---

#### Newton Backward

$p = \frac{x - x_n}{h}$

$y(x) = y_n + \frac{p}{1!} . \nabla ^1 y_n + \frac{p(p + 1)}{2!} . \nabla ^2 y_n + \frac{p(p + 1)(p + 2)}{3!} . \nabla ^3 y_n + ...$

---

### For data in Unequal Intervals

#### Lagrange's method

The simplest form of an interpolant is a polynomial. It is always possible to construct
a unique polynomial of degree $n$ that passes through $n + 1$ distinct data points.

$y = P_n(x) = \sum _{i = 0} ^n y_i l_i (x)$

where:
- $n$ denotes the degree of the polynomial
- $l_i = \frac{x - x_0}{x_i - x_0} . \frac{x - x_1}{x_i - x_1} . \frac{x - x_2}{x_i - x_2} ... \frac{x - x_n}{x_i - x_n}$
  
  where $i = 1, 2, 3 ... n$

<br>


>**Question:** Find the value of $y$ at $x = 0$ given some set of values $(-2, 5), (1, 7), (3, 11), (7, 34)$.

**Solution:** Given values are,
<table>
<tr>
<th>x</th>
<td>-2</td>
<td>1</td>
<td>3</td>
<td>7</td>
</tr>
<tr>
<th>y</th>
<td>5</td>
<td>7</td>
<td>11</td>
<td>34</td>
</tr>
</table>

As we are given $4$ sets of data, $n = 4$

We need to find $y$ for $x = 0$

Therefore:

$y = y_0 l_0(x) + y_1 l_1(x) + y_2 l_2(x) + y_3 l_3(x)$

Now,

$l_0 = \frac{x - x_1}{x_0 - x_1} . \frac{x - x_2}{x_0 - x_2} . \frac{x - x_3}{x_0 - x_3} = \frac{(0-1)(0-3)(0-7)}{(-2-1)(-2-3)(-2-7)} = \frac{21}{135}$

$l_1 = \frac{x - x_0}{x_1 - x_0} . \frac{x - x_2}{x_1 - x_2} . \frac{x - x_3}{x_1 - x_3} = \frac{(0+2)(0-3)(0-7)}{(1+2)(1-3)(1-7)} = \frac{42}{36}$

$l_2 = \frac{x - x_0}{x_2 - x_0} . \frac{x - x_1}{x_2 - x_1} . \frac{x - x_3}{x_2 - x_3} = \frac{(0+2)(0-1)(0-7)}{(3+2)(3-1)(3-7)} = \frac{14}{-40}$

$l_3 = \frac{x - x_0}{x_3 - x_0} . \frac{x - x_1}{x_3 - x_1} . \frac{x - x_2}{x_3 - x_2} = \frac{(0+2)(0-1)(0-3)}{(7+2)(7-1)(7-3)} = \frac{6}{216}$

Therefore,

$y = \frac{21}{27} + \frac{49}{6} + \frac{-77}{20} + \frac{51}{54} = \frac{1087}{180}$ (Answer)

## Polynomial Curve Fitting

Polynomial curve fitting is a mathematical technique used to approximate a relationship between two variables using a polynomial function.

Here are some common applications of polynomial curve fitting:
1. **Data Modeling**: Polynomial curve fitting is often used to model data when there is a suspected polynomial relationship between variables. It can be used to describe and predict data trends.

2. **Interpolation and Extrapolation**: It's used to estimate data points within a given range (interpolation) or outside the observed data range (extrapolation) using a polynomial function.

3. **Function Approximation**: In engineering and physics, polynomial curve fitting is used to approximate complex functions with simpler polynomial functions for ease of analysis.

4. **Signal Processing**: Polynomial curve fitting can be applied in signal processing to smooth data and remove noise from signals.

5. **Regression Analysis**: It's used for polynomial regression, where a polynomial function is fitted to data to make predictions.

6. **Scientific Research**: Polynomial curve fitting is applied in various scientific disciplines to model and analyze experimental data.

### Least Squares fitting of Straight Line

>**Question:** Using the method of least square, find the best fitting straight line for the given data:

    x  | 1 | 2 | 3 | 4 | 5 |
    ---+---+---+---+---+---+
    y  | 1 | 3 | 5 | 6 | 5 |

**Solution:** Let the straight line be: $y = a + bx ---- (1)$

Multiplying x in both sides, we get: $xy = ax + bx^2 ---- (2)$

<br>

Performing Summation in equation (1) and (2):

$\sum y = na + b \sum x  ---- (3)$

$\sum xy = a \sum x + b \sum x^2  ---- (4)$

<br>

    x  |  y  |  xy  |  x^2  |
    ---+-----+------+-------+
    1  |  1  |  1   |   1   |
    2  |  3  |  6   |   4   |
    3  |  5  |  15  |   9   |
    4  |  6  |  24  |   16  |
    5  |  5  |  25  |   25  |

- $\sum x = 15$
- $\sum y = 20$
- $\sum xy = 71$
- $\sum x^2 = 55$

So the equations become:

$20 = 5a + 15b$

$71 = 15a + 55b$

<br>

Solving these equations, we get:
- $a = 0.7$
- $b = 1.1$

<br>

Therefore our curve becomes:

$y = 0.7 + 1.1x$ (Answer)



### Least Squares fitting of a $2^{nd}$ degree Parabola

>**Question:** Fit the parabola $y = a + bx + cx^2$ for the following data. Also find `y` when `x = 6`.

    x  |  0   1    2    3    4  |
    ---+------------------------+
    y  |  1  1.8  1.9  2.5  6.3 |

**Solution:** Let the equation of the parabola be: $y = a + bx + cx^2$

Its normal equation is:

$\sum y = na + b \sum x + c \sum x^2$ --- (1)

<br>

Multiplying $x$ in both sides - once and twice, the other two normal equations are:

$\sum xy = a \sum x + b \sum x^2 + c \sum x^3$ --- (2)

$\sum x^2 y = a \sum x^2 + b \sum x^3 + c \sum x^4$ --- (3)

    x  |  y  |  x^2  |  x^3  |  x^4  |  xy   |  x^2 * y  |
    ---+-----+-------+-------+-------+-------+-----------+
    0  |  1  |   0   |   0   |   0   |  0    |     0     |
    1  | 1.8 |   1   |   1   |   1   |  1.8  |    1.8    |  
    2  | 1.9 |   4   |   8   |   10  |  3.8  |    7.6    |
    3  | 2.5 |   9   |  27   |   81  |  7.5  |    22.5   |
    4  | 6.3 |   16  |  64   |  256  |  25.2 |   100.8   |

$\sum x = 10$

$\sum y = 13.5$

$\sum x^2 = 30$

$\sum x^3 = 100$

$\sum x^4 = 354$

$\sum xy = 38.3$

$\sum x^2 y = 132.7$

The equations become:

$13.5 = 5a + 10b + 30c$

$38.3 = 10a + 30b + 100c$

$132.7 = 30a + 100b + 354c$

Rest is solving these equations and putting the values into the curve.

<br>

## Numerical Integration

Numerical integration methods can generally be described as combining evaluations of the integrand to get an approximation to the integral. The integrand is evaluated at a finite set of points called integration points and a weighted sum of these values is used to approximate the integral.

### Trapezoidal Rule

Trapezoidal Rule is a rule that evaluates the area under the curves by dividing the total area into smaller trapezoids rather than using rectangles. This integration works  by approximating the region under the graph of a function as a trapezoid, and it calculates the area. This rule takes the average of the left and the right sum.

<img src = "https://cdn1.byjus.com/wp-content/uploads/2021/06/Trapezoidal-rule.png" height = 400>

<br>

**Formula:** Let $y = f(x)$ be a continuous function on the interval $[a, b]$.

Next we divide the interval into $n$ subsequent parts. Thus width of each part is:

$\Delta x = \frac{b - a}{n}$

where:
- $x_0 < x_1 < x_2 < ... < x_{n-1} < x_n $
- $a = x_0$
- $b = x_n$

Therefore the area is given by:

$\int _a ^b f(x) dx \approx T_n = \frac{\Delta x}{2} (y_0 + 2y_1 + 2y_2 + ... + 2y_{n - 1} + y_n)$

where: $x_i = a + i (\Delta x)$

>**Note:** It is applicable on any number of intervals.

<br>

>**Example:** Approximate the area under the curve $y = f(x)$ between $x = 0$ and $x = 8$ using Trapezoidal Rule with $n = 4$ subintervals. A function $f(x)$ is given in the table of values.

<table>
<tr>
<th>x</th>
<th>f(x)</th>
</tr>
<tr>
<td>0</td>
<td>3</td>
</tr>
<tr>
<td>2</td>
<td>7</td>
</tr>
<tr>
<td>4</td>
<td>11</td>
</tr>
<tr>
<td>6</td>
<td>9</td>
</tr>
<tr>
<td>8</td>
<td>3</td>
</tr>
</table>

**Solution:** The Trapezoidal Rule formula for $n = 4$ subintervals is given as:

$T_4 = \frac{\Delta x}{2} \{ f(x_0) + 2f(x_1) + 2f(x_2) + 2f(x_3) + f(x_4) \}$

Here, $\Delta x = 2$

Therefore, $A \approx T_4 = \frac{2}{2} (3 + 14 + 22 + 18 + 3) = 60$

So the approximate area under the curve using Trapezoidal rule is **60** (Answer).

---

### Simpson's $\frac{1}{3}$ Rule

Simpson's $\frac{1}{3}$ Rule is a numerical method that approximates the value of a definite integral by using quadratic functions.

<img src = "https://math24.net/images/simpsons-rule1.svg" height = 400 style = "background:white">

**Formula:** To obtain an approximation of the definite integral $\int ^b _a f(x) dx$ using Simpson's Rule, we partition the interval $[a, b]$ into an **even** number of $n$ subintervals.

Width of each part $\Delta x = \frac {b - a}{n}$.

On each pair of consecutive subintervals $[x_{i - 1}, x_i], [x_i, x_{i + 1}]$, we consider a quadratic function $y = ax^2 + bx + c$ such that it passes through the points:
- $(x_{i - 1}, f(x_{i - 1}))$
- $(x_{i}, f(x_{i}))$
- $(x_{i + 1}, f(x_{i + 1}))$

Therefore,

$\int ^b _a f(x) dx \approx \frac{\Delta x}{3} \{ y_0 + 4y_1 + 2y_2 + 4y_3 + 2y_4 + ... + 4y_{n - 1} + y_n \}$

The coefficients have the following pattern:

$\underbrace {1,4,2,4,2, \ldots ,4,2,4,1}_{{n + 1}\;\text{points}}$

We can also write the formula as:

$\int _a ^b f(x) dx \approx \frac{\Delta x}{3} [ \{ y_0 + y_n \} + 2\{ y_2 + y_4 + y_6 + ... \} + 4 \{ y_1 + y_3 + y_5 + ... \} ]$

>**Note:** This rule is applicable for even number of intervals.

<br>

>**Example:** A function $f(x)$ is given by the table of values. Approximate the area under the curve $y = f(x)$ between $x = 0$ and $x = 4$ using Simpson's $\frac{1}{3}$ Rule with $n = 4$ subintervals.

<img src = "https://math24.net/images/simpsons-rule4.svg" width = 300 style = "background:white">

**Solution:** For $n = 4$ subintervals, Simpson's rule is given by the following equation:

$S_4 = \frac{\Delta x}{3} \{ f(x_0) + 4f(x_1) + 2f(x_2) + 4f(x_3) + f(x_4) \}$

Here, width of each subinterval is:

$\Delta x = \frac {b - a}{n} = \frac {4 - 0}{4} = 1$

Substituting values into the equation, we get:

$A \approx S_4 = \frac {1}{3} [2 + 28 + 24 + 40 + 5] = \frac{1}{3} . 99 = 33$ (Answer)

<br>

---

### Simpson's $\frac{3}{8}$ Rule

It is completely based on the cubic interpolation rather than the quadratic interpolation.

**Formula:** Simpson’s 3/8 or three-eight rule is given by:

$\int _a ^b f(x) dx = \frac{3 \Delta x}{8} [(y_0 + y_n) + 3(y_1 + y_2 + y_4 + y_5 + …. + y_{n-1}) + 2(y_3 + y_6 + y_9 + ….. + y_{n-3})]$

>**Note:** This rule is applicable where the number of intervals is a multiple of 3.

>**Note:** Simpson's rule provides a more accurate value than Trapezoidal rule as it uses Quadratic Approximation instead of Linear Approximation.

---

### Gaussian Quadrature

The Gauss integration is a very efficient method to perform numerical integration over intervals. In fact, if the function to be integrated is a polynomial of an appropriate egree, then the Gauss integration scheme produces exact results.

<img src = "https://www.12000.org/my_courses/UCI_COURSES/CREDIT_COURSES/spring_2006/spring_MAE_207/other_class_documents/Nasser_Abbasi/numerical_integration/images/d2.svg" style = "background:white">

<br>

**Formula:** Gauss quadrature aims to find the **least** number of fixed points to approximate the integral of a function $f:[a, b]$ such that:

$I=\int _{a} ^b f (x) dx \approx \sum _{i=1} ^n c_i f(x_i)$

where:
- $1 \leq i \leq n$, where $n$ is the number of parts
- Associated weight, $c_i = \frac {b - a}{n}$
- Integration point, $x_i \in [a : b]$

<br>

> **Example:** For the given integral:
>$$\int _{0.1} ^{1.3} 5xe^{-2x} dx$$
>- Use the two-point Gauss quadrature rule to estimate the value of the integral
>- Find the true error
>- Find the absolute relative error

**Solution:** The two-point Gauss quadrature rule is given by:

$\int _a ^b f(x) dx \approx c_1 f_1(x) + c_2 f_2 (x)$\

## Ordinary Differential Equations

An ordinary differential equation (also abbreviated as ODE), in Mathematics, is an
equation which consists of one or more functions of one independent variable along
with their derivatives.

### Types
The ordinary differential equation is further classified into three types. They
are:
- **Autonomous ODE**

  A differential equation which does not depend on the variable, say x is known as an autonomous differential equation.

- **Linear ODE**

  If differential equations can be written as the linear combinations of the derivatives of y, then they are called linear ordinary differential equations.

  These can be further classified into two types:

    - Homogeneous linear differential equations
    - Non-homogeneous linear differential equations

- **Non-linear ODE**

  If the differential equations cannot be written in the form of linear combinations of the derivatives of y, then it is known as a non-linear ordinary differential equation.

---

### Euler's Rule

The Euler’s method is a first-order numerical procedure for solving ordinary differential equations (ODE) with a given initial value.

**General Formula:** 

$y_{i + 1} = y_i + hf(x_i, y_i)$

where:
- $y_{i + 1}$ is the next estimated value
- $y_i$ is the current value
- $h$ is the interval between steps
- $f(x_i, y_i)$ is the value of the derivative at the current $(x_i, y_i)$ point.

<br>

>**Example:** Find $y(0.2)$ for $y' = x - y^2$, $y(0) = 1$, with step length $0.1$ using Euler method.

**Solution:** Given:
- $y' = x - y^2$
- $y(0) = 1$
- $h = 0.1$

We need to find the value of $y(0.2)$.

Applying Euler's method:

$y_1 = y_0 + hf(x_0, y_0)$

$y_1 = 1 + (0.1)f(0, 1)$

$y_1 = 1 + (0.1)(-1)$

$y_1 = 0.99$

<br>

$y_2 = y_1 + hf(x_1, y_1)$

$y_2 = 0.99 + (0.1)f(0.1, 0.99)$

$y_2 = 0.99 + (0.1)(-0.8801)$

$y_2 = 0.90199$

<br>

Therefore, $y_2 = y(0.2) = 0.90199$ (Answer)

---

### Runge-Kutta method

Runge-Kutta methods is used to solve differential equations. These will give us higher accuracy without performing more calculations.

**Formula:** Consider an ordinary differential equation of the form $\frac{dy}{dx} = f(x, y)$ with initial condition $y(x_0) = y_0$. For this, we can define the formulas for Runge-Kutta methods as follows:


- **$1^{st}$ order Runge-Kutta method**

  $y_1 = y_0 + hf(x_0, y_0)$

  or, $y_1 = y_0 + h y' _0$ {since $y'_0 = \frac{dy}{dx} = f(x, y)$}
  
  This formula is same as that of Euler's method.

<br>

- **$2^{nd}$ order Runge-Kutta method** (probably **NOT** in syllabus)

  $y_1 = y_0 + \frac{1}{2} (k_1 + k_2)$

  where,

  - $k_1 = hf(x_0, y_0)$
  - $k_2 = hf(x_0 + h, y_0 + k_1)$

<br>

- **$3^{rd}$ order Runge-Kutta method** (probably **NOT** in syllabus)

  $y_1 = y_0 + \frac{1}{6}(k_1 + 4k_2 + k_3)$

  where,
  - $k_1 = hf(x_0, y_0)$
  - $k_2 = hf(x_0 + \frac{1}{2} h, y_0 + \frac{1}{2} k_1)$
  - $k_3 = hf(x_0 + h, y_0 + k')$ where $k' = hf(x_0 + h, y_0 + k_1)$

  <br>

- **$4^{th}$ order Runge-Kutta method**

  The most commonly used Runge Kutta method to find the solution of a differential equation.

  $y_1 = y_0 + \frac{1}{6}(k_1 + 2k_2 + 2k_3 + k_4)$
  
  Here,
  - $k_1 = hf(x_0, y_0)$
  - $k_2 = hf[x_0 + \frac{1}{2} h, y_0 + \frac{1}{2} k_1]$
  - $k_3 = hf[x_0 + \frac{1}{2} h, y_0 + \frac{1}{2} k_2]$
  - $k_4 = hf(x_0 + h, y_0 + k_3)$

<br>

>**Example:** Consider an ordinary differential equation $\frac{dy}{dx} = x^2 + y^2$, $y(1) = 1.2$. Find $y(1.05)$ using the fourth order Runge-Kutta method.

**Solution:** Given:
- $\frac{dy}{dx} = x^2 + y^2$
- $y(1) = 1.2$
- $x_0 = 1, y_0 = 1.2$
- $h = 0.05$

Let's calculate $k_1, k_2, k_3, k_4$:

$k_1 = hf(x_0, y_0) = (0.05)(1^2 + 1.2^2) = 0.122$

$k_2 = hf[x_0 + \frac{1}{2} h, y_0 + \frac{1}{2} k_1] = (0.05)f(1 + 0.025, 1.2 + 0.061) = (0.05)(1.025^2 + 1.261^2) = 0.1320$

$k_3 = hf[x_0 + \frac{1}{2} h, y_0 + \frac{1}{2} k_2] = = (0.05)f(1 + 0.025, 1.2 + 0.066) = (0.05)(1.025^2 + 1.266^2) = 0.1326$

$k_4 = hf(x_0 + h, y_0 + k_3) = (0.05)f(1 + 0.05, 1.2 + 0.1326) =  (0.05)(1.05^2 + 1.3326^2) = 0.1439$

<br>

Now, by RK4 method, we have:

$y(1.05) = y_1 = y_0 + \frac{1}{6}(k_1 + 2k_2 + 2k_3 + k_4)$

Substituting the values, we get:

$y(1.05) = 1.2 + \frac{1}{6} \{ 0.122 + 2(0.1320) + 2(0.1326) + 0.1439 \}$

$y(1.05) = 1.2 + \frac{1}{6}  (0.122 + 0.264 + 0.2652 + 0.1439)$

$y(1.05) = 1.2 + 0.1325$

$y(1.05) = 1.3325$ (Answer)

