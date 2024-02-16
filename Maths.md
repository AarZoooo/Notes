# UNIT 1

## Measure of Central Tendency

A single value which can represent a collection of data. Also called **Average Value**. When it comes to comparing two or more large datasets, in that case we summarise the dataset into a single value, which generally lies at the center of the dataset.

**Types of Measure of Central Tendency:**

1. Mean
2. Median
3. Mode

## Mean

Value obtained by dividing the sum of all observations by the total number of observations.

Mean = $\frac{Sumof all observations}{Number of observations}$

There are **three methods** to find mean:

1. Direct method
2. Short-cut method
3. Step deviation method

To be completed later

# UNIT 2

## Curve Fitting

The process of constructing a **curve** or mathematical function that has the best fit to a series of data points. Basically it examines the relationship between one or more independent variables and a dependent variable.

Let `x` be an **independent variable** and `y` be the **dependent variable**, and we have a set of values:

`(x1, y1)`, `(x2, y2)`, ... `(xn, yn)`.

Suppose `Y = f(X)` is an approximate relation that fits into a given data `(xi, yi)`. 

Then `yi` are called **observed (given) values** and `Yi = f(Xi)` are **expected values**.

The difference between `Ri = yi - Yi` is called **error or residual of yi**.

<img src = "https://blog.mbedded.ninja/mathematics/curve-fitting/linear-curve-fitting/linear_curve_fitting_graph_of_points_and_line.png" height = 400></img>

There are ways to minimize the residual, as follows:

### Method of Least Squares

This method leads to minimizing the sum of squares of the residuals with the formula:

$E_i = \sum_{i=1}^{n}(y_i - Y_i)^2$

We need to make the output of this formula minimum to reduce the residuals.

