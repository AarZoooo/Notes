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

<br>

# UNIT 2

## Curve Fitting

The process of constructing a **curve** or mathematical function that has the best fit to a series of data points. Basically it examines the relationship between one or more independent variables and a dependent variable.

Let $x$ be an **independent variable** and $y$ be the **dependent variable**, and we have a set of values:

$(x_1, y_1), (x_2, y_2), ... (x_n, y_n)$

Suppose $Y = f(X)$ is an approximate relation that fits into a given data $x_i$, $y_i$. 

Then $y_i$ are called **observed (given) values** and $Y_i = f(X_i)$ are **expected values**.

The difference $R_i = y_i - Y_i$ is called **error or residual of $y_i$**.

<img src = "https://blog.mbedded.ninja/mathematics/curve-fitting/linear-curve-fitting/linear_curve_fitting_graph_of_points_and_line.png" height = 400></img>

### Method of Least Squares

This method leads to minimizing the sum of squares of the residuals with the formula:

$E_i = \sum_{i=1}^{n}(y_i - Y_i)^2$

We need to make the output of this formula minimum to reduce the residuals.

---

### Fitting of a Straight line $Y = a + bx$

We fit a straight line on the given points $(x_i, y_i)$:

Let: $Y = a + bX$ be the equation of a straight line to be fitted.

Now residual or error at $X = x_i$ is:

$E_i = (y_i - Y_i)^2$

or, $E_i = (y_i - a - bx_i)^2$

Now, $E = \sum_{i=1}^{n}(y_i - Y_i)^2$

therefore, $E = \sum_{i=1}^{n}(y_i - a - bx_i)^2$

<br>

By the method of least square, $a$ and $b$ are to be determined so that the sum of squares of residues is minimum. That is:

$\frac{\delta E}{\delta a} = 0$

$\frac{\delta E}{\delta b} = 0$

<br>

$\frac{\delta E}{\delta a} = 2\sum_{i=1}^{n}(y_i - a - bx_i)(-1) = 0$

or, $\sum (y_i - a - bx_i) = 0$

or, $\sum y_i - a \sum 1 - b \sum x_i = 0$

or, $\sum y_i = na + b \sum x_i$

<br>

$\frac{\delta E}{\delta b} = 2\sum_{i=1}^{n}(y_i - a - bx_i)(-x_i) = 0$

or, $\sum (y_i x_i - a x_i - bx_i^2) = 0$

or, $\sum y_i x_i - a \sum x_i - b \sum x_i^2 = 0$

or, $\sum y_i x_i = a \sum x_i + b \sum x_i^2$

<br>

We obtained two equations, which are our normal equations for straight line. 

$\sum y = na + b \sum x$

$\sum xy = a \sum x + b \sum x^2$

<br>

Now we put the values we get from the given table into these two equations and solve them for values of $a$ and $b$. Hence, putting their values into our initial equation, we get the curve that is the best fit.

---

### Fitting of a Second-degree Parabola $𝑌 = 𝑎 + 𝑏𝑋 + 𝑐𝑋^2$

Let $𝑌 = 𝑎 + 𝑏𝑋 + 𝑐𝑋^2$ be the second-degree parabola and we have a set of n points $(x_i, y_i)$, where $i = 1, 2, …, n$.

With given n points $(x_i, y_i)$, the second-degree parabola be:

$𝑦_𝑖 = 𝑎 + 𝑏x_𝑖 + 𝑐𝑥_𝑖 ^2$

<br>

Let $𝑌_𝑖 = 𝑎 + 𝑏𝑥_𝑖 + 𝑐𝑥_𝑖 ^2$ be the estimated value of $Y$. Then according to the
principle of least squares:

$E = \sum ^n _{i = 1} (y_i - Y_i)^2$

$E = \sum ^n _{i = 1} (y_i - a - bx_i - cx_i ^2) ^2$

<br>

By the method of least square, $a$, $b$ and $c$ are to be determined so that the sum of squares of residues is minimum. That is:

$\frac{\delta E}{\delta a} = 0$
,
$\frac{\delta E}{\delta b} = 0$
,
$\frac{\delta E}{\delta c} = 0$

<br>

Therefore,

$\frac{\delta E}{\delta a} = 2 \sum ^n _{i = 1} (y_i - a - bx_i - cx_i ^2) (-1) = 0$

or, $-2 \sum ^n _{i = 1} (y_i - a - bx_i - cx_i ^2) = 0$

or, $\sum ^n _{i = 1} y_i = na + b \sum ^n _{i = 1} x_i + c \sum ^n _{i = 1} x_i ^2$

<br>

Similarly,

$\frac{\delta E}{\delta b} = -2 \sum ^n _{i = 1} (y_i - a - bx_i - cx_i ^2)(x_i) = 0$

or, $\sum y_i x_i = a \sum x_i + b \sum x_i ^2 + c \sum x_i ^3$

<br>

Similarly,

$\frac{\delta E}{\delta c} = -2 \sum ^n _{i = 1} (y_i - a - bx_i - cx_i ^2)(x_i ^2) = 0$

or, $\sum y_i x_i ^ 2 = a \sum x_i ^2 + b \sum x_i ^3 + c \sum x_i ^4$

<br>

Therefore, the normal equations we have are:

$\sum y = na + b \sum x + c \sum x ^2$

$\sum y x = a \sum x + b \sum x ^2 + c \sum x ^3$

$\sum y x ^ 2 = a \sum x ^2 + b \sum x ^3 + c \sum x ^4$

Upon solving these normal equations, we can get values of $a$, $b$ and $c$. Hence the equation we get is the best fit.

---

### Fitting of a Power Curve $Y = a x^b$

Let $Y = a X^b$ be a power curve where `a` and `b` are constants.

Taking log on both sides, we get:
$log (Y) = log (a X^b)$

$log (Y) = log (a) + log (X^b)$

$log (Y) = log (a) + (b) log (X) ----(2)$

<br>

Let:
- $log (Y) = U$
- $log (a) = A$
- $log (X) = V$

<br>

Then (2) becomes:

$U = A + bV ----(3)$ 

<br>

The normal equations corresponding to (3) are:

$\sum U = n A + b \sum V$

$\sum U V = A \sum V + b \sum V^2$

Solving these normal equations, we get `A` and `b`.

After that take $a = antilog(A)$

Thus with the values of `a` and `b`, the curve we get is the best fit.

---

### Fitting of an exponential curve $Y = a b^X$

Let $Y = a b^X$

Applying log on both sides:

$log (Y) = log (a b^X)$

$log(Y) = log(a) + log(b^X)$

$log(Y) = log(a) + (X)log(b) ---- (2)$

<br>

Let:
- $log(Y) = U$
- $log(a) = A$
- $log(b) = B$

<br>

Then (2) becomes:

$U = A + BX ---- (3)$

<br>

THe normal equations corresponding to (3) are:

$\sum U = n A + B \sum X$

$\sum U X = A \sum X + B \sum X^2$

Solving, we get `A` and `B`

After that take $a = antilog(A)$, $b = antilog(B)$

Thus with the values of `a` and `b` the curve we get is the best fit.

---

### Fitting of exponential curve $Y = a e^{bX}$

Let $Y = a e^{bX} ---- (1)$

<br>

Taking log on both sides, we have:
$log (Y) = log (a) + log(e^{bX})$

$log(Y) = log(a) + (b X)  log(e) ---- (2)$

<br>

Let:
- $log (Y) = U$
- $log(a) = A$
- $(b)log(e) = B$

<br>

Then (2) becomes:

$U = A + BX ---- (3)$

<br>

The normal equations corresponding to (3) are:

$\sum U = n A + B \sum X$

$\sum U X = A \sum X + B \sum X^2$

<br>

Solving, we get `A` and `B`

After that, we take:
- $a = antilog(A)$
- $b = \frac{B}{log(e)}$

Thus with the values of `a` and `b`, the curve we get is the best fit.

<br>

## Testing of Hypothesis

Hypothesis testing is used to test some hypothesis about parent population from which the sample is drawn.

### Hypothesis

It is a statement that is yet to be tested. It is a tentative answer to your research work. Hypothesis may be accepted or rejected based on the test.

### Procedure of testing of hypothesis for large sample

Steps:

1. Set up **Null hypothesis** $H_0$ and **Alternate Hypothesis** $H_1$.
2. Set up level of significance $\alpha$ (Generally it is taken 5% or 1%)
3. Use Z-test formula and find the calculated value.
4. Find out the Critical or Cut off values corresponding to $\alpha$
5. Take the decision about the null hypothesis based on the calculated and critical value of test. i.e.
   - If `Computed value < Critical Value` => `Accept the null hypothesis`
   - If `Computed value > Critical Value` => `Reject the null hypothesis`

<br>

>**Note:** 
>- $n > 30 \rightarrow$ Large sample
>- $n <= 30 \rightarrow$ Small sample
  
### Formula to find the value of Z-test

$Z = \frac{\bar x - \mu _0}{\frac{\sigma}{\sqrt n}}$

Where:

- $\bar x$ -> mean of sample
- $\mu _0$ -> mean of population
- $\sigma$ -> Standard Deviation of population
- $n$ -> Number of observations

**Note:** Critical value depends upon the nature of test:
1. One tailed test
2. Two tailed test

<img src = "https://d138zd1ktt9iqe.cloudfront.net/media/seo_landing_files/critical-value-2-1640777886.png"  height = 500 style = "background:white">

### One Tailed test

- For One Sample test:
  
  $H_0 : \mu = \bar X$
  
  $H_1 : \mu < \bar X (left tailed)$
  
  $H_2 : \mu > \bar X (right tailed)$
  

- For Two Sample test:
  
  $H_0 : \bar X_1 = \bar X_2$

  $H_1 : \bar X_1 < \bar X_2 (left tailed)$


  $H_2 : \bar X_1 > \bar X_2 (right tailed)$
  

### Two Tailed test

- For One Sample test:
  
  $H_0 : \mu = \bar X$
  
  $H_1 : \mu _1 \neq \bar X$
  

- For Two Sample test:
  
  $H_0 : \bar X_1 = \bar X_2$
  
  $H_1 : \bar X_1 \neq \bar X_2$

<br>

### Decision Making about Null Hypothesis using $p$-value

In this case we compare the $p$-value with given level of significance ($\alpha$)

If $p$-value <= $\alpha$, then we reject the null hypothesis

If $p$-value >= $\alpha$, then we accept the null hypothesis

### For two-tailed test:

- $P$-value = $2P[Z \geq z]$

### For one-tailed test:

- For $H_1 : \mu > \bar X$ (Right tailed)
  
  $P$-value = $P[Z \geq z]$

- For $H_1 : \mu < \bar X$ (Left tailed)

  $P$-value = $P[Z \leq z]$

<br>

>**Question 1:** If test is right-tailed and calculated value of test statistics $z$ is $1.23$, then calculate the $p$-value.
>
>**Answer:** We know for right-tailed test,
>
>P-value = $P[Z \geq z]$
>
>P-value = $P[Z \geq 1.23]$
>
>P-value = $1 - P[Z \leq 1.23]$
>
>P-value = $1 - 0.89065$
>
>P-value = $0.1093$

<br>

>**Question 2:** A light bulb company claims that their 100-watt light bulb has an average life of 1200 hours with Standard Deviation of 100 hours. For testing the claim, 50 new bulbs were selected randomly and allowed to burn out. The average lifetime of these bulbs was found to be 1180 hours. Is the company's claim true at 5% level of significance?
>
>**Answer:** Given:
>- $\mu _0$ = 1200
>- $\sigma$ = 100
>- $n$ = 50
>- $\bar X$ = 1180
>
>Now,
>$z = \frac{\bar X - \mu _0}{\frac{\sigma}{\sqrt{n}}}$
>
>$z = -1.41$
>
>The critical values for two tailed test at 5% level of significance are:
>
>$Z_{\frac{\alpha}{2}} = \pm Z_{0.025} = \pm 1.96$
>
>Since calculated value of test `z = -1.41` is greater than critical value `(-1.96)` and less than critical value `(1.96)`: **It lies in non-rejection region.**

<br>

### Testing Of Hypothesis For Difference Of Two Population Means Using Z-Test

$z = \frac{\bar x - \bar y}{\sqrt{\frac{\sigma _1 ^2}{n _1}+ \frac{\sigma _2 ^2}{n _2}}}$

where:
- $\bar x$ and $\bar y$ are sample population means of populations 1 and 2
- $\sigma _1$ and $\sigma _2$ are Standard Deviations of populations 1 and 2

<br>

>**Example:** In two samples of women from Punjab and Tamil Nadu each, the mean height of 1000 and 2000 women are 67.6 and 68.0 inches respectively. If population Standard Deviation is 5.5 inches for both, then can the mean heights of women in Punjab and Tamil Nadu be regarded as same at 1% level of significance?
>
>**Solution:** Given:
>- $\bar x = 67.6$
>- $\bar y = 68.0$
>- $\sigma _1 = \sigma _2 = 5.5$
>- $n_1 = 1000, n_2 = 2000$
>
>And we have $H_0 : \bar x = \bar y$
>
>$H_1 : \bar x \neq \bar y$
>
>Now,
>
>$z = \frac{67.6 - 68.0}{\sqrt{\frac{(5.5)^2}{1000}+ \frac{(5.5)^2}{2000}}} = -1.8778$
>
>Critical values for two-tailed test at 1% level of significance are:
>
>$Z_{0.005} = \pm 2.58$
>
>Since $-2.58 < -1.8778 < 2.58$ The null hypothesis can't be rejected

<br>

### Testing of hypothesis for Single Population Proportion



---

1. In a random sample of 100 people from town A, 60 are found to be high consumers of wheat. In another sample of 80 people from town B, 40 are found to be high consumers of wheat. Do these data reveal a significant difference between the proportions of high wheat consumers in town A and town B (at $\alpha = 0.05$)?

