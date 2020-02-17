## Getting Started with SQL- Coursera (Notes)

* Primer in the fundamentals of the SQL
* Asking the right questions and coming up with the right analysis for business impact

 ### What is SQL
* Its a `query` language relational database management and data manipulation 
* Used to *query*, *update* and *insert* data 
* Interface between the user and the database
* It's a **non-procedural** language, hence can't be used to write complete applications and is powerful to interact with data.
* There are lot of roles that require the knowledge of SQL roles around Data Engineering [ETL, QA Engineer, DBA], Data Analysis and Data Scientists. 
* A Database Administrator is responsible for managing the whole database. He gives out access, manages and creates tables, determines access to data 
* DataScientist is more of an end user of a database. Use it to analyze data
*  Knowledge of SQL is fundamental in using data. They can use it to get the data or post deploying a model, they can use it to add the results back to a table
* The syntax of the SQL used might change based on the RDMS being used. 
	* Each RDBMS has its own dialect
	* Its like a change in 'accent'. For every RDMS, you might need to tweak your SQL queries a bit
	* Popular ones include Microsoft SQL Server, PostGresql, SQLite, Oracle

### Data Models 1
* Understanding the structure of the data is very essential in writing good queries
	* Understand the business process or subject matter on the data is modeled
	* Know the business rules
	* Understand how the data is organised and structured
* **Database** is a container to store all the files, a set of related information 
* **Table** would be one of the cabinets/store within the whole wall of cabinets
* Within a table we have *rows* and *columns*

### Evolution of Data Models

* Data modeling helps us organize multiple tables into a coherent structure
* Can represent a business process or show relationships between different business process
* The major types of data models are :
	* **Relational**  (1970) : Really simplify the relationship between the data and easily write queries to retrieve, update data 
	* Set oriented access 
	* ** Entity Relationship** (1976):  
* **NoSQL** (2009): Came late with the advent of the big data. Not in tabular form.
	* Less Semantics
	* Based on schema less key value
	* Best suited for large sparse data

### Relational vs. Transactional Models
* Relational model shows the relationships between tables and is used to optimise the queries for retrieving the data. Logical and intutive
* Transactional Database:
	* Think of it as a operational database
	* Data is not stored in an easy manner and would be difficult to query
* Three simple building blocks of a relational database are:
	* **Entity**: Person, place or an event
	* **Attribute**:  characteristic of an entity
	* **Relationships**: 
		* One to many: ex. customer to invoices 
		* Many to many: ex. student to classes
		* One to One: managers to a store
* These relationships are best described using an **ER Diagram**
* For joining the tables we have:
	* **Primary Key**: Column or set of column whose values identify the every row in the table (level of data)
	* **Foreign Key**: Keys which can be used to identify a single row in another table
	* **ER Diagram Notations**
		* Chen Notation
		* Crow's Foot Notation : Mostly used
		* UML Class Diagram Notation
	
### Retreiving Data 
* A basic query consists of the columns which we need using the `SELECT` statement along with a `FROM` to specify the table
*  Use `LIMIT` when you just want to have a look at the sample of the data

### Creating Tables
* Creating tables can be useful because:
	* You can make predictions and then put them back in the tables
	* Customise data for Dashboards
	* Visualize with other tools 
* Usual syntax is 
```sql
CREATE TABLE Shoes (
	ID CHAR(10) PRIMARY KEY
	,Brand CHAR(10) NOT NULL
	,Type CHAR(250) NOT NULL
	,Color CHAR(250) NOT NULL
	,Desc  NULL
	);
```
* One lists the columns and the data type of each column. Like Brand should be a character with 10	
* Define which column is going to be the primary key
* Data Types: how many characters and decimals would be allowed to be inserted into a column
* Whether we should allow for a `NULL` in a column or not. ex in above table we allow Desc to be `NULL`.
	* NULL values are different from empty strings, it is 'absence of everything' in a cell
* `PK` can't have `NULL` values
* If we specify that a column cannot be NULL, the column can't be empty when we are inserting data into it
* After we have created the table, we use the `INSERT` command to add data to the table
* Specifiying the column names before the values makes it easy to allocate the data to the right columns
```sql
INSERT INTO
Shoes (
	,ID 
	,Brand 
	,Type
	,Color 
	,Desc 
	)
VALUES ('145323'
,'GUCCI'
,'SLIPPERS'
,'PINK'
,NULL) ;
```
* With the above method, we ensure that the data gets feeded into the right column, even when we remove few columns, it will get into the right column

### Temporary Tables
* These table gets deleted when the current client session is terminated 
* They are faster than creating a real table
* Useful for complex queries using subsets and joins
*
```sql
CREATE TEMPORARY TABLE Sandals AS(
SELECT * 
FROM shoes
WHERE shoe_type = 'sandals'
);
```
* There are two ways to add comments in SQL :
	*  ` -- ` or by using `/*   */` 


## Module 2: Filtering, Sorting and Calculating data with SQL
* Wildcards
* Group BY 
* ORDER BY 
* Aggregate Functions 

### Basics of Filtering 
* Be specific about the data which you want to download
* Reduce the number of records
* Increase query performance
* Reduce the strain on client application
* Filtering is done using the `WHERE` clause and couple it with an operator like
	* `>`, `<`, `<=`, `>=`,  `<>`, `BETWEEN`, `IS NULL`, 
* It is not necessary to have the column in the `SELECT` statement on which filtering is being done

 ### Advanced Filtering : `IN`, `OR` and `NOT`
 * `IN` is used  when we are looking for specific values in a column
 * We also use the `OR` operator. 
	 * An important condition to note that is RDMS won't evaluate the second condition, when first condition is met 
 * `IN` works as the same like `OR`, although `IN` has few benefits:
	 * Long list of options
	 * `IN` executes faster than `OR` [*why so?*]
	 * No need to think about an order in `IN`
	 * Can contain under another `SELECT`
 * While using `OR` and `AND` together , it is important to understand that `OR` might happen before `AND` and we need to use the `()` to properly define the order

### Wildcards in SQL
* Wildcards are extremely useful, especially when we are dealing with String value or text data
*  We are doing a pattern search for different parts of the text like beginning or ending of a phrase
* `LIKE` is technically a predicate and not an operator
	* It cannot be used for a non-text or numeric value
*  Three ways we can use wildcards
	* `'%Pizza'`: Grabs anything ending with Pizza
	* `'Pizza%'`: Grabs anything which is before word Pizza
	* `'%Pizza%'`: Grabs anything before and after the word pizza
	* `'S%E'`: Grabs anything that starts with 'S' and ends with 'E'.
	* Wildcards will not match the NULL values
	* Wildcards take a longer time to run 
		* Placements of wilcards is important
		* Statements with wildcards take longer time to run if they are used at the end of serach patterns. 
 
 ### Sorting with ORDER BY
 * If you don't specify the order of your data, it will just be captured in the same manner as it was captured/entered in the database; which is essentially random
 * `ORDER BY` can use multiple column names or a single column
 * We can also use a column which is not there in our `SELECT` statement
 * It should always be the last clause in the query
 * We can also do ordering based on column position like
  ```sql
ORDER BY  2, 3
-- This orders data by 2nd and 3rd column
```
* We can use `ASC` or `DESC` to sort data in a particular order
 
 ### Math Operator
 * We have the basic math operators like `+, -, * and /`
 * We can combine them to do most of the mathematical analysis
	 * Be careful of the order in which they get executed starting with the paranthesis
 
 ### Aggregate Functions
 * Helps to summarize and analyse the data in a concise manner
 * These are
	 * ` AVG(), COUNT(), MIN(), MAX(), SUM()`
 * When we do `AVG`, rows containing `NULL` values are ignored
	 * Even by `MIN` and `MAX` function
 * When we do `COUNT(*)` , all the rows get counted including the ones with `NULL` values
 * When we do `Count(column)`, the `NULL` values get ignored
 * We need to use `DISTINCT` if we need unique values, because SQL by default assumes that we need all the values
 
 ### Grouping Data with SQL
 * `GROUP BY` can contain multiple columns
 * Every column in the `SELECT` statement must be present in the `GROUP BY` clause, except for aggregated functions
 * In case of `NULL`, they will be grouped togther by `GROUP BY`
 * Post grouping, we need to use `HAVING` to do the filtering on aggregated values
 
 ### Subqueries
 * The main value in relational database is achieved when we combine different facts, sources and tables together
 *  Subqueries are queries embedded into other queries, a query inside another query
 * Subqueries are usually used to get selected data or columns which is then used to filter further. 
	 * Helps to add filtering criteria from another table into your table

 
 





