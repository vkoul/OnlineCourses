

## 1. Transforming Data

* **Pandas** can be used for data manipulation and data visualisation 
* Pandas is built on two python libraries - **Numpy** and **Matplotlib**
	* Numpy provides multi-dimensional array of objects which Pandas use to store data
	* Matplotlib provides visualisation capabilities
	* Pandas is best for rectangular or tabular data, represented as a data frame 
	* Every column in the dataframe has the same data type

### Pandas functions
 pandas has several methods for quick data exploration:
* `df.head()` - explore the initial few rows 
* `df.tail()` - explore the last few rows
* `df.info()` - data type and missing value info
* `df.shape`- dimensions of the data 
	* Since shape is an attribute of data and not a method, it doesn't have a parenthesis
* `df.describe()` -  computes summary statistics for numeric data

### Dataframe Components
Data frames consist of **three** different components accessible using attributes
* `df.values` - shows the values of the dataframe in a 2-d array
* `df.columns` - An index of columns: the column names.
* `df.index` -An index for the rows: either row numbers or row names.
	* row labels are stored in index
* pandas has multiple ways to solve a problem, this resembles more of a swiss army knife approach

### Pandas - Sorting and subsetting
#### Sorting columns
* `df.sort_values('column_name')` - This is used to sort the values based on a column. 
	* ascending order is the default
	* `ascending = False` argument will sort it in the descending order 
* Multiple columns sort - pass the column names as list 
	 ```py
	 df.sort_values(["Column1", "Column2"], ascending = [True, False]) # specify the direction of sorting for each column
	 ```

#### Subsetting Columns 
* `df['column_name']` - subsetting a particular column
* `df[['column1', 'column2']]` - subsetting multiple columns. 
	* We require two brackets. The inner one creates a list of column names and the outer one is for data-frame subsetting
	* We can only seprately define a list of column names and then pass that variable to subset data, a neater method. 

#### Subsetting Rows
* We can create the subsets at a row level using logical conditions
	* `df[df['column'] > 50]`
	* `df[df['column'] == 50]`
	* `df[df['column'] < 50]` 
* Text Data filters
	* `df[df['Name_column'] == 'Razz']`
* Date filters
	* `df[df['date_column'] > '2012-02-30']`
* Multiple row condition filters
	 ```py
	 df[(df["Column1"] == "XYZ") & (df["Column2"] == "PQR")] 
	 # the conditions are written separately in parenthesis
	 ```
 * Multiple values for a condition- we use  `.isin()` 
```py
is_black_or_brown = dogs["color"].isin(["Black" , "Brown"]) dogs[is_black_or_brown]
```
 #### New Columns
 
 * Use existing  columns to create new columns
  `df['new_column'] = df['existing_column'] / 100 ` 
  
## 2. Aggregating Data


