
## Week 1 Notes- Python Crash Course

* Division of two `int` in python always gives out a `float `
* Strings are not mutable 
* `strings.find()` can be used to fetch the location of a particular text in a string
* The variables in python just store the location of an item,  so if x = 5 and y = 5. In the background, the x and y will point to the same address
	* The address can be identified by using `id` command. `id(x)`

## Week 2 Notes- Python Crash Course

* We also have collections [Data Structures] in Python along with the basic data types- these are arrays and vectors to put in different data datatypes

* `list` is one of the basic collections in Python. `[]`are used to generate list 
	* mutable
	* ordered or sequential collection - sequence of elements matters
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
	* `x.remove(z)` - Remove z from the list
	* 

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAwNTQ3OTQzNywxMTE3MzE5MjcyLC0xMD
M5OTU5OTA3LDQwMTQwMzU5Niw5MDE0NTU3MjksLTUxMDU4Nzk3
MywtMTM4NzM1NDU5NywtOTU4MjI0MjM5LDE5NzQ3NjEwMDYsMT
g2MzIwMjE5NywtMTA1ODMyMTA1N119
-->