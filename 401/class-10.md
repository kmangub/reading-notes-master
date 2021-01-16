# JupyterLab 

JupyterLab allows us to work with documents and using jupyter notebooks, terminals, text editors in an extensive way. It is broken down to three categories:

- Text, code consoles, and terminals. 

- Common formats. All image types and pdfs can be accessed through JupyterLab. 

- Jupyter notebooks. Data and code working together.

**Cells** contain thoughts or code and **kernals** execute that code. The neat thing is that there is an execution order on the left hand side that tells us when it will run, making debugging easier. 

# NumPy
NumPy is a Python data analysis package used to speed up our workflow. It can work with multidimensional arrays as well as 2-dimensional arrays. Here are some of the things we can do with NumPy:

- `numpy.array`, we can create a NumPy array for easier computation. 
- `numpy.zeros` creates elements that have zero in it. 
- `numpy.genfromtxt` - read csv or other files into arrays.
- `numpy.ndarray.astype` - convert array to a different type. 
- `numpy.ndarray.sum` - gives us the sum of the array. Ex// `<array>.sum()`
- `numpy.ndarray.mean` — finds the mean of an array.
- `numpy.ndarray.std` — finds the standard deviation of an array.
- `numpy.ndarray.min` — finds the minimum value in an array.
- `numpy.ndarray.max` — finds the maximum value in an array.
- `numpy.transpose` - changes the shape for easier access. Ex// rows to columns and vice versa.
- `numpy.ravel` - changes an array to a one-dimensional representation. 
- `numpy.reshape` - changes the array to the shape we specify. 
- `numpy.vstack` - Vertically stacks the arrays
- `numpy.hstack` - Horizontally stacks the arrays
- `numpy.concatenate` - General purpose of hstacks and vstacks. 

NumPy is 0 indexed, which means that rows and columns start with 0. If we pass in an array that looks like this: 

```
wines[2,3]
```

it will retrieve the third row, fourth column of that array. If an element in the array is empty, we can fill it out by setting it equal to the value we want to input. 

We can utilize slicing by using `:`, and it will enable us to grap certain parts of the array. 

We can take an entire row or column and assign it to the varaible, then we can grab the index of it.

Multidimensional arrays are just nested arrays with dimensions n. For example, if we are working with a dimension of 3, we are working with a list of a list of a list. The more dimensions we work with, the easier it is to organize out data. To see the size of our array, we use `<array_name>.shape`

Data types, like string, integer, object, and float, can be stored inside of the array. To find out what data type resides in an element, we can use `<array_name>.dtype`.

To check the name of the data type, we use `<array_name>.dtype.name`

We can perform all mathematical operations (/, *, -, +, ^) in NumPy for easy computations. If we do operations between arrays, it will only do the operation for the paired elements. Sometimes when we try to do operations between arrays, it will throw us an error and that's because the arrays need to be the same size.

We can do array comparisons to return a boolean.

A powerful tool that we can use is subsetting, where we can select certain elements in the array
