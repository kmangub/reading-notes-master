# Pandas

## Object Creation
Pandas is a python library tool that we can use for data analysis, data science, or machine learning. We use pandas to load, prepare, model, and manipulate data. 

To use it, we first have to import the library:

```
import numpy as np

import pandas as pd
```

We create an object for series, so:

```
s = pd.Series([1, 3, 5, np.nan, 6, 8])
s

output:
#0    1.0
#1    3.0
#2    5.0
#3    NaN
#4    6.0
#5    8.0
#dtype: float64
```

Below, we are creating a **DataFrame**:

```
In [5]: dates = pd.date_range("20130101", periods=6)

In [6]: dates
Out[6]: 
DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
               '2013-01-05', '2013-01-06'],
              dtype='datetime64[ns]', freq='D')

In [7]: df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))

In [8]: df
Out[8]: 
                   A         B         C         D
2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
2013-01-02  1.212112 -0.173215  0.119209 -1.044236
2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
2013-01-04  0.721555 -0.706771 -1.039575  0.271860
2013-01-05 -0.424972  0.567020  0.276232 -1.087401
2013-01-06 -0.673690  0.113648 -1.478427  0.524988
```

We create a dataframe by passing in a dictionary with objects:

```
In [9]: df2 = pd.DataFrame(
   ...:     {
   ...:         "A": 1.0,
   ...:         "B": pd.Timestamp("20130102"),
   ...:         "C": pd.Series(1, index=list(range(4)), dtype="float32"),
   ...:         "D": np.array([3] * 4, dtype="int32"),
   ...:         "E": pd.Categorical(["test", "train", "test", "train"]),
   ...:         "F": "foo",
   ...:     }
   ...: )
   ...: 

In [10]: df2
Out[10]: 
     A          B    C  D      E    F
0  1.0 2013-01-02  1.0  3   test  foo
1  1.0 2013-01-02  1.0  3  train  foo
2  1.0 2013-01-02  1.0  3   test  foo
3  1.0 2013-01-02  1.0  3  train  foo
```

and the columns have different datatypes. To show the datatypes, input `df2.dtypes` and we get the following result:

```
A           float64
B    datetime64[ns]
C           float32
D             int32
E          category
F            object
dtype: object
```

## Viewing Data

- `head()` shows the data
- `tail(3)` shows the last three rows of data

- `index` shows the index
- `columns` shows columns
- `DataFrame.to_numpy()` give the numpy respresentation 
- `describe()` shows a quick statistic summary of your data
- `T` transposes data
- `sort_index(axis=1, ascending=False)` sorts by axis
- `sort_values(by="B")` sorts values by the "B" column

> NumPy arrays have one dtype for the entire array, while pandas DataFrames have one dtype per column

## Selection 

- `df["A"]` selects a column, similarly `df.A`
- `df[0:3]` slices the rows
- `df["20130102":"20130104"]` slices rows as well

## Selection by label 

- `loc[dates[0]` gives the cross section 
- `df.loc[:, ["A", "B"]]` multi-axis label

Pandas is capable of doing so much, such as:

## Selection by position

## Boolean indexing

## Setting

## Missing data

## Operations

## Apply

## Histogramming

## String Methods

## Merge

## Concat

## Join

## Grouping

## Reshaping

## Pivot tables 

## Time series

## Categoricals

## Plotting

## Getting data in/out

## CSV

## HDF5

## Excel

## Gotchas



