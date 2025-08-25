# Pearson correlation coefficient

Ex. (196) - Pearson correlation coefficient, is presented here in three programming languages: Python, MATLAB, and JavaScript. Although the implementations differ in syntax, the underlying concept remains identical across all three versions. Each code sample is reproduced from its respective volume of the series <i>Coding Examples from Simple to Complex</i> (Springer, 2024).
***

Here, the code begins by initializing two arrays, <i>a</i> and <i>b</i>, each containing three numeric values. The purpose of this code is to calculate the <i>Pearson correlation coefficient</i> between these two arrays, which is a statistical measure of the linear relationship between two datasets. The core of the calculation is performed in the <i>p</i> function. Inside this function, the length of the arrays is stored in the variable <i>n</i>. Two arrays, <i>m</i> and <i>s0</i>, are initialized to store intermediate values during the calculation. First, the means (averages) of arrays <i>a</i> and <i>b</i> are computed. The sum of all values in <i>a</i> is accumulated in <i>m[0]</i>, and the sum of all values in <i>b</i> is accumulated in <i>m[1]</i>. These sums are then divided by <i>n</i> to calculate the mean of each array. The next step involves calculating the <i>Pearson correlation coefficient</i>, namely:

$$
r = \frac{\sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})}
         {\sqrt{\sum_{i=1}^{n}(x_i - \bar{x})^2} \times \sqrt{\sum_{i=1}^{n}(y_i - \bar{y})^2}}
$$

Where <i>x</i><sub>i</sub> is a sample from the first data set, <i>y</i><sub>i</sub> is the sample from the second data set, <i>x̄</i> is the mean of the values from the first data set, <i>ȳ</i> is the mean of the values from the second data set, and finally <i>n</i> is the total number of samples from either data set (because they are equal). The formula for <i>r</i> looks complicated, however, the code will show the reader a different story. Thus, the above mathematical formula is computed by using three accumulators: <i>s0</i>, <i>s1</i>, and <i>s2</i>. Variable <i>s0</i> accumulates the sum of the products of the differences between each element of <i>a</i> and <i>b</i> from their respective means. On the other hand, variable <i>s1</i> accumulates the sum of the squared differences of each element in <i>a</i> from its <i>mean</i>, and <i>s2</i> accumulates the sum of squared differences for each element in <i>b</i> from its <i>mean</i>. With these intermediate values, the <i>Pearson correlation coefficient</i> (<i>r</i>) is computed as the ratio of <i>s0</i> divided by the square root of the product of <i>s1</i> and <i>s2</i>.

$$
r = \frac{s0}{s1 \times s2}
$$

$$
s0 = \sum_{i=1}^{n}(x_i - \bar{x})(y_i - \bar{y})
   = \sum_{i=0}^{n-1} \big[(a[i] - m[0])(b[i] - m[1])\big]
$$

$$
s1 = \sqrt{\sum_{i=1}^{n}(x_i - \bar{x})^2}
   = \sqrt{\sum_{i=0}^{n-1}(a[i] - m[0])^2}
   = \left(\sum_{i=0}^{n-1}(a[i] - m[0])^2\right)^{0.5}
$$

$$
s2 = \sqrt{\sum_{i=1}^{n}(y_i - \bar{y})^2}
   = \sqrt{\sum_{i=0}^{n-1}(b[i] - m[1])^2}
   = \left(\sum_{i=0}^{n-1}(b[i] - m[1])^2\right)^{0.5}
$$

Note the progressive replacement in the formulas with the Python representation from the source code. This coefficient measures the strength and direction of the linear relationship between the two arrays. A positive value of <i>r</i> indicates a positive correlation, a negative <i>r</i> indicates a negative correlation, and <i>r</i> close to 0 indicates a weak or no linear correlation. The result of the <i>Pearson correlation coefficient</i> calculation is returned from the <i>p</i> function, and then is printed in the output. In other words, the <i>Pearson correlation coefficient</i>, often denoted as <i>r</i>, is a common and very important method used to determine how closely two variables are linearly related, with values ranging from -1 (perfect negative correlation) to 1 (perfect positive correlation), and 0 indicating no linear correlation.

## Example in Python:

```python

``` 

```text
Python output:

```

## Example in Javascript:

```javascript

```

```text
Javascript output:

```

## Example in Matlab:

```matlab

```

```text
Matlab output:

```

## References

- <i>Paul A. Gagniuc. Coding Examples from Simple to Complex - Applications in Python, Springer, 2024, pp. 1-245.</i>
- <i>Paul A. Gagniuc. Coding Examples from Simple to Complex - Applications in MATLAB, Springer, 2024, pp. 1-255.</i>
- <i>Paul A. Gagniuc. Coding Examples from Simple to Complex - Applications in Javascript, Springer, 2024, pp. 1-240.</i>

***
