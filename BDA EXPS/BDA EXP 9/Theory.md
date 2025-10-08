Experiment: Linear Regression
Aim

To implement and understand the concept of Linear Regression, a fundamental supervised machine learning algorithm used for predicting continuous outcomes based on input variables.

Theory
Introduction

Linear Regression is one of the simplest and most widely used algorithms in machine learning.
It models the relationship between a dependent variable (y) and one or more independent variables (X) using a straight line.

The equation of a simple linear regression line is given by:

𝑦
=
𝑚
𝑋
+
𝑏
y=mX+b

Where:

y → Predicted output (dependent variable)

X → Input or independent variable

m → Slope or coefficient of the line

b → Intercept (value of y when X = 0)

Working Principle

The algorithm tries to find the best-fitting line that minimizes the difference between the actual and predicted values.

This difference is measured using the Mean Squared Error (MSE).

The slope (m) and intercept (b) are calculated using the Least Squares Method, which minimizes the sum of squared residuals.

Mathematical Formulation

For a dataset with 
𝑛
n points 
(
𝑥
𝑖
,
𝑦
𝑖
)
(x
i
	​

,y
i
	​

):

𝑚
=
𝑛
(
∑
𝑥
𝑦
)
−
(
∑
𝑥
)
(
∑
𝑦
)
𝑛
(
∑
𝑥
2
)
−
(
∑
𝑥
)
2
m=
n(∑x
2
)−(∑x)
2
n(∑xy)−(∑x)(∑y)
	​

𝑏
=
(
∑
𝑦
)
−
𝑚
(
∑
𝑥
)
𝑛
b=
n
(∑y)−m(∑x)
	​

Advantages

Simple to understand and implement.

Computationally efficient.

Provides good interpretability of model coefficients.

Useful as a baseline model for regression problems.

Disadvantages

Assumes a linear relationship between variables.

Sensitive to outliers, which can distort results.

Not suitable for non-linear data.

Performance degrades when there is multicollinearity among features.

Conclusion

Linear Regression helps in understanding relationships between variables and predicting numerical outcomes.
It provides the foundation for more advanced regression and machine learning models.
In this experiment, the slope and intercept obtained were:

Slope (m)
=
0.3167
,
Intercept (b)
=
4.2
Slope (m)=0.3167,Intercept (b)=4.2

Hence, the final regression equation is:

𝑦
^
=
0.3167
𝑋
+
4.2
y
^
	​

=0.3167X+4.2
