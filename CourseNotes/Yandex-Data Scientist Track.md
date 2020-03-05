
# Yandex Practicum - Data Scientist

## Sprint 1 Notes

Python codes from the course:
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

—'children', with age value <= 18 years

—'adult', with age value over 18 and up to 64

—'retired' for all other cases
"""

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
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzQyOTE4MjQ5LC0xMzkxNzY4NzM3XX0=
-->