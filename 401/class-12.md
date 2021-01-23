# Linear Regression with Python

Linear Regression shows us the prediction of an equation based on the given data points on a graph. To use it, we use a module called `Scikit-learn` and linear regression is one of many things we can use. To start us off, we are going to import `numpy`, `pandas`, `scipy.stats`, `matplotlib.pyplot`, and `sklearn`. 

In the graph:

- The x-axis represents the independent variables
- the y-axis represents the target data, for example, the prices of housing

We import linear regression:

`from sklearn.linear_model import LinearRegression`


Next, we `drop` the parameters for the x-axis.

Finally, create an empty object:

`lm = LinearRegression`


```
EX//
> lm.fit(X, bos.PRICE)
> LinearRegression(copy_X=True, fit_intercept=True, normalize=False)
```

We then construct a data frame that contains features and estimated coefficients.

```
pd.DataFrame(zip(X.columns, lm.coef_), columns = ['features', 'estimatedCoefficients'])
```

To scatter a plot:

```
plt.scatter(bos.Rm, bos.PRICE)
plt.xlabel("Average number of rooms per dwelling (RM)")
plt.ylabel("Housing Price")
plt.title("Relationship between RM and Price")
pl.show()
```

If the plot trends up, it's a positive correlation. If it trends down, it's a negative correlation. 

We use the `predict()` to show what the predicted outputs would be. 

The mean squared error shows us how close a fitted line is to data points.

A `train-test split` provides random data sets.

Residual Plots provides us with a visual that shows the errors in our data. 

In short (taken from https://bigdata-madesimple.com/how-to-run-linear-regression-in-python-scikit-learn/):

- I explored the boston data set and then renamed its column names.
- I explored the boston data set using .DESCR, my goal was to predict the housing prices using the given features.
- I used Scikit learn to fit linear regression to the entire data set and calculated the mean squared error.
- I made a train-test split and calculated the mean squared error for my training data and test data.
- I then plotted the residuals for my training and test datasets.