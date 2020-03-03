

## Pandas Intro 

* **Pandas** can be used for data manipulation and data visualisation 
* Pandas is built on two python libraries - **Numpy** and **Matplotlib**
	* Numpy provides multi-dimensional array of objects which Pandas use to store data
	* Matplotlib provides visualisation capabilities
	* Pandas is best for rectangular or tabular data, represented as a data frame 
	* Every column in the dataframe has the same data type

### Pandas functions
* pandas has 	several methods for quick data exploration:
	* `df.head()` - explore the initial few rows 
	* `df.tail()` - explore the last few rows
	* `df.info()` - data type and missing value info
	* `df.shape`- dimensions of the data 
		* Since shape is an attribute of data and not a method, it doesn't have a parenthesis
	* `df.describe()` - summary statistics for numeric data

	* Data frames consists of three different components accessible using attributes
	* `df.values` - shows the values of the dataframe in a 2-d array
	* 
