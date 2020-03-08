---


---

<hr>
<hr>
<h1 id="yandex-practicum---data-scientist">Yandex Practicum - Data Scientist</h1>
<h2 id="sprint-1-notes">Sprint 1 Notes</h2>
<p>Python code from the course:</p>
<pre class="  language-py"><code class="prism  language-py">
<span class="token comment"># Exclude values from a data-frame</span>
data <span class="token operator">=</span> data<span class="token punctuation">[</span>data<span class="token punctuation">[</span><span class="token string">'subcategory_id'</span><span class="token punctuation">]</span> <span class="token operator">!=</span>  <span class="token string">'total'</span><span class="token punctuation">]</span>
</code></pre><p><span class="token comment"># as type conversion</span><br>
df<span class="token punctuation">[</span><span class="token string">‘column’</span><span class="token punctuation">]</span> <span class="token operator">=</span> df<span class="token punctuation">[</span><span class="token string">‘column’</span><span class="token punctuation">]</span><span class="token punctuation">.</span>astype<span class="token punctuation">(</span><span class="token string">‘int’</span><span class="token punctuation">)</span></p>
<p><span class="token comment"># datatime in python, - Python has a specific format for datetime called ‘datetime’. We can use the to_datetime() to change the values into date-time</span></p>
<p><span class="token comment"># —%d: day of the month (01 to 31)</span></p>
<p><span class="token comment"># —%m: month (01 to 12)</span></p>
<p><span class="token comment"># —%Y: four-digit year (2019)</span></p>
<p><span class="token comment"># — Z: standard separator for date and time</span></p>
<p><span class="token comment"># —%H: hour in 24-hour format</span></p>
<p><span class="token comment"># —%I: hour in 12-hour format</span></p>
<p><span class="token comment"># —%M: minutes (00 to 59)</span></p>
<p><span class="token comment"># —%S: seconds (00 to 59)</span></p>
<p><span class="token comment"># conversion step</span><br>
arrivals<span class="token punctuation">[</span><span class="token string">‘date_datetime’</span><span class="token punctuation">]</span><span class="token operator">=</span> pd<span class="token punctuation">.</span>to_datetime<span class="token punctuation">(</span>arrivals<span class="token punctuation">[</span><span class="token string">‘date’</span><span class="token punctuation">]</span><span class="token punctuation">,</span> <span class="token builtin">format</span><span class="token operator">=</span><span class="token string">’%d.%m.%YZ%H:%M:%S’</span><span class="token punctuation">)</span></p>
<p><span class="token comment"># There are all kinds of different ways to represent dates and times, but a particularly uncommon one is the unix time format.</span></p>
<p><span class="token comment"># The idea is simple: It’s the number of seconds that have passed since 00:00:00 on January 1, 1970. Unix time corresponds to the Coordinated Universal Time, or UTC.</span></p>
<p><span class="token comment"># getting the month equally</span><br>
arrivals<span class="token punctuation">[</span><span class="token string">‘month’</span><span class="token punctuation">]</span> <span class="token operator">=</span> pd<span class="token punctuation">.</span>DatetimeIndex<span class="token punctuation">(</span>arrivals<span class="token punctuation">[</span><span class="token string">‘date’</span><span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">.</span>month</p>
<p><span class="token comment">#There’s a function called try-except that we use when we’re working with unpredictable data.</span><br>
<span class="token comment"># You add the source code to the try block, and if there’s a problem with it, the code in the except block will be executed instead.</span></p>
<p>a <span class="token operator">=</span>  <span class="token number">1</span></p>
<p>b <span class="token operator">=</span>  <span class="token number">0</span></p>
<p><span class="token keyword">try</span><span class="token punctuation">:</span></p>
<p><span class="token keyword">print</span><span class="token punctuation">(</span>a <span class="token operator">/</span> b<span class="token punctuation">)</span></p>
<p><span class="token keyword">except</span><span class="token punctuation">:</span></p>
<p><span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">‘Check the values of the parameters a and b’</span><span class="token punctuation">)</span></p>
<p><span class="token keyword">print</span> <span class="token punctuation">(</span><span class="token string">‘By the way, good afternoon’</span><span class="token punctuation">)</span></p>
<p><span class="token comment"># usage</span></p>
<p>position <span class="token operator">=</span> <span class="token punctuation">[</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-01’</span><span class="token punctuation">,</span> <span class="token string">‘- 6’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-02’</span><span class="token punctuation">,</span> <span class="token string">‘+5’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-03’</span><span class="token punctuation">,</span> <span class="token string">’ 5’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-04’</span><span class="token punctuation">,</span> <span class="token string">‘4’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-05’</span><span class="token punctuation">,</span> <span class="token string">‘5’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-06’</span><span class="token punctuation">,</span> <span class="token string">‘5’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-07’</span><span class="token punctuation">,</span> <span class="token string">‘4’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-08’</span><span class="token punctuation">,</span> <span class="token string">‘Error 5’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-09’</span><span class="token punctuation">,</span> <span class="token string">‘3’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">[</span><span class="token string">‘2019-05-10’</span><span class="token punctuation">,</span> <span class="token string">‘3’</span><span class="token punctuation">]</span><span class="token punctuation">,</span></p>
<p><span class="token punctuation">]</span></p>
<p>total_position <span class="token operator">=</span>  <span class="token number">0</span><br>
count_lines <span class="token operator">=</span>  <span class="token number">0</span><br>
wrong_lines <span class="token operator">=</span>  <span class="token number">0</span></p>
<p><span class="token keyword">for</span> row <span class="token keyword">in</span> position<span class="token punctuation">:</span></p>
<p><span class="token keyword">try</span><span class="token punctuation">:</span></p>
<p>count_lines <span class="token operator">+=</span>  <span class="token number">1</span></p>
<p>level <span class="token operator">=</span>  <span class="token builtin">int</span><span class="token punctuation">(</span>row<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span></p>
<p>total_position <span class="token operator">+=</span> level</p>
<p><span class="token keyword">except</span><span class="token punctuation">:</span></p>
<p>wrong_lines <span class="token operator">+=</span>  <span class="token number">1</span></p>
<p><span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">“Total measurements”</span><span class="token punctuation">,</span> count_lines<span class="token punctuation">)</span></p>
<p><span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">“Total erroneous rows”</span><span class="token punctuation">,</span> wrong_lines<span class="token punctuation">)</span></p>
<p><span class="token comment"># joining in python</span><br>
data_subcategory <span class="token operator">=</span> data<span class="token punctuation">.</span>merge<span class="token punctuation">(</span>subcategory_dict<span class="token punctuation">,</span> on<span class="token operator">=</span><span class="token string">‘subcategory_id’</span><span class="token punctuation">,</span> how<span class="token operator">=</span><span class="token string">‘left’</span><span class="token punctuation">)</span></p>
<p><span class="token comment"># count the duplicated data</span><br>
data<span class="token punctuation">[</span><span class="token string">‘column’</span><span class="token punctuation">]</span><span class="token punctuation">.</span>duplicated<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span></p>
<p><span class="token comment"># drop duplicates</span><br>
stock<span class="token punctuation">[</span><span class="token string">‘item_lowercase’</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">‘item_lowercase’</span><span class="token punctuation">]</span><span class="token punctuation">.</span>drop_duplicates<span class="token punctuation">(</span><span class="token punctuation">)</span></p>
<p><span class="token comment"># lower the case</span><br>
pd<span class="token punctuation">.</span><span class="token builtin">str</span><span class="token punctuation">.</span>lower<span class="token punctuation">(</span><span class="token punctuation">)</span></p>
<p><span class="token comment"># whole process</span><br>
<span class="token keyword">import</span> pandas <span class="token keyword">as</span> pd</p>
<p>stock <span class="token operator">=</span> pd<span class="token punctuation">.</span>read_csv<span class="token punctuation">(</span><span class="token string">’/datasets/stock_upd_eng.csv’</span><span class="token punctuation">)</span></p>
<p>stock<span class="token punctuation">[</span><span class="token string">‘item_lowercase’</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">‘item’</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">str</span><span class="token punctuation">.</span>lower<span class="token punctuation">(</span><span class="token punctuation">)</span></p>
<p>apple <span class="token operator">=</span> stock<span class="token punctuation">[</span>stock<span class="token punctuation">[</span><span class="token string">‘item_lowercase’</span><span class="token punctuation">]</span> <span class="token operator">==</span>  <span class="token string">‘apple iphone xr 64gb’</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token string">‘count’</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span></p>
<p>samsung <span class="token operator">=</span> stock<span class="token punctuation">[</span>stock<span class="token punctuation">[</span><span class="token string">‘item_lowercase’</span><span class="token punctuation">]</span> <span class="token operator">==</span>  <span class="token string">‘samsung galaxy a30 32gb’</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token string">‘count’</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span></p>
<p>stock<span class="token punctuation">[</span><span class="token string">‘item_lowercase’</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">‘item_lowercase’</span><span class="token punctuation">]</span><span class="token punctuation">.</span>drop_duplicates<span class="token punctuation">(</span><span class="token punctuation">)</span></p>
<p>stock <span class="token operator">=</span> stock<span class="token punctuation">.</span>dropna<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span>reset_index<span class="token punctuation">(</span>drop<span class="token operator">=</span><span class="token boolean">True</span><span class="token punctuation">)</span></p>
<p><span class="token comment">## defining a function with comments</span><br>
<span class="token keyword">def</span>  <span class="token function">age_group</span><span class="token punctuation">(</span>age<span class="token punctuation">)</span><span class="token punctuation">:</span><br>
<span class="token triple-quoted-string string"></span></p>
<h1 id="yandex-practicum---data-scientist">Yandex Practicum - Data Scientist</h1>
<h2 id="sprint-1-notes">Sprint 1 Notes</h2>
<p>Python code from the course:</p>
<pre class=" language-py"><code class="prism  language-py">
<span class="token comment"># Exclude values from a data-frame</span>
data <span class="token operator">=</span> data<span class="token punctuation">[</span>data<span class="token punctuation">[</span><span class="token string">'subcategory_id'</span><span class="token punctuation">]</span> <span class="token operator">!=</span>  <span class="token string">'total'</span><span class="token punctuation">]</span>

<span class="token comment"># as type conversion</span>
df<span class="token punctuation">[</span><span class="token string">'column'</span><span class="token punctuation">]</span> <span class="token operator">=</span> df<span class="token punctuation">[</span><span class="token string">'column'</span><span class="token punctuation">]</span><span class="token punctuation">.</span>astype<span class="token punctuation">(</span><span class="token string">'int'</span><span class="token punctuation">)</span>

<span class="token comment"># datatime in python, - Python has a specific format for datetime called 'datetime'. We can use the to_datetime() to change the values into date-time</span>


<span class="token comment"># —%d: day of the month (01 to 31)</span>

<span class="token comment"># —%m: month (01 to 12)</span>

<span class="token comment"># —%Y: four-digit year (2019)</span>

<span class="token comment"># — Z: standard separator for date and time</span>

<span class="token comment"># —%H: hour in 24-hour format</span>

<span class="token comment"># —%I: hour in 12-hour format</span>

<span class="token comment"># —%M: minutes (00 to 59)</span>

<span class="token comment"># —%S: seconds (00 to 59)</span>


<span class="token comment"># conversion step</span>
arrivals<span class="token punctuation">[</span><span class="token string">'date_datetime'</span><span class="token punctuation">]</span><span class="token operator">=</span> pd<span class="token punctuation">.</span>to_datetime<span class="token punctuation">(</span>arrivals<span class="token punctuation">[</span><span class="token string">'date'</span><span class="token punctuation">]</span><span class="token punctuation">,</span> <span class="token builtin">format</span><span class="token operator">=</span><span class="token string">'%d.%m.%YZ%H:%M:%S'</span><span class="token punctuation">)</span>

<span class="token comment"># There are all kinds of different ways to represent dates and times, but a particularly uncommon one is the unix time format.</span>

<span class="token comment"># The idea is simple: It’s the number of seconds that have passed since 00:00:00 on January 1, 1970. Unix time corresponds to the Coordinated Universal Time, or UTC.</span>

<span class="token comment"># getting the month equally</span>
arrivals<span class="token punctuation">[</span><span class="token string">'month'</span><span class="token punctuation">]</span> <span class="token operator">=</span> pd<span class="token punctuation">.</span>DatetimeIndex<span class="token punctuation">(</span>arrivals<span class="token punctuation">[</span><span class="token string">'date'</span><span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">.</span>month

<span class="token comment">#There’s a function called try-except that we use when we’re working with unpredictable data.</span>
<span class="token comment"># You add the source code to the try block, and if there’s a problem with it, the code in the except block will be executed instead.</span>

a <span class="token operator">=</span>  <span class="token number">1</span>

b <span class="token operator">=</span>  <span class="token number">0</span>

<span class="token keyword">try</span><span class="token punctuation">:</span>

<span class="token keyword">print</span><span class="token punctuation">(</span>a <span class="token operator">/</span> b<span class="token punctuation">)</span>

<span class="token keyword">except</span><span class="token punctuation">:</span>

<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'Check the values of the parameters a and b'</span><span class="token punctuation">)</span>

<span class="token keyword">print</span> <span class="token punctuation">(</span><span class="token string">'By the way, good afternoon'</span><span class="token punctuation">)</span>

  

<span class="token comment"># usage</span>

position <span class="token operator">=</span> <span class="token punctuation">[</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-01'</span><span class="token punctuation">,</span> <span class="token string">'- 6'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-02'</span><span class="token punctuation">,</span> <span class="token string">'+5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-03'</span><span class="token punctuation">,</span> <span class="token string">' 5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-04'</span><span class="token punctuation">,</span> <span class="token string">'4'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-05'</span><span class="token punctuation">,</span> <span class="token string">'5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-06'</span><span class="token punctuation">,</span> <span class="token string">'5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-07'</span><span class="token punctuation">,</span> <span class="token string">'4'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-08'</span><span class="token punctuation">,</span> <span class="token string">'Error 5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-09'</span><span class="token punctuation">,</span> <span class="token string">'3'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-10'</span><span class="token punctuation">,</span> <span class="token string">'3'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">]</span>

total_position <span class="token operator">=</span>  <span class="token number">0</span>
count_lines <span class="token operator">=</span>  <span class="token number">0</span>
wrong_lines <span class="token operator">=</span>  <span class="token number">0</span>

  

<span class="token keyword">for</span> row <span class="token keyword">in</span> position<span class="token punctuation">:</span>

<span class="token keyword">try</span><span class="token punctuation">:</span>

count_lines <span class="token operator">+=</span>  <span class="token number">1</span>

level <span class="token operator">=</span>  <span class="token builtin">int</span><span class="token punctuation">(</span>row<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span>

total_position <span class="token operator">+=</span> level

<span class="token keyword">except</span><span class="token punctuation">:</span>

wrong_lines <span class="token operator">+=</span>  <span class="token number">1</span>

  

<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">"Total measurements"</span><span class="token punctuation">,</span> count_lines<span class="token punctuation">)</span>

<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">"Total erroneous rows"</span><span class="token punctuation">,</span> wrong_lines<span class="token punctuation">)</span>

<span class="token comment"># joining in python</span>
data_subcategory <span class="token operator">=</span> data<span class="token punctuation">.</span>merge<span class="token punctuation">(</span>subcategory_dict<span class="token punctuation">,</span> on<span class="token operator">=</span><span class="token string">'subcategory_id'</span><span class="token punctuation">,</span> how<span class="token operator">=</span><span class="token string">'left'</span><span class="token punctuation">)</span>

<span class="token comment"># count the duplicated data</span>
data<span class="token punctuation">[</span><span class="token string">'column'</span><span class="token punctuation">]</span><span class="token punctuation">.</span>duplicated<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token comment"># drop duplicates</span>
stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span><span class="token punctuation">.</span>drop_duplicates<span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token comment"># lower the case</span>
pd<span class="token punctuation">.</span><span class="token builtin">str</span><span class="token punctuation">.</span>lower<span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token comment"># whole process</span>
<span class="token keyword">import</span> pandas <span class="token keyword">as</span> pd

stock <span class="token operator">=</span> pd<span class="token punctuation">.</span>read_csv<span class="token punctuation">(</span><span class="token string">'/datasets/stock_upd_eng.csv'</span><span class="token punctuation">)</span>

stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">'item'</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">str</span><span class="token punctuation">.</span>lower<span class="token punctuation">(</span><span class="token punctuation">)</span>

apple <span class="token operator">=</span> stock<span class="token punctuation">[</span>stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">==</span>  <span class="token string">'apple iphone xr 64gb'</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token string">'count'</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span>

samsung <span class="token operator">=</span> stock<span class="token punctuation">[</span>stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">==</span>  <span class="token string">'samsung galaxy a30 32gb'</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token string">'count'</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span>

stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span><span class="token punctuation">.</span>drop_duplicates<span class="token punctuation">(</span><span class="token punctuation">)</span>

  

stock <span class="token operator">=</span> stock<span class="token punctuation">.</span>dropna<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span>reset_index<span class="token punctuation">(</span>drop<span class="token operator">=</span><span class="token boolean">True</span><span class="token punctuation">)</span>

  
  

<span class="token comment">## defining a function with comments</span>
<span class="token keyword">def</span>  <span class="token function">age_group</span><span class="token punctuation">(</span>age<span class="token punctuation">)</span><span class="token punctuation">:</span>
<span class="token triple-quoted-string string">"""
The function returns the age group according to age value, by using the following rules:

—'children', with age value &amp;lt;&lt;= 18 years

—'adult', with age value over 18 and up to 64

—'retired' for all other cases
"""</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">if</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> age <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;</span><span class="token operator">&amp;</span>lt<span class="token punctuation">;</span><span class="token operator">=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>  <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">18</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">:</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">return</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>  <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'child'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">if</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> age <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;</span><span class="token operator">&amp;</span>lt<span class="token punctuation">;</span><span class="token operator">=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>  <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">64</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">:</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">return</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>  <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'adult'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">return</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>  <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'retired'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment">## text analytics&lt;/span&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># using the example&lt;/span&gt;</span>

text <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>  <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'Heard melodies are sweet, but those unheard Are sweeter; therefore, ye soft pipes, play on;'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

words <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> nltk<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">.</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>word_tokenize<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>text<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">print</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>words<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

  
<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># lemmitization&lt;/span&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># WordNet Lemmatizer is imported as follows:&lt;/span&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">import</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> nltk

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">from</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> nltk<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">.</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>stem <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">import</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> WordNetLemmatizer

wordnet_lemma <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> WordNetLemmatizer<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span><span class="token operator">/</span>code<span class="token operator">&gt;</span><span class="token operator">&lt;</span><span class="token operator">/</span>pre<span class="token operator">&gt;</span>
<span class="token operator">&lt;</span>h2 <span class="token builtin">id</span><span class="token operator">=</span><span class="token string">"sprint-3"</span><span class="token operator">&gt;</span>Sprint <span class="token number">3</span><span class="token operator">&lt;</span><span class="token operator">/</span>h2<span class="token operator">&gt;</span>
<span class="token operator">&lt;</span>h5 <span class="token builtin">id</span><span class="token operator">=</span><span class="token string">"commands"</span><span class="token operator">&gt;</span>Commands<span class="token operator">&lt;</span><span class="token operator">/</span>h5<span class="token operator">&gt;</span>
<span class="token operator">&lt;</span>pre <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">" language-py"</span><span class="token operator">&gt;</span><span class="token operator">&lt;</span>code <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"prism  language-py"</span><span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># using the parameters of the read_csv file&lt;/span&gt;</span>
<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token builtin"</span><span class="token operator">&gt;</span><span class="token builtin">file</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> pd<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">.</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>read_csv<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'file.csv'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">,</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> sep<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">';'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">,</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> decimal<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">','</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>
<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment">## sep is for pointing out the separator and decimal parameter is for numeric values&lt;/span&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># histogram parameters&lt;/span&gt;</span>
df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">.</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>hist<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>bins <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">10</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">,</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token builtin"</span><span class="token operator">&gt;</span><span class="token builtin">range</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;=</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token builtin"</span><span class="token operator">&gt;</span><span class="token builtin">min</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">,</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token builtin"</span><span class="token operator">&gt;</span><span class="token builtin">max</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># Boxplot parameters&lt;/span&gt;</span>
<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">import</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> matplotlib<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">.</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>pyplot <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token keyword"</span><span class="token operator">&gt;</span><span class="token keyword">as</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> plt 

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># setting the dimensions of the chart&lt;/span&gt;</span>
plt<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">.</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>ylim<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;</span><span class="token operator">-</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">50</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">,</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">500</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> 
plt<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">.</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>xlim<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">0</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">,</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">200</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># Doing multiple condition filter in pandas&lt;/span&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># having two conditions simultaneously&lt;/span&gt;</span>
df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'Is_Direct'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;</span><span class="token operator">&amp;</span>amp<span class="token punctuation">;</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'Price'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;</span><span class="token operator">&amp;</span>lt<span class="token punctuation">;</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">210</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># having OR conditions&lt;/span&gt;</span>
df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'Has_luggage'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> ⎮ <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'Price'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;</span><span class="token operator">&amp;</span>lt<span class="token punctuation">;</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token number"</span><span class="token operator">&gt;</span><span class="token number">200</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># having a negating condition and full condition&lt;/span&gt;</span>
df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token operator"</span><span class="token operator">&gt;</span><span class="token operator">~</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'Is_Direct'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span> ⎮ <span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">(</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>df<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">[</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token string"</span><span class="token operator">&gt;</span><span class="token string">'Has_luggage'</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">)</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span><span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token punctuation"</span><span class="token operator">&gt;</span><span class="token punctuation">]</span><span class="token operator">&lt;</span><span class="token operator">/</span>span<span class="token operator">&gt;</span>


<span class="token operator">&lt;</span>span <span class="token keyword">class</span><span class="token operator">=</span><span class="token string">"token comment"</span><span class="token operator">&gt;</span><span class="token comment"># &lt;/span&gt;</span>
<span class="token operator">&lt;</span><span class="token operator">/</span>code<span class="token operator">&gt;</span><span class="token operator">&lt;</span><span class="token operator">/</span>pre<span class="token operator">&gt;</span>
1 id="yandex-practicum---data-scientist">Yandex Practicum - Data Scientist</h1>
<h2 id="sprint-1-notes">Sprint 1 Notes</h2>
<p>Python code from the course:</p>
<pre class=" language-py"><code class="prism  language-py">
<span class="token comment"># Exclude values from a data-frame</span>
data <span class="token operator">=</span> data<span class="token punctuation">[</span>data<span class="token punctuation">[</span><span class="token string">'subcategory_id'</span><span class="token punctuation">]</span> <span class="token operator">!=</span>  <span class="token string">'total'</span><span class="token punctuation">]</span>

<span class="token comment"># as type conversion</span>
df<span class="token punctuation">[</span><span class="token string">'column'</span><span class="token punctuation">]</span> <span class="token operator">=</span> df<span class="token punctuation">[</span><span class="token string">'column'</span><span class="token punctuation">]</span><span class="token punctuation">.</span>astype<span class="token punctuation">(</span><span class="token string">'int'</span><span class="token punctuation">)</span>

<span class="token comment"># datatime in python, - Python has a specific format for datetime called 'datetime'. We can use the to_datetime() to change the values into date-time</span>


<span class="token comment"># —%d: day of the month (01 to 31)</span>

<span class="token comment"># —%m: month (01 to 12)</span>

<span class="token comment"># —%Y: four-digit year (2019)</span>

<span class="token comment"># — Z: standard separator for date and time</span>

<span class="token comment"># —%H: hour in 24-hour format</span>

<span class="token comment"># —%I: hour in 12-hour format</span>

<span class="token comment"># —%M: minutes (00 to 59)</span>

<span class="token comment"># —%S: seconds (00 to 59)</span>


<span class="token comment"># conversion step</span>
arrivals<span class="token punctuation">[</span><span class="token string">'date_datetime'</span><span class="token punctuation">]</span><span class="token operator">=</span> pd<span class="token punctuation">.</span>to_datetime<span class="token punctuation">(</span>arrivals<span class="token punctuation">[</span><span class="token string">'date'</span><span class="token punctuation">]</span><span class="token punctuation">,</span> <span class="token builtin">format</span><span class="token operator">=</span><span class="token string">'%d.%m.%YZ%H:%M:%S'</span><span class="token punctuation">)</span>

<span class="token comment"># There are all kinds of different ways to represent dates and times, but a particularly uncommon one is the unix time format.</span>

<span class="token comment"># The idea is simple: It’s the number of seconds that have passed since 00:00:00 on January 1, 1970. Unix time corresponds to the Coordinated Universal Time, or UTC.</span>

<span class="token comment"># getting the month equally</span>
arrivals<span class="token punctuation">[</span><span class="token string">'month'</span><span class="token punctuation">]</span> <span class="token operator">=</span> pd<span class="token punctuation">.</span>DatetimeIndex<span class="token punctuation">(</span>arrivals<span class="token punctuation">[</span><span class="token string">'date'</span><span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">.</span>month

<span class="token comment">#There’s a function called try-except that we use when we’re working with unpredictable data.</span>
<span class="token comment"># You add the source code to the try block, and if there’s a problem with it, the code in the except block will be executed instead.</span>

a <span class="token operator">=</span>  <span class="token number">1</span>

b <span class="token operator">=</span>  <span class="token number">0</span>

<span class="token keyword">try</span><span class="token punctuation">:</span>

<span class="token keyword">print</span><span class="token punctuation">(</span>a <span class="token operator">/</span> b<span class="token punctuation">)</span>

<span class="token keyword">except</span><span class="token punctuation">:</span>

<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">'Check the values of the parameters a and b'</span><span class="token punctuation">)</span>

<span class="token keyword">print</span> <span class="token punctuation">(</span><span class="token string">'By the way, good afternoon'</span><span class="token punctuation">)</span>

  

<span class="token comment"># usage</span>

position <span class="token operator">=</span> <span class="token punctuation">[</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-01'</span><span class="token punctuation">,</span> <span class="token string">'- 6'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-02'</span><span class="token punctuation">,</span> <span class="token string">'+5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-03'</span><span class="token punctuation">,</span> <span class="token string">' 5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-04'</span><span class="token punctuation">,</span> <span class="token string">'4'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-05'</span><span class="token punctuation">,</span> <span class="token string">'5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-06'</span><span class="token punctuation">,</span> <span class="token string">'5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-07'</span><span class="token punctuation">,</span> <span class="token string">'4'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-08'</span><span class="token punctuation">,</span> <span class="token string">'Error 5'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-09'</span><span class="token punctuation">,</span> <span class="token string">'3'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">[</span><span class="token string">'2019-05-10'</span><span class="token punctuation">,</span> <span class="token string">'3'</span><span class="token punctuation">]</span><span class="token punctuation">,</span>

<span class="token punctuation">]</span>

total_position <span class="token operator">=</span>  <span class="token number">0</span>
count_lines <span class="token operator">=</span>  <span class="token number">0</span>
wrong_lines <span class="token operator">=</span>  <span class="token number">0</span>

  

<span class="token keyword">for</span> row <span class="token keyword">in</span> position<span class="token punctuation">:</span>

<span class="token keyword">try</span><span class="token punctuation">:</span>

count_lines <span class="token operator">+=</span>  <span class="token number">1</span>

level <span class="token operator">=</span>  <span class="token builtin">int</span><span class="token punctuation">(</span>row<span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">]</span><span class="token punctuation">)</span>

total_position <span class="token operator">+=</span> level

<span class="token keyword">except</span><span class="token punctuation">:</span>

wrong_lines <span class="token operator">+=</span>  <span class="token number">1</span>

  

<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">"Total measurements"</span><span class="token punctuation">,</span> count_lines<span class="token punctuation">)</span>

<span class="token keyword">print</span><span class="token punctuation">(</span><span class="token string">"Total erroneous rows"</span><span class="token punctuation">,</span> wrong_lines<span class="token punctuation">)</span>

<span class="token comment"># joining in python</span>
data_subcategory <span class="token operator">=</span> data<span class="token punctuation">.</span>merge<span class="token punctuation">(</span>subcategory_dict<span class="token punctuation">,</span> on<span class="token operator">=</span><span class="token string">'subcategory_id'</span><span class="token punctuation">,</span> how<span class="token operator">=</span><span class="token string">'left'</span><span class="token punctuation">)</span>

<span class="token comment"># count the duplicated data</span>
data<span class="token punctuation">[</span><span class="token string">'column'</span><span class="token punctuation">]</span><span class="token punctuation">.</span>duplicated<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token comment"># drop duplicates</span>
stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span><span class="token punctuation">.</span>drop_duplicates<span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token comment"># lower the case</span>
pd<span class="token punctuation">.</span><span class="token builtin">str</span><span class="token punctuation">.</span>lower<span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token comment"># whole process</span>
<span class="token keyword">import</span> pandas <span class="token keyword">as</span> pd

stock <span class="token operator">=</span> pd<span class="token punctuation">.</span>read_csv<span class="token punctuation">(</span><span class="token string">'/datasets/stock_upd_eng.csv'</span><span class="token punctuation">)</span>

stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">'item'</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">str</span><span class="token punctuation">.</span>lower<span class="token punctuation">(</span><span class="token punctuation">)</span>

apple <span class="token operator">=</span> stock<span class="token punctuation">[</span>stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">==</span>  <span class="token string">'apple iphone xr 64gb'</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token string">'count'</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span>

samsung <span class="token operator">=</span> stock<span class="token punctuation">[</span>stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">==</span>  <span class="token string">'samsung galaxy a30 32gb'</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token string">'count'</span><span class="token punctuation">]</span><span class="token punctuation">.</span><span class="token builtin">sum</span><span class="token punctuation">(</span><span class="token punctuation">)</span>

stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span> <span class="token operator">=</span> stock<span class="token punctuation">[</span><span class="token string">'item_lowercase'</span><span class="token punctuation">]</span><span class="token punctuation">.</span>drop_duplicates<span class="token punctuation">(</span><span class="token punctuation">)</span>

  

stock <span class="token operator">=</span> stock<span class="token punctuation">.</span>dropna<span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">.</span>reset_index<span class="token punctuation">(</span>drop<span class="token operator">=</span><span class="token boolean">True</span><span class="token punctuation">)</span>

  
  

<span class="token comment">## defining a function with comments</span>
<span class="token keyword">def</span>  <span class="token function">age_group</span><span class="token punctuation">(</span>age<span class="token punctuation">)</span><span class="token punctuation">:</span>
<span class="token triple-quoted-string string">
# Yandex Practicum - Data Scientist

## Sprint 1 Notes

Python code from the course:
```py 

# Exclude values from a data-frame
data = data[data['subcategory_id'] !=  'total']

# as type conversion
df['column'] = df['column'].astype('int')

# datatime in python, - Python has a specific format for datetime called 'datetime'. We can use the to_datetime() to change the values into date-time


# —%d: day of the month (01 to 31)

# —%m: month (01 to 12)

# —%Y: four-digit year (2019)

# — Z: standard separator for date and time

# —%H: hour in 24-hour format

# —%I: hour in 12-hour format

# —%M: minutes (00 to 59)

# —%S: seconds (00 to 59)


# conversion step
arrivals['date_datetime']= pd.to_datetime(arrivals['date'], format='%d.%m.%YZ%H:%M:%S')

# There are all kinds of different ways to represent dates and times, but a particularly uncommon one is the unix time format.

# The idea is simple: It’s the number of seconds that have passed since 00:00:00 on January 1, 1970. Unix time corresponds to the Coordinated Universal Time, or UTC.

# getting the month equally
arrivals['month'] = pd.DatetimeIndex(arrivals['date']).month

#There’s a function called try-except that we use when we’re working with unpredictable data.
# You add the source code to the try block, and if there’s a problem with it, the code in the except block will be executed instead.

a =  1

b =  0

try:

print(a / b)

except:

print('Check the values of the parameters a and b')

print ('By the way, good afternoon')

  

# usage

position = [

['2019-05-01', '- 6'],

['2019-05-02', '+5'],

['2019-05-03', ' 5'],

['2019-05-04', '4'],

['2019-05-05', '5'],

['2019-05-06', '5'],

['2019-05-07', '4'],

['2019-05-08', 'Error 5'],

['2019-05-09', '3'],

['2019-05-10', '3'],

]

total_position =  0
count_lines =  0
wrong_lines =  0

  

for row in position:

try:

count_lines +=  1

level =  int(row[1])

total_position += level

except:

wrong_lines +=  1

  

print("Total measurements", count_lines)

print("Total erroneous rows", wrong_lines)

# joining in python
data_subcategory = data.merge(subcategory_dict, on='subcategory_id', how='left')

# count the duplicated data
data['column'].duplicated().sum()

# drop duplicates
stock['item_lowercase'] = stock['item_lowercase'].drop_duplicates()

# lower the case
pd.str.lower()

# whole process
import pandas as pd

stock = pd.read_csv('/datasets/stock_upd_eng.csv')

stock['item_lowercase'] = stock['item'].str.lower()

apple = stock[stock['item_lowercase'] ==  'apple iphone xr 64gb']['count'].sum()

samsung = stock[stock['item_lowercase'] ==  'samsung galaxy a30 32gb']['count'].sum()

stock['item_lowercase'] = stock['item_lowercase'].drop_duplicates()

  

stock = stock.dropna().reset_index(drop=True)

  
  

## defining a function with comments
def  age_group(age):
"""
The function returns the age group according to age value, by using the following rules:

—'children', with age value &lt;<= 18 years

—'adult', with age value over 18 and up to 64

—'retired' for all other cases
"""</span>

<span class="token keyword">if</span> age <span class="token operator">&lt;=</span>  <span class="token number">18</span><span class="token punctuation">:</span>

<span class="token keyword">return</span>  <span class="token string">'child'</span>

<span class="token keyword">if</span> age <span class="token operator">&lt;=</span>  <span class="token number">64</span><span class="token punctuation">:</span>

<span class="token keyword">return</span>  <span class="token string">'adult'</span>

<span class="token keyword">return</span>  <span class="token string">'retired'</span>

<span class="token comment">## text analytics</span>

<span class="token comment"># using the example</span>

text <span class="token operator">=</span>  <span class="token string">'Heard melodies are sweet, but those unheard Are sweeter; therefore, ye soft pipes, play on;'</span>

words <span class="token operator">=</span> nltk<span class="token punctuation">.</span>word_tokenize<span class="token punctuation">(</span>text<span class="token punctuation">)</span>

<span class="token keyword">print</span><span class="token punctuation">(</span>words<span class="token punctuation">)</span>

  
<span class="token comment"># lemmitization</span>

<span class="token comment"># WordNet Lemmatizer is imported as follows:</span>

<span class="token keyword">import</span> nltk

<span class="token keyword">from</span> nltk<span class="token punctuation">.</span>stem <span class="token keyword">import</span> WordNetLemmatizer

wordnet_lemma <span class="token operator">=</span> WordNetLemmatizer<span class="token punctuation">(</span><span class="token punctuation">)</span>

</code></pre>
<h2 id="sprint-3">Sprint 3</h2>
<h5 id="commands">Commands</h5>
<pre class=" language-py"><code class="prism  language-py"><span class="token comment"># using the parameters of the read_csv file</span>
<span class="token builtin">file</span> <span class="token operator">=</span> pd<span class="token punctuation">.</span>read_csv<span class="token punctuation">(</span><span class="token string">'file.csv'</span><span class="token punctuation">,</span> sep<span class="token operator">=</span><span class="token string">';'</span><span class="token punctuation">,</span> decimal<span class="token operator">=</span><span class="token string">','</span><span class="token punctuation">)</span>
<span class="token comment">## sep is for pointing out the separator and decimal parameter is for numeric values</span>

<span class="token comment"># histogram parameters</span>
df<span class="token punctuation">.</span>hist<span class="token punctuation">(</span>bins <span class="token operator">=</span> <span class="token number">10</span><span class="token punctuation">,</span> <span class="token builtin">range</span><span class="token operator">=</span> <span class="token punctuation">(</span><span class="token builtin">min</span><span class="token punctuation">,</span> <span class="token builtin">max</span><span class="token punctuation">)</span><span class="token punctuation">)</span>

<span class="token comment"># Boxplot parameters</span>
<span class="token keyword">import</span> matplotlib<span class="token punctuation">.</span>pyplot <span class="token keyword">as</span> plt 

<span class="token comment"># setting the dimensions of the chart</span>
plt<span class="token punctuation">.</span>ylim<span class="token punctuation">(</span><span class="token operator">-</span><span class="token number">50</span><span class="token punctuation">,</span> <span class="token number">500</span><span class="token punctuation">)</span> 
plt<span class="token punctuation">.</span>xlim<span class="token punctuation">(</span><span class="token number">0</span><span class="token punctuation">,</span> <span class="token number">200</span><span class="token punctuation">)</span>

<span class="token comment"># Doing multiple condition filter in pandas</span>

<span class="token comment"># having two conditions simultaneously</span>
df<span class="token punctuation">[</span><span class="token punctuation">(</span>df<span class="token punctuation">[</span><span class="token string">'Is_Direct'</span><span class="token punctuation">]</span><span class="token punctuation">)</span> <span class="token operator">&amp;</span> <span class="token punctuation">(</span>df<span class="token punctuation">[</span><span class="token string">'Price'</span><span class="token punctuation">]</span> <span class="token operator">&lt;</span> <span class="token number">210</span><span class="token punctuation">)</span><span class="token punctuation">]</span>

<span class="token comment"># having OR conditions</span>
df<span class="token punctuation">[</span><span class="token punctuation">(</span>df<span class="token punctuation">[</span><span class="token string">'Has_luggage'</span><span class="token punctuation">]</span><span class="token punctuation">)</span> ⎮ <span class="token punctuation">(</span>df<span class="token punctuation">[</span><span class="token string">'Price'</span><span class="token punctuation">]</span> <span class="token operator">&lt;</span> <span class="token number">200</span><span class="token punctuation">)</span><span class="token punctuation">]</span>

<span class="token comment"># having a negating condition and full condition</span>
df<span class="token punctuation">[</span><span class="token operator">~</span><span class="token punctuation">(</span><span class="token punctuation">(</span>df<span class="token punctuation">[</span><span class="token string">'Is_Direct'</span><span class="token punctuation">]</span><span class="token punctuation">)</span> ⎮ <span class="token punctuation">(</span>df<span class="token punctuation">[</span><span class="token string">'Has_luggage'</span><span class="token punctuation">]</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">]</span>


<span class="token comment"># </span>
</code></pre>


if age <=  18:

return  'child'

if age <=  64:

return  'adult'

return  'retired'

## text analytics

# using the example

text =  'Heard melodies are sweet, but those unheard Are sweeter; therefore, ye soft pipes, play on;'

words = nltk.word_tokenize(text)

print(words)

  
# lemmitization

# WordNet Lemmatizer is imported as follows:

import nltk

from nltk.stem import WordNetLemmatizer

wordnet_lemma = WordNetLemmatizer()

```

## Sprint 3

##### Commands

```py
# using the parameters of the read_csv file
file = pd.read_csv('file.csv', sep=';', decimal=',')
## sep is for pointing out the separator and decimal parameter is for numeric values

# histogram parameters
df.hist(bins = 10, range= (min, max))

# Boxplot parameters
import matplotlib.pyplot as plt 

# setting the dimensions of the chart
plt.ylim(-50, 500) 
plt.xlim(0, 200)

# Doing multiple condition filter in pandas

# having two conditions simultaneously
df[(df['Is_Direct']) & (df['Price'] < 210)]

# having OR conditions
df[(df['Has_luggage']) ⎮ (df['Price'] < 200)]

# having a negating condition and full condition
df[~((df['Is_Direct']) ⎮ (df['Has_luggage']))]

dfdsf
# 
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMTU1MzgzOTIsNDQ4NTE3MjE5XX0=
-->