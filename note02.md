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

## 3: Tuples

## 4: Sets


## 5: Dictionary
