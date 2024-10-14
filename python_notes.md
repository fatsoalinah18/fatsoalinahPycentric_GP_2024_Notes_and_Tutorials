 # Python Notes
- Python is case-sensitive.
- It uses snake case.

 ## Data types
 - Integers **(int)**
 - String **(str)**
 - Float -**float**
 - Boolean **(bool)**

> - Using the '+' operator with strings is known as __concatenation__.
> - Data conversion assists with data quality issues.
> 

## input()
 - **input()** - Used to receive input from user.
 - Always collects data as a string by default.

## print()
- **print** - Used to display output.

## type()
- **type()** - an instruction used to check the data type stored in a variable.
~~~
x = "18"
print(type(x))
~~~
### Output
~~~
<class 'str'>
~~~

# Explicit conversions
These are performed by an instruction given by a programmer.

## 1. int()
-  **int()** - an instruction that converts any type of value into an integer.
~~~
x = "18"
print(type(x))
y = int(x)
print(type(y))
~~~

### Output
~~~
<class 'str'>
<class 'int'>
~~~

## 2. float()
- __float()__ - an instruction that converts any type of value into a float.
~~~
x = "18"
print(type(x))
y = float(x)
print(type(y))
~~~
### Output
~~~
<class 'str'>
<class 'float'>
~~~
## 3. str()
- **str()** - an instruction that converts any type of value into a string.
~~~
x = 18
print(type(x))
y = str(x)
print(type(y))
~~~
### Output
~~~
<class 'int'>
<class 'str'>
~~~

# Implicit conversion
These are performed by an instruction given by the computer.

### Example
~~~
x = 5
y = 2
z = x/y  #float - implicit conversion
print(z)
~~~

### Output
~~~
2.5
~~~
# Comparison operator
**Comparison operations** - Key to the development of computer programs.

- The result of a comparison operation in Python is either **True** or **False.**
> Both the "__and__" and "**or**" operators are in lowercase.
>
>
## "and" operator
- T **and** T = T
- Every other combination = F

## "or" operator
- F **or** F = F
- Any combination with T = T

# Control flow
### Sequences
The computer runs your code in order, from top to bottom.

### Iterations
- Executing an instruction repeatedly. 
- Iteration is commonly represented as a __loop__.
- Iteration is used to automate tasks that need to be done over and over again.
- Iteration makes your programs simpler, faster and reduces errors.

_Example: Putting your favorite song on repeat._

### Selections

- Specifies when to follow each path.

_Example: Smartwatches notify the wearer if their heart rate goes outside the normal range ._

~~~
Real computer programs perform complex tasks by combining the 3 techniques.
~~~
### if-else statements
### elif (else if)


## Algorithms
- __Algorithm__ is a set of step-by-step instructions to complete a task, placed in a certain order.
### Ways to represent an algorithm

- **Pseudocode** is a simplified language that is a bit closer to a programming language. It is not specific to one programming language.
~~~
start
repeat until authorized = true
  INPUT log_in
access_granted = true
~~~
- **Flowcharts** help to visualize algorithms.

# Loops
## for loop
- A **for** loop is used to execute the same instruction over and over again, a specific number of times.

### Example:
~~~|
for i in range(3):
print("Hi Tshego.")
~~~
### Output
~~~
Hi Tshego.
Hi Tshego.
Hi Tshego.
~~~
- **Indentation** is the spaces at the beginning of lines.

The code you want to display in a for loop, i.e. your print() statement, should be indented in python.

- To signal the start of the iteration block, the initial loop statement must be followed by a **colon**.

**NB: In general, use `for` loops when the number of iterations is known.**

## While loop

- They can be used even when you don’t know how many iterations will be needed.
- `While` loops  repeat code whilst a condition holds true.
- A `counter` is a variable that keeps track of the number of iterations.
- An infinite loop is possible with this loop and counters help avoid them.

~~~
seats = 300  
while seats > 0: 
  print("Sell ticket") 
seats = seats - 1 #counter
~~~

**NB: In general, use `While` loops when there is a condition that needs to be met.**

**NOTE**
~~~
Calculations with <,> results to boolean data type.
~~~

# Collections
- `Lists` are ordered collections of items. 
- **Lists** allow you to store a collection of multiple values in a single variable.
- They can store any data type.
- You can access an item in a list using its position or **index number.**
- Negative indexing - indexing from the end.

~~~
cart = ["milk", "tea", "jam"]
~~~

## Slicing
- `Slicing` allows you to extract a portion of a list. Starting and stopping indexes are separated by a **colon**.
- *Strings* are **immutable** in python while _list_ are **mutable**.
- The starting index is inclusive and the stopping index is exclusive.
- Omitting the starting index will slice data from the first element. An in that same way, omitting the stopping index will slice until the very last element and it's called **negative indexing**. 
- Negative indexing means that the last value of a sequence has an index of -1.
- It's possible to combine positive with negative indexing when slicing.

### Example
~~~
animals =['dog', 'cat', 'bird', 'cow'] 
print(animals[:1]) 

~~~
### Output
~~~
['dog']
~~~

# Loops and Lists
## Iterating over Lists

- To check if an item is in a particular list the `in` operator is used. It returns True if the item occurs one or more times in the list, and False if it doesn’t.

### Example

~~~
products = ['milk', 'eggs', 'apples']
print('bread' in products)
~~~

### Output
~~~
False
~~~

- The __for__ loop can be used with the in operator to iterate over lists and perform the sam eoperation for each element.

### Example

~~~
products = ['milk', 'eggs', 'apples']
for i in products:
  print(i)
~~~

### Output
~~~
milk
eggs
apples
~~~

## Nested Loops

### Example

~~~
ranks = ["Ace", "King", "Queen"]
suits = ["Hearts", "Clubs", "Diamonds"]

for rank in ranks:
  for suit in suits:
    print(rank, suit)
~~~

### Output

~~~
Ace Hearts
Ace Clubs
Ace Diamonds
King Hearts
King Clubs
King Diamonds
Queen Hearts
Queen Clubs
Queen Diamonds
~~~

## Iterations and selections

### Initializing a counter and using a for loop.
~~~
counter = 0
devices = ['PC', 'TV', 'PS', 'TV', 'PS', 'Xbox', 'TV']
for device in devices:
  if device == 'TV':
    counter = counter +1
print("Number of TVs:", counter)
~~~

### Output
~~~
Number of TVs: 3
~~~
### break and continue statement

- The `break` statement stops a loop hen a condition is met.


- The `continue` statement allows you to skip the current iteration of a loop when a certain condition is true.

# Functions

## Functions

- A `function` contains code to perform a task, and it has to be called in order to be used.

- `range()` and `print()` are examples of built-in functions.

## String functions
- All these functions use __dot notation__.
- `upper()` - Changes the string to all in uppercase.

~~~
print('Smartphone'.upper())
# Output = SMARTPHONE
~~~

- `lower()` -Changes the string to all in lowercase.


~~~
print('Smartphone'.lower())

# Output = smartphone
~~~

- `capitalize()` - Converts the first character of a string to uppercase, while making the remaining characters lowercase.
- `find()` - checks if a character (or a pattern of characters) is present in a string. It returns `-1` if the value can't be found in the string.

## Built-in list functions

- `len()` - When used on lists, it returns the number of items in the list.
- `append()` - Adds a new item at the end of a list. This function uses `dot notation` as it's specific to lists.
- `insert()` - It allows the addition of an element to a list at a specific position.

~~~
items.insert(2,"marker")
~~~

- `pop()` - It removes an element from a list. The only argumentt is the index of the element to be removed.

## Custom functions

A **function** is a reusable block of code.

### Defining a function

~~~
def greet():
  print("Hello from a function")
  print("Have a great day")
~~~

When this function is called, it will display the two `print()` statements.

- `return()` - It sends the results of a function back. It is mostly helpful for the continuous use of the result.

## More on custom functions

- `rect()` - It calculates the area and perimeter of a rectangle. An it takes two paramenters, **length** and **width**.

~~~
def rect(length, width):
  area = length * width
  perimeter = 2 * length + 2 * width
  return area, perimeter 

x, y = rect(50, 100) #2 variables
print(x, y)
~~~


