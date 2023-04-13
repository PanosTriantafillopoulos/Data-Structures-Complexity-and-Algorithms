# Data Structures


## 1: Matrices & List Comprehension
A matrix is a representation of numbers, symbols, or expressions in a 2-Dimensional Array. In Python we can create a data structure that has values in rows and columns (much like a table) by utilizing a list within a list. There are external modules that help this process, but we will be constructing them ourselves within python.

```python
# Representation of matrix A

matrix_A = [
  [1, 2, 3, 4],
  [5, 6, 7, 8]
]

# Accessing Matrix A
print('Row 1: %s' % matrix_A[0]) # outputs --> Row 1: [1, 2, 3, 4]
print('Value at Row 2 Column 2: %s' % matrix_A[1][1]) # outputs --> Value at Row 2 Column 2: 6
```
In python there is no data structure called a "Matrix".
Therefore, we are programming a list within a list and following the rules of a regular matrix:
- All rows must have the same number of values
- All columns must have the same number of values
- All items in the 2D List must have the same data types
- Since indexing always starts at 0 ... row 1 is technically located at matrix_A[0]

### List comprehension in Python 3
List comprehension is a concise method to create a list in Python 3.
The technique is used when:
- The list is a result of some operations applied to all its items.
- It is made from another sequence/iterable data.
- The list is a member of another list/sequence/iterable data that satisfies a certain condition

This is wheer the __lambda function__ would be used...
```python
# List comprehension example 1
squares = [i**2 for i in range(10)]

print('Our new result: %s' % squares) # output --> Our new result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
List comprehension consists of :
- A __Square Bracket__ containing an expression that describes the list
- One or more __For clause__ to explain itrs members
- Then a zero or more __if clauses__ depending on the complexit of the list

```python
# List comprehension example 2
a = [1,2,3]
b = [3,1,4]

result = [[x, y] for x in a for y in b if x != y]
print(result) # output --> [[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]

# List comprehension example 3
vec = [[1,2,3], [4,5,6], [7,8,9]]

result = [value for row in vec for value in row]
print('Vec as a single list of values: %s' % result) # outpust --> [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
Vec is an example of a matrix in python be using list of lists
## 2: Map & Filter
### The Map Function
The idea of a map function is to apply a function to an iterable data.

Format: map(function_name, sequence)
- function_name: any function (built-in or selfmade) that returns a desired value of choice
- sequence: any iterable data type

```python
# Example
def square(num):
    ''' squares the given num argument '''
    return num ** 2

array = list(range(1,11))
square_array = list(map(square, array))

print('Original Array:', array)
print('Array Squared:', square_array)
```
Original Array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Array Squared: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

Note: map function doesn’t return a specific data type, but rather, an python iterable data. Therefore, after we apply the map function, we just execute a list function on it.
### Filter Function
The idea of the filter function is to filter out items from a data set that meets a certain condition.

Format: filter(bool_returning_function, sequence)
- function: The function name we provide for filter() must be return a boolean value ... should also be able handle the items inside the sequence as its arguments.
- sequence: any iterable data type.

```python
def isOdd(x):
    ''' isOdd() returns True if x is odd.'''
    return x % 2 != 0

array = list(range(1,101))
odds = list(filter(isOdd, array))

print('Odd Numbers from 1 to 100:', odds) # will output all add numbers from one to 100
```
### Example using Both Filter and Map
```python
# Palindromic Numbers from 1 to 10000

def isPalindrome(x):
    ''' isPalindrome returns True if string X is a palindrome.'''
    return x == x[::-1]

array = list(range(1,10000))

palindromic_numbers = list(map(int, filter(isPalindrome, map(str, array))))
print('Palindromic Numbers from 1 to 10,000', palindromicNumbers)
```
Function Composition Breakdown
1. string version of the array --> map(str, array)
2. filter out the palindrome --> filter(isPalindrome, string version of the array)
3. remap all values back to integers --> map(int, palindromes)
4. turn the mapped integers iterable back inside a list --> list(palindromicIterables)

## 3: Tuples
Strings and Lists are basic iterable data types that are very similar with key differences:

Strings only allow alphanumeric characters and special symbols to represent text
Lists allow all data types as its items/members
Strings are immutable whereas Lists are mutable
These significant differences cause a headache when you require the following data structure:

It must be immutable
It must allow different datatypes as items
It must be iterable
It must be nestable (much like a list within a list)
All of these are solved with a data structure called: __Tuple__.
- Tuples are declared with parenthesis … aka round brackets
- () is an empty tuple
- (50,) is a singleton tuple; the comma is required
- Tuples are sliceable; therefore, indexable using square brackets
```python 
# Some Tuple Examples
tup = ('C', ' Java', 'Python')
empty_tup = ()
single_tup = ('Park',)

print(tup) # O: ('C', ' Java', 'Python')
print(empty_tup) # O: ()
print(single_tup) # O: ('Park',)

# Concatenation: Joining two tuples
a = (1,2,3)
b = (4,5,6)
concat_result = a + b
print('a+b:', concat_result)


# Repetition: Repeating a list multiple times
c = ('Hi!',)
repet_result = c * 3
print('c*3', repet_result)

# Membership: Check if a value exists in a tuple
d = a + b + c
print('d:', d)
print('\'Hi!\' in d:', 'Hi!' in d)
print('7 in d:', 7 in d)
# Packing
var_1 = 2
var_2 = 3
var_3 = 5

prime = var_1, var_2, var_3

print('Packed prime values:', prime)

# Unpacking and Repacking
fib = (0, 1, 1, 2, 3, 5, 8)

fib_0, fib_1, fib_n = fib[0], fib[1], fib[2:]
print('fib_0:', fib_0)
print('fib_1:', fib_1)
print('fib_n:', fib_n)
```
A singleton is an iterable data structure with only single item.
## 4: Sets
A set is an unordered collection with no duplicate elements in Python 3.

Set is a mathematical way to describe collection of different unique objects.

Built-in functions can be utilized on sets.
```python
# Defining a Set
example_set1 = {1, 2, 3}
example_set2 = {'h','e','l','l','o'}

print('example_set1:', example_set1)
print('example_set2:', example_set2) # Notice there is only 1 'l'; Also notice the order of the values outputted
print('--')

singleton_set = {7}
empty_set = set() # this is because {} is reversed for a different feature in python 3.

print('Singleton:', singleton_set)
print('Empty Set:', empty_set)

'''
output
example_set1: {1, 2, 3}
example_set2: {'o', 'e', 'h', 'l'}
--
Singleton: {7}
Empty Set: set()
'''
```
## 5: Dictionary
Dictionary (Associative Array, map, symbol table) is a data type that stores a collection of (key, value) pairs, such that each possible key appears at most once in the collection (This concept is an introduction to concepts similar to: hash table and search trees).
Dictionaries also use {} like sets; however, their individual item format is very different. Each item in a dictionary be a pair of key: value. Keys are unique address for a dictionary value’s location. Keys must be immutable (string, numbers, tuples, frozenset) and unique (therefore, two same key values cannot exist in a single dictionary)

dict(): Turns other data types to dictionaries.
```python
# Dictionary Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

# There are 3 items: each with their unique addresses and value
# Accessing
print('Sammy dict:', sammy)
print('Username:', sammy['username'])
print('Online Status:', sammy['online'])
print('Follower Count:', sammy['followers'])
'''
Output
Sammy dict: {'username': 'sammy', 'online': True, 'followers': 42}
Username: sammy
Online Status: True
Follower Count: 42
'''
```
### Updating a Dictionary
- We can modify existing values by referencing the key
- We can add new values to a dictionary by creating a new key
- We can overwrite a value at an existing key by referencing and recreating the value for it
```python
# Example of Updating Dictionary
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy['followers'] += 10 # We are adding 10 to the value located at key: 'followers'
sammy['verified'] = True # We added a new value at a new key: 'verified'
sammy['username'] = 'SammySammy'

print('Sammy Dict:', sammy) # O: Sammy Dict: {'username': 'SammySammy', 'online': True, 'followers': 52, 'verified': True}
```
### Deletion with Dictionary
- We can delete a key hence deleting the value connected to the key
- We can empty out the entire dictionary
- We can delete the dictionary (uncommonly used)
```python
# Example of Deletion In Dictionary
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

del sammy['followers'] # del is a keyword used to help us to execute a removal
print('followers key deleted:', sammy)

sammy.clear() # {} is considered an empty dict
print('emptying out a dictionary', sammy)
print('--\n\n')

del sammy
print('Deleting sammy, should create an error when referenced again', sammy)
```
Will produce errors as samy is no longer defined.
### Dictionary Methods
- A.keys() –> Returns a sequence of keys/addresses in A
- A.values() –> Returns a sequence of item values in A
- A.items() –> Returns a sequence of key,item pairs in A
- A.get(address) –> Returns the item value at address
- A.update(B) –> Extends A with the dictionary of key,value pairs of B
# Complexity & Algorithm
