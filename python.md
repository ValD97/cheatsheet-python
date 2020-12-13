# Cheatsheet Python

Here's a cheatsheet for the python's knowledge I've learned doing the Advent of Code 2020.

## Table Content
* Global syntax
* Types
* Arrays
* Dictionaries
* Tuples
* Functions
* Class
* File handling
* Error handling

## Global syntax
Tabulation is *everything* in python. They must be constant.
```python
if True:
  # good
     # not good
```
### Variables
There's no required keyword to declare a variable.
```python
some_var = "hello world"
another_var = 123
```
A new block of code (class, function, condition, loop, etc) is always introduced by ':' at the end of a line.
### Conditions
A condition follows this syntax :
```python

if test():
  print("this is true")
elif test2():
  print("elif is true")
else:
  print("the previous conditions where falses")
```
### Loops
There's different way to perform a loop (for, while) :
```python
# "for" loop

# Loop over numbers
for index in range(10):
  print(index) # Will display numbers from 0 to 9

array = ["a", "b", "c", "d", "e"]
for element in array:
  print(element) # Will display on multiple lines a, b, c, d, e

# "while" Loop
while True:
  do_something()
```
*In case you're searching for it : there is no do ... while syntax in python*
## Types
By default, python determines itself the type of the variables you declare.
If you need to cast a variable into another type, many methods exists according to the desired type :
```python
# Cast string to int :
a = int("12") # a = 12
b = str(1239) # b = "1239"
c = int(98.3) # c = 98
d = float(34) # d = 34.0
```
## Arrays
It's possible to declare an empty array or with some values within :
```python
array = [] # emtpy array
another_array = [123, "abc", 72.8] # you can put values with different types in a list if you want
```
To access a value, just call the index you want :
```python
array = ["hello", "world"]
print(array[1]) # will print "world" on the standard output
```
You can also use negative index to start your search from the end :
```python
array = ["this", "is", "a", "test"]
print(array[-1], array[-2]) # will display "test, a" on the standard output
```
If you want to get the index of a value, you can use the index(...) method :
```python
array = ["this", "is", "a", "test"]
print(array.index("a")) # will print "2" on standard output
```
If you want to reverse an array, there's also a syntax for that :
```python
array = ["this", "is", "a", "test"]
reversed_array = array[::-1]
```
You can slice an array with the following syntax :
```python
array = ["this", "is", "a", "test"]
new_array = array[0:2] # will create a new array with the first two elements in array
```
_Warning : array[a:b] will get the elements from index a to index b - 1, the b-th index won't be included_
If you want to copy a list, you can use the list(...) constructor :
```python
list1 = ["a", "b", "c"]
list2 = list(list1) # create a copy of list1
list3 = list1 # doesn't create a copy, just copy the reference.
              # Here, update list3 will update list1 too.
```
## Dictionaries
To declare a dictionary :
```python
dict = {} # empty dictionary
dict2 = {"key": "value", "key2": "value2"} # a key can be made of characters/numbers
```
To access values, specify the desired key :
```python
dict = {"key": "value", "key2": "value2"} # a key can be made of characters/numbers
print(dict["key"]) # will print "value" on standard output
```
To loop over keys in a dictionary, you can use the keys() method :
```python
dict = {"key": "value", "key2": "value2"}
for key in dict.keys():
  print(key)
```
## Tuples
A tuple is some kind of an immutable set you can represent like (a, b). You can have more than "just" 2 values in a tuple, like (a, b, c).
To create a tuple :
```python
tuple = ("value_a", "value_b")
```
To access one of the value of the tuple, specify the index of the element within the tuple :
```python
tuple = ("value_a", "value_b", "value_c")
print(tuple[0]) # will print "value_a" on standard output
```
## Functions
A fonction follow this syntax :
```python
def my_function(arg1, arg2):
  return arg1 + arg2
```
When a structure (list, dictionary, object) is given as argument of a function, it is given by reference. That means at least you redefine completely the given structure, the function can affect the original structure and not only the argument.
Examples :
```python
def update_array(array):
  array[1] = "has changed"

t = ["War", "never changes"]
update_array(t)
print(" ".join(t)) # will print "War has changed on standard output
```
```python
def wont_update_array(array):
  array = ["Fresh new array !"] # Here, instead of "just" updating the array,
                                # we're creating another one.

t = ["War", "never changes"]
update_array(t)
print(" ".join(t)) # will print "War never changed" on standard output
```
## Class
A class can be defined with this syntax :
```python
class Book:
  def __init__(self, title, author): # The __init__ method is mandatory. It's the class' constructor.
    self.title = title # "self" is a mandatory argument, it allows you to declare class parameters
                       # and to initialize them.
    self.author = author

book = Book("1984", "George Orwell")
```
## File handling
To open a file in read-only :
```python
file_descriptor = open("path", "r") # the "r" specify "read"
```
To parse the lines of the file, you can just iterate on the file descriptor :
```python
file_descriptor = open("path", "r") # the "r" specify "read"
for line in file_descriptor:
  print(line)
```
To close the file descriptor, use the close() method :
```python
file_descriptor = open("path", "r") # the "r" specify "read"
file_descriptor.close()
```
## Error handling
Because everyone loves handling its errors :
```python
try:
  # An instruction that may rise an error
except:
  # do whatever you want. If you want to do nothing, just use :
  pass
```
You can specify the error you want to catch :
```python
dict = {"roger": "rabbit"}
try:
  print(dict["louis"])
except KeyError:
  # do whatever you want. If you want to do nothing, just use :
  print("this key doesn't exist")
```
