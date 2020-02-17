---


---

<h2 id="getting-started-with-sql--coursera-notes">Getting Started with SQL- Coursera (Notes)</h2>
<ul>
<li>Primer in the fundamentals of the SQL</li>
<li>Asking the right questions and coming up with the right analysis for business impact</li>
</ul>
<h3 id="what-is-sql">What is SQL</h3>
<ul>
<li>Its a <code>query</code> language relational database management and data manipulation</li>
<li>Used to <em>query</em>, <em>update</em> and <em>insert</em> data</li>
<li>Interface between the user and the database</li>
<li>It’s a <strong>non-procedural</strong> language, hence can’t be used to write complete applications and is powerful to interact with data.</li>
<li>There are lot of roles that require the knowledge of SQL roles around Data Engineering [ETL, QA Engineer, DBA], Data Analysis and Data Scientists.</li>
<li>A Database Administrator is responsible for managing the whole database. He gives out access, manages and creates tables, determines access to data</li>
<li>DataScientist is more of an end user of a database. Use it to analyze data</li>
<li>Knowledge of SQL is fundamental in using data. They can use it to get the data or post deploying a model, they can use it to add the results back to a table</li>
<li>The syntax of the SQL used might change based on the RDMS being used.
<ul>
<li>Each RDBMS has its own dialect</li>
<li>Its like a change in ‘accent’. For every RDMS, you might need to tweak your SQL queries a bit</li>
<li>Popular ones include Microsoft SQL Server, PostGresql, SQLite, Oracle</li>
</ul>
</li>
</ul>
<h3 id="data-models-1">Data Models 1</h3>
<ul>
<li>Understanding the structure of the data is very essential in writing good queries
<ul>
<li>Understand the business process or subject matter on the data is modeled</li>
<li>Know the business rules</li>
<li>Understand how the data is organised and structured</li>
</ul>
</li>
<li><strong>Database</strong> is a container to store all the files, a set of related information</li>
<li><strong>Table</strong> would be one of the cabinets/store within the whole wall of cabinets</li>
<li>Within a table we have <em>rows</em> and <em>columns</em></li>
</ul>
<h3 id="evolution-of-data-models">Evolution of Data Models</h3>
<ul>
<li>Data modeling helps us organize multiple tables into a coherent structure</li>
<li>Can represent a business process or show relationships between different business process</li>
<li>The major types of data models are :
<ul>
<li><strong>Relational</strong>  (1970) : Really simplify the relationship between the data and easily write queries to retrieve, update data</li>
<li>Set oriented access</li>
<li>** Entity Relationship** (1976):</li>
</ul>
</li>
<li><strong>NoSQL</strong> (2009): Came late with the advent of the big data. Not in tabular form.
<ul>
<li>Less Semantics</li>
<li>Based on schema less key value</li>
<li>Best suited for large sparse data</li>
</ul>
</li>
</ul>
<h3 id="relational-vs.-transactional-models">Relational vs. Transactional Models</h3>
<ul>
<li>Relational model shows the relationships between tables and is used to optimise the queries for retrieving the data. Logical and intutive</li>
<li>Transactional Database:
<ul>
<li>Think of it as a operational database</li>
<li>Data is not stored in an easy manner and would be difficult to query</li>
</ul>
</li>
<li>Three simple building blocks of a relational database are:
<ul>
<li><strong>Entity</strong>: Person, place or an event</li>
<li><strong>Attribute</strong>:  characteristic of an entity</li>
<li><strong>Relationships</strong>:
<ul>
<li>One to many: ex. customer to invoices</li>
<li>Many to many: ex. student to classes</li>
<li>One to One: managers to a store</li>
</ul>
</li>
</ul>
</li>
<li>These relationships are best described using an <strong>ER Diagram</strong></li>
<li>For joining the tables we have:
<ul>
<li><strong>Primary Key</strong>: Column or set of column whose values identify the every row in the table (level of data)</li>
<li><strong>Foreign Key</strong>: Keys which can be used to identify a single row in another table</li>
<li><strong>ER Diagram Notations</strong>
<ul>
<li>Chen Notation</li>
<li>Crow’s Foot Notation : Mostly used</li>
<li>UML Class Diagram Notation</li>
</ul>
</li>
</ul>
</li>
</ul>
<h3 id="retreiving-data">Retreiving Data</h3>
<ul>
<li>A basic query consists of the columns which we need using the <code>SELECT</code> statement along with a <code>FROM</code> to specify the table</li>
<li>Use <code>LIMIT</code> when you just want to have a look at the sample of the data</li>
</ul>
<h3 id="creating-tables">Creating Tables</h3>
<ul>
<li>Creating tables can be useful because:
<ul>
<li>You can make predictions and then put them back in the tables</li>
<li>Customise data for Dashboards</li>
<li>Visualize with other tools</li>
</ul>
</li>
<li>Usual syntax is</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> Shoes <span class="token punctuation">(</span>
	ID CHAR<span class="token punctuation">(</span><span class="token number">10</span><span class="token punctuation">)</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span>
	<span class="token punctuation">,</span>Brand CHAR<span class="token punctuation">(</span><span class="token number">10</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
	<span class="token punctuation">,</span><span class="token keyword">Type</span> CHAR<span class="token punctuation">(</span><span class="token number">250</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
	<span class="token punctuation">,</span>Color CHAR<span class="token punctuation">(</span><span class="token number">250</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
	<span class="token punctuation">,</span><span class="token keyword">Desc</span>  <span class="token boolean">NULL</span>
	<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<ul>
<li>One lists the columns and the data type of each column. Like Brand should be a character with 10</li>
<li>Define which column is going to be the primary key</li>
<li>Data Types: how many characters and decimals would be allowed to be inserted into a column</li>
<li>Whether we should allow for a <code>NULL</code> in a column or not. ex in above table we allow Desc to be <code>NULL</code>.
<ul>
<li>NULL values are different from empty strings, it is ‘absence of everything’ in a cell</li>
</ul>
</li>
<li><code>PK</code> can’t have <code>NULL</code> values</li>
<li>If we specify that a column cannot be NULL, the column can’t be empty when we are inserting data into it</li>
<li>After we have created the table, we use the <code>INSERT</code> command to add data to the table</li>
<li>Specifiying the column names before the values makes it easy to allocate the data to the right columns</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">INSERT</span> <span class="token keyword">INTO</span>
Shoes <span class="token punctuation">(</span>
	<span class="token punctuation">,</span>ID 
	<span class="token punctuation">,</span>Brand 
	<span class="token punctuation">,</span><span class="token keyword">Type</span>
	<span class="token punctuation">,</span>Color 
	<span class="token punctuation">,</span><span class="token keyword">Desc</span> 
	<span class="token punctuation">)</span>
<span class="token keyword">VALUES</span> <span class="token punctuation">(</span><span class="token string">'145323'</span>
<span class="token punctuation">,</span><span class="token string">'GUCCI'</span>
<span class="token punctuation">,</span><span class="token string">'SLIPPERS'</span>
<span class="token punctuation">,</span><span class="token string">'PINK'</span>
<span class="token punctuation">,</span><span class="token boolean">NULL</span><span class="token punctuation">)</span> <span class="token punctuation">;</span>
</code></pre>
<ul>
<li>With the above method, we ensure that the data gets feeded into the right column, even when we remove few columns, it will get into the right column</li>
</ul>
<h3 id="temporary-tables">Temporary Tables</h3>
<ul>
<li>These table gets deleted when the current client session is terminated</li>
<li>They are faster than creating a real table</li>
<li>Useful for complex queries using subsets and joins</li>
<li></li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TEMPORARY</span> <span class="token keyword">TABLE</span> Sandals <span class="token keyword">AS</span><span class="token punctuation">(</span>
<span class="token keyword">SELECT</span> <span class="token operator">*</span> 
<span class="token keyword">FROM</span> shoes
<span class="token keyword">WHERE</span> shoe_type <span class="token operator">=</span> <span class="token string">'sandals'</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<ul>
<li>There are two ways to add comments in SQL :
<ul>
<li><code>--</code> or by using <code>/* */</code></li>
</ul>
</li>
</ul>
<h2 id="module-2-filtering-sorting-and-calculating-data-with-sql">Module 2: Filtering, Sorting and Calculating data with SQL</h2>
<ul>
<li>Wildcards</li>
<li>Group BY</li>
<li>ORDER BY</li>
<li>Aggregate Functions</li>
</ul>
<h3 id="basics-of-filtering">Basics of Filtering</h3>
<ul>
<li>Be specific about the data which you want to download</li>
<li>Reduce the number of records</li>
<li>Increase query performance</li>
<li>Reduce the strain on client application</li>
<li>Filtering is done using the <code>WHERE</code> clause and couple it with an operator like
<ul>
<li><code>&gt;</code>, <code>&lt;</code>, <code>&lt;=</code>, <code>&gt;=</code>,  <code>&lt;&gt;</code>, <code>BETWEEN</code>, <code>IS NULL</code>,</li>
</ul>
</li>
<li>It is not necessary to have the column in the <code>SELECT</code> statement on which filtering is being done</li>
</ul>
<h3 id="advanced-filtering--in-or-and-not">Advanced Filtering : <code>IN</code>, <code>OR</code> and <code>NOT</code></h3>
<ul>
<li><code>IN</code> is used  when we are looking for specific values in a column</li>
<li>We also use the <code>OR</code> operator.
<ul>
<li>An important condition to note that is RDMS won’t evaluate the second condition, when first condition is met</li>
</ul>
</li>
<li><code>IN</code> works as the same like <code>OR</code>, although <code>IN</code> has few benefits:
<ul>
<li>Long list of options</li>
<li><code>IN</code> executes faster than <code>OR</code> [<em>why so?</em>]</li>
<li>No need to think about an order in <code>IN</code></li>
<li>Can contain under another <code>SELECT</code></li>
</ul>
</li>
<li>While using <code>OR</code> and <code>AND</code> together , it is important to understand that <code>OR</code> might happen before <code>AND</code> and we need to use the <code>()</code> to properly define the order</li>
</ul>
<h3 id="wildcards-in-sql">Wildcards in SQL</h3>
<ul>
<li>Wildcards are extremely useful, especially when we are dealing with String value or text data</li>
<li>We are doing a pattern search for different parts of the text like beginning or ending of a phrase</li>
<li><code>LIKE</code> is technically a predicate and not an operator
<ul>
<li>It cannot be used for a non-text or numeric value</li>
</ul>
</li>
<li>Three ways we can use wildcards
<ul>
<li><code>'%Pizza'</code>: Grabs anything ending with Pizza</li>
<li><code>'Pizza%'</code>: Grabs anything which is before word Pizza</li>
<li><code>'%Pizza%'</code>: Grabs anything before and after the word pizza</li>
<li><code>'S%E'</code>: Grabs anything that starts with ‘S’ and ends with ‘E’.</li>
<li>Wildcards will not match the NULL values</li>
<li>Wildcards take a longer time to run
<ul>
<li>Placements of wilcards is important</li>
<li>Statements with wildcards take longer time to run if they are used at the end of serach patterns.</li>
</ul>
</li>
</ul>
</li>
</ul>
<h3 id="sorting-with-order-by">Sorting with ORDER BY</h3>
<ul>
<li>If you don’t specify the order of your data, it will just be captured in the same manner as it was captured/entered in the database; which is essentially random</li>
<li><code>ORDER BY</code> can use multiple column names or a single column</li>
<li>We can also use a column which is not there in our <code>SELECT</code> statement</li>
<li>It should always be the last clause in the query</li>
<li>We can also do ordering based on column position like</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ORDER</span> <span class="token keyword">BY</span>  <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span>
<span class="token comment">-- This orders data by 2nd and 3rd column</span>
</code></pre>
<ul>
<li>We can use <code>ASC</code> or <code>DESC</code> to sort data in a particular order</li>
</ul>
<h3 id="math-operator">Math Operator</h3>
<ul>
<li>We have the basic math operators like <code>+, -, * and /</code></li>
<li>We can combine them to do most of the mathematical analysis
<ul>
<li>Be careful of the order in which they get executed starting with the paranthesis</li>
</ul>
</li>
</ul>
<h3 id="aggregate-functions">Aggregate Functions</h3>
<ul>
<li>Helps to summarize and analyse the data in a concise manner</li>
<li>These are
<ul>
<li><code>AVG(), COUNT(), MIN(), MAX(), SUM()</code></li>
</ul>
</li>
<li>When we do <code>AVG</code>, rows containing <code>NULL</code> values are ignored
<ul>
<li>Even by <code>MIN</code> and <code>MAX</code> function</li>
</ul>
</li>
<li>When we do <code>COUNT(*)</code> , all the rows get counted including the ones with <code>NULL</code> values</li>
<li>When we do <code>Count(column)</code>, the <code>NULL</code> values get ignored</li>
<li>We need to use <code>DISTINCT</code> if we need unique values, because SQL by default assumes that we need all the values</li>
</ul>
<h3 id="grouping-data-with-sql">Grouping Data with SQL</h3>
<ul>
<li><code>GROUP BY</code> can contain multiple columns</li>
<li>Every column in the <code>SELECT</code> statement must be present in the <code>GROUP BY</code> clause, except for aggregated functions</li>
<li>In case of <code>NULL</code>, they will be grouped togther by <code>GROUP BY</code></li>
<li>Post grouping, we need to use <code>HAVING</code> to do the filtering on aggregated values</li>
</ul>
<h3 id="subqueries">Subqueries</h3>
<ul>
<li>The main value in relational database is achieved when we combine different facts, sources and tables together</li>
<li>Subqueries are queries embedded into other queries, a query inside another query</li>
<li>Subqueries are usually used to get selected data or columns which is then used to filter further.
<ul>
<li>Helps to add filtering criteria from another table into your table</li>
</ul>
</li>
</ul>

