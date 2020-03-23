
## Week 1 Notes- Python Crash Course

* Division of two `int` in python always gives out a `float `
* Strings are not mutable 
* `strings.find()` can be used to fetch the location of a particular text in a string
* The variables in python just store the location of an item,  so if x = 5 and y = 5. In the background, the x and y will point to the same address
	* The address can be identified by using `id` command. `id(x)`

## Week 2 Notes- Python Crash Course

#### Lists
* We also have collections [Data Structures] in Python along with the basic data types- these are arrays and vectors to put in different data datatypes

* `list` is one of the basic collections in Python. `[]`are used to generate list 
	* mutable
	* ordered or sequential collection - can access them by indexing
	* collection of related objects
* list can contain objects of different data types and can also contain other lists
* `y = list()` or `y = []` creates an empty list 

* **Adding elements** to the list:
	* `x.append()` adds element to the end of the list **as it is**
		* Takes only one argument
	* `x.insert(0, "Half")` helps us to insert the values. We can specify the location of the element 
	* `x.extend([1, 2, 3]) ` by this, we can take a list and add it to an extending list. It will **unpack the list** and append it to the existing list

* **Calling elements from a list** Lists are indexed and can be sliced
* **Removing items from a list**:
	* `x.pop(y)` - Remove the element at the location y
	* `x.pop()`- Removes the last item in the list
	* `x.remove(z)` - Remove first z from the list
	
#### Mutability
* Every object in Python is either mutable or immutable
* `int`,  `str`, `bool`, `float` are immutable. 5 will remain a 5, we can't make it 8 
* `list` objects are immutable in python
	* We can change the elements of a list 

### Tuples
* They are similar to lists, essential difference is that they are immutable
* We might want to work on the data elements one by one and working with the individual components






## Week 7 Notes- Data Analysis And Visualization: Part 1

#### Numpy Intro
*  Numpy - supports numerical and array operations and is a very fast one. 
*  Scipy - lot of capabilities for differential eqns etc
* **Numpy** :
	* Very fast mechanism for dealing with arrays and matrices
	* Most space efficient than lists. primarily coz it allows only 1 data type within an array
	* Can incorporate C++ / Fortran code. The underlying code is C
	* good support for Linear Algebra, Fourier transformation, Random number support

* **Numpy array**
	* basic data structure in numpy
	* sequential collection of like objects- indexing is faster and is memory efficient 
	* numpy arrays are mutable
	* optimised for matrix operations
	* provides random number support

* while reading data in numpy, we can specify the data type 
```py
x = ['1', '2', '3']
xi = np.array(x, 'int') # reading in as int
xf = np.array(x, 'float') # reading in as float 
xs = np.array(x, 'str') # reading in as str
```
* We can do the index in numpy using numpy[row, column]
* We can do the slicing in the similar manner [rows_select, column_select]
* numpy arrays can be reshaped using numpy.reshape
* 


