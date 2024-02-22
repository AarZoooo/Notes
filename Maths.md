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

$(x_1, y_1), (x_2, y_2), ... (x_n, y_n)$

Suppose `Y = f(X)` is an approximate relation that fits into a given data $x_i, y_i$. 

Then $y_i$ are called **observed (given) values** and $Y_i = f(X_i)$ are **expected values**.

The difference $R_i = y_i - Y_i$ is called **error or residual of $y_i$**.

<img src = "https://blog.mbedded.ninja/mathematics/curve-fitting/linear-curve-fitting/linear_curve_fitting_graph_of_points_and_line.png" height = 400></img>

### Method of Least Squares

This method leads to minimizing the sum of squares of the residuals with the formula:

$E_i = \sum_{i=1}^{n}(y_i - Y_i)^2$

We need to make the output of this formula minimum to reduce the residuals.

### Fitting of Straight line

We fit a straight line on the given points $(x_i, y_i)$:

Let: $Y = a + bx$ be the equation of a straight line to be fitted.

Now residual or error at $x = x_i$ is:

$E_i = y_i - Y_i$

or, $E_i = y_i - a - bx_i$

Now, $E = \sum_{i=1}^{n}(y_i - Y_i)^2$

therefore, $E = \sum_{i=1}^{n}(y_i - a - bx_i)$

By the method of least square, `a` and `b` are to be determined so that the sum of squares of residues is minimum.

$\frac{\delta E}{\delta a} = 0$

$\frac{\delta E}{\delta b} = 0$

now, $\frac{\delta E}{\delta a} = 2\sum_{i=1}^{n}(y_i - a - bx_i)(-1) = 0$

or, $\frac{\delta E}{\delta a} = \sum_{i=1}^{n}(y_i - a - bx_i) = 0$

or, $\sum y_i - a \sum 1 - b \sum x_i = 0$

or, $\sum y_i = an + b \sum x_i$

<br>

---

### Fitting of a Power Curve $Y = a x^b$

Let:
$$
Y = a x^b
$$
be a power curve where `a` and `b` are constants.

Taking log on both sides, we get:
$$
log (Y) = log (a X^b)
$$
$$
log (Y) = log (a) + log (X^b)
$$
$$
log Y = log (a) + b*log (X) ----(2)
$$
Let: $log (Y) = U$, $log (a) = A$, and $log (X) = V$

Then (2) becomes:

$$
U = A + bV ----(3)
$$ 

The normal equations corresponding to (3) are:

$$
\sum U = n A + b \sum V
$$
$$
\sum U V = A \sum V + b \sum V^2
$$

Solving, we get `A` and `b`

After that take $a = antilog(A)$

<br>

---

### Fitting of an exponential curve $Y = a b^X$

Let:
$$
Y = a b^X
$$

Applying log on both sides:
$$
log (Y) = log (a b^X)
$$
$$
log(Y) = log(a) + log(b^X)
$$
$$
log(Y) = log(a) + X*log(b) ---- (2)
$$

Let $log(Y) = U$, $log(a) = A$, $log(b) = B$

Then (2) becomes:
$$
U = A + BX ---- (3)
$$

THe normal equations corresponding to (3) are:

$$
\sum U = n A + B \sum X
$$
$$
\sum U X = A \sum X + B \sum X^2
$$

Solving, we get `A` and `B`

After that take $a = antilog(A)$, $b = antilog(B)$

<br>

---

### Fitting of exponential curve $Y = a e^{bX}$

Let:
$$
Y = a e^{bX} ---- (1)
$$

Taking log on both sides, we have:
$$
log (Y) = log (a) + log(e^{bX})
$$
$$
log(Y) = log(a) + b * X * log(e) ---- (2)
$$

Let:
- $log (Y) = U$
- $log(a) = A$
- $b*log(e) = B$

Then (2) becomes:
$$
U = A + BX ---- (3)
$$

The normal equations corresponding to (3) are:
$$
\sum U = n A + B \sum X
$$
$$
\sum U X = A \sum X + B \sum X^2
$$

Solving, we get `A` and `B`

After that, we take:
- $a = antilog(A)$
- $b = \frac{B}{log(e)}$

<br>

---

