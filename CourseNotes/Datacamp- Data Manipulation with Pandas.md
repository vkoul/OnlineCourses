

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
	* `df[df['name_column'] == 'Razz']`
* Date filters
	* `df[df['date_column'] > '2012-02-30']`
* Multiple row condition filters
	 ```py
	 df[(df["column1"] == "XYZ") & (df["column2"] == "PQR")] 
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

#### Summary Statitics
* Calculating the central tendencies and other values
	* `df['column'].mean()`
	* Other calculations are : `.median()`, `.mode()`, `.min()`, `.max()`, `.var()`, `.std()`, `.sum()`, `.quantile()`,  
* Cumulative stats- `.cumsum()`, `.cummax()`, `.cummin()`, `cumprod()`
* These operations can run for numeric and date columns (wherever applicable) 
* The `.agg()` method in pandas allows to create custom summary statistics

```py 
# creating a 30 percent quantile function 
def pct30(column):
	return column.quantile(30)

# using the above function in a dataframe
df['column1'].agg(pct30)

# can also be used on more than one column
df[['column1', 'column2'].agg(pct30) #list of columns

# agg can also be used to calculate multiple summaries at once
df['column'].agg([mean, median]) # make a list of functions 
```

#### Duplicates & Counting

##### Duplicates and Counting 
* `df.drop_duplicates(subset = 'column')` - Drops the duplicate values in the data frame based on the column specified. 
* In case of multiple columns to be used: 
 `df.drop_duplicates(subset = ['column1', 'column2'])`
 * To get the frequency distribution of a column 
	`df['column'].value_counts()`
	* With sorting - `df['column'].value_counts(sort = True)`
	* With normalisation - `df['column'].value_counts(normalize = True)`

##### Grouping
* Grouping is one of the important ways to calculate the summary statistics for different groups of data :
	`df.groupby('column1')['column2'].mean()`
* We can combine the group by with `.agg()` method to get multiple summary statistics:
	`df.groupby('column1')['column2'].agg([min, max, mean])`
* Grouping can also be done using multiple columns:
`df.groupby('column1', 'column2)['column2'].agg([min, max, mean])`

##### Pivot Tables
* At its core, `pivot_table` functionality is very similar to `.groupby` in pandas
* Pivot table uses include: 
```py
# groupby 
df.groupby('column2')['column1'].mean()

# its equivalent in pivot table
df.pivot_table(values = 'column1' , index = 'column2')
## values column is the one by which to summarise and index column is the one by which you want to group by. Mean is the default summary statistics in pivot table

# Using a different summary statistics
df.pivot_table(values = 'column1', index = 'column2', aggfunc = np.median)

# multiple statistics in pivot table
df.pivot_table(values = 'column1', index = 'column2', aggfunc = [np.median, np.mean])

# multiple column groupby 
df.groupby(['column2', 'column3'])['column1'].mean()

# achieving similar operations in pivot tables
df.pivot_table(values = 'column1', index = 'column2', columns  = 'column3', aggfunc = [np.median, np.mean])
## The output of this is similar to the spread function in R

# to fill the missing values in the above step 
df.pivot_table(values = 'column1', index = 'column2', columns  = 'column3', fill_value = 0, aggfunc = [np.median, np.mean])
## the NaN of the data will be filled by 0 

# margin argument for a total in the end 
df.pivot_table(values = 'column1', index = 'column2', columns  = 'column3', fill_value = 0, margins = True, aggfunc = [np.median, np.mean])
```

## 3. Slicing and Indexing
#### The major benefit of index in data-frame is in the slicing and dicing of the dataframe
* We have rows as the by default index, but we can set a  particular column as the index: `df_new = df.set_index("column_name")`
	* To identify the index column, remember the index values are left aligned rather than right aligned
* To undo the setting of an index -  `df_new.reset_index()` 
	* it also has a `drop = True` argument which totally drops the column
* How index makes things simple:
```py
 # subsetting
 df[df['column'].isin(['ABC', 'PQR'])]
 
 # subsetting with the help of an index. the column is the index
 df_new.loc[["ABC", "PQR"]]
 ## the loc filters on the index values
```
* The values in the `index` don't need to be unique
* Index values don't get their own columns
* We can also sort the data by the index values using `df.sort_index()`
* Further control the sort index using the additional arguments
`df.sort_index(level = ['column1', 'column2'], ascending = [True, False]`
* The index column behaves differently than a normal dataframe column and hence there is a need to learn two syntaxes
	* To keep code simple, one can avoid index in the data and have a consistent set of codes

 

## 4. Creating and Visualising Data 

`Matplotlib` is a powerful visualization library used in python 
##### Histogram 
```py
import matplotlib.pyplot as plt
df['column'].hist()
plt.show()
```
The `bins` argument can help us to adjust the number of bars in the chart

##### Bars
```py
df['column'].plot(kind = "bar", title = "XYZ")
plt.show()
```
##### Lines
```py
df.plot(kind = "line", x = "column1", y = 'column2')
plt.show()
```
* The `rot` argument variable can be used to tilt the labels to make it more readable

##### Scatter Plots
```py
df.plot(kind = "scatter", x = "column1", y = 'column2')
plt.show()
```
* Plots can also be layered on top of each other by calling them one by one
	* `plt.legend()` can be useful to indicate the variable 
	* `alpha` can decide the transparency level with 0 being transparent and 1 being opaque


#### Missing Values
* In a pandas dataframe missing values are indicated using `NaN`

Missing value capabilities in pandas

```py
# detect the na across the dataset. This will give out a boolean output
df.isna()

# to see if there is at least 1 missing value
df.isna().any()

# count the missing values in the columns
df.isna().sum()

# visualizing te missing values
df.isna().sum().plot(kind = "bar")
plt.show()

# drop the rows with missing values
df.dropna()
## be cautious to use this, because if missing values are not absent at random, dropping the rows will introduce bias

# filling the missing values 
df.fillna(0)
```

