# JupyterLab 
`JupyterLab` is a next-generation web-based user interface for Project Jupyter.

`JupyterLab` enables you to work with documents and activities such as Jupyter `notebooks`, `text editors`, `terminals`, and `custom components` in a flexible, integrated, and extensible manner. For a demonstration of `JupyterLab` and its features, you can view this video:

# NumPy: Data Analysis with Python
`NumPy`, which stands for Numerical Python, is a library consisting of multidimensional array objects and a collection of routines for processing those arrays. Using `NumPy`, mathematical and logical operations on arrays can be performed. This tutorial explains the basics of `NumPy` such as its architecture and environment. It also discusses the various array functions, types of indexing, etc. An introduction to `Matplotlib` is also provided. All this is explained with the help of examples for better understanding.

## Creating A NumPy Array
We can create a NumPy array using the numpy.array function. If we pass in a list of lists, it will automatically create a NumPy array with the same number of rows and columns. Because we want all of the elements in the array to be float elements for easy computation, we’ll leave off the header row, which contains strings. One of the limitations of NumPy is that all the elements in an array have to be of the same type, so if we include the header row, all the elements in the array will be read in as strings. Because we want to be able to do computations like find the average quality of the wines, we need the elements to all be floats.

## NumPy Data Types
- float — numeric floating point data.
- int — integer data.
- string — character data.
- object — Python objects.


## Broadcasting
Unless the arrays that you’re operating on are the exact same size, it’s not possible to do elementwise operations. In cases like this, NumPy performs broadcasting to try to match up elements. Essentially, broadcasting involves a few steps:

- The last dimension of each array is compared.
   - If the dimension lengths are equal, or one of the dimensions is of length 1, then we keep going.
   - If the dimension lengths aren’t equal, and none of the dimensions have length 1, then there’s an error.

- Continue checking dimensions until the shortest array is out of dimensions.