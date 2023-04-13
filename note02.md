# Data Structures Complexity and Algorithms


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

## 4: Sets


## 5: Dictionary
