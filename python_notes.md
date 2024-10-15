 # Python Notes

## Variables and Data Types

- Variables store values and can be assigned using the `=` operator.

### Example:
~~~ 
x = 5
name = "Alice"
is_active = True
~~~

### Data Types:
- **int**: Integer values (`x = 5`)
- **float**: Decimal values (`y = 5.7`)
- **str**: Strings (`name = "Alice"`)
- **bool**: Boolean (`is_active = True`)

### Checking Data Types:
~~~ 
print(type(x))  # <class 'int'>
~~~

## Comments

- Comments in Python are written with a `#`.

### Example:
~~~ 
# This is a comment
print("Hello, World!")  # This prints a message
~~~

## Input and Output

- `print()` is used to display output, and `input()` is used to take user input.

### Example:
~~~ 
name = input("Enter your name: ")
print("Hello, " + name)
~~~

## Arithmetic Operators

- Addition: `+`
- Subtraction: `-`
- Multiplication: `*`
- Division: `/`
- Floor Division: `//`
- Modulus: `%`
- Exponent: `**`

### Example:
~~~ 
x = 5
y = 2
print(x + y)   # 7
print(x ** y)  # 25
~~~

## Comparison Operators

- Equal to: `==`
- Not equal to: `!=`
- Greater than: `>`
- Less than: `<`
- Greater than or equal to: `>=`
- Less than or equal to: `<=`

### Example:
~~~ 
x = 5
y = 10
print(x > y)   # False
~~~

## Logical Operators

- AND: `and`
- OR: `or`
- NOT: `not`

### Example:
~~~ 
x = 5
y = 10
print(x > 3 and y < 20)  # True
~~~

## Conditional Statements

- **if**, **elif**, and **else** are used for decision making.

### Example:
~~~ 
age = 18

if age >= 18:
  print("You are an adult.")
elif age > 12:
  print("You are a teenager.")
else:
  print("You are a child.")
~~~

### Output:

~~~ 
You are an adult.
~~~

## Loops

### For Loop:
- Repeats a block of code for a given sequence.

### Example:
~~~ 
for i in range(5):
  print(i)
~~~

### Output:

~~~ 
0
1
2
3
4
~~~

### While Loop:
- Repeats as long as a condition is true.

### Example:
~~~ 
count = 0
while count < 5:
  print(count)
  count += 1
~~~

### Output:

~~~ 
0
1
2
3
4
~~~

## Lists

- A **list** stores multiple items in a single variable.

### Example:
~~~ 
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # apple
~~~

### Modifying Lists:
~~~ 
fruits.append("orange")
fruits.remove("banana")
~~~

### List Methods:
- `append()`: Add an element to the end.
- `remove()`: Remove an element.
- `sort()`: Sort the list.

### Example:
~~~ 
numbers = [4, 2, 8, 1]
numbers.sort()
print(numbers)  # [1, 2, 4, 8]
~~~

## Tuples

- A **tuple** is similar to a list, but it's immutable (cannot be changed).

### Example:
~~~ 
colors = ("red", "green", "blue")
print(colors[1])  # green
~~~

## Dictionaries

- A **dictionary** stores data in key-value pairs.

### Example:
~~~ 
person = {"name": "Alice", "age": 25}
print(person["name"])  # Alice
~~~

### Modifying Dictionaries:
~~~ 
person["age"] = 26
person["city"] = "New York"
~~~

### Dictionary Methods:
- `keys()`: Returns all keys.
- `values()`: Returns all values.

### Example:
~~~ 
print(person.keys())    # dict_keys(['name', 'age', 'city'])
print(person.values())  # dict_values(['Alice', 26, 'New York'])
~~~

## Functions

- A **function** is a block of reusable code that performs a specific task.

### Defining a Function:
~~~ 
def greet(name):
  print("Hello, " + name)
~~~

### Calling a Function:
~~~ 
greet("Alice")  # Output: Hello, Alice
~~~

### Returning Values:
~~~ 
def add(x, y):
  return x + y

result = add(3, 5)
print(result)  # 8
~~~

### Multiple Parameters:
~~~ 
def rect(length, width):
  area = length * width
  perimeter = 2 * (length + width)
  return area, perimeter

x, y = rect(50, 30)
print(x, y)
~~~

### Output:

~~~ 
5000 300
~~~

## Parameters and Arguments

- A **parameter** is the name used in a function definition for the data that the function accepts.

- An **argument** is the actual value passed to the function when calling it.

### Example:
~~~ 
def square(x):  
  return x * x  

result = square(5)
print(result)
~~~

### Output:

~~~ 
25
~~~

## Scoping

- **Global variables** are those declared outside of any function and can be accessed anywhere within the code.

- **Local variables** are declared inside a function and can only be accessed within that specific function.

### Example:
~~~ 
a = 10 # Global

def example_func():  
  b = 5  # Local  
  print("Inside function:", b)

example_func()
print("Outside function:", a)
~~~

### Output:

~~~ 
Inside function: 5
Outside function: 10
~~~

## File Handling

Python allows you to work with files in multiple ways.

### Opening a File
- The `open()` function is used to open a file.

- You can specify the mode when opening a file: 

  - `'r'` for read (default mode).
  - `'w'` for write (creates a file if it doesn’t exist).
  - `'a'` for append (adds to the file without overwriting).
  - `'x'` for create (returns an error if the file exists).

### Example:

~~~ 
file = open("example.txt", "r")
print(file.read())
file.close()
~~~

### Writing to a File

- Use `'w'` or `'a'` mode to write to a file.

### Example:

~~~ 
file = open("example.txt", "w")
file.write("Hello, world!")
file.close()
~~~

### Reading from a File

- You can use methods such as `read()` or `readlines()` to read content from a file.

### Example:

~~~ 
file = open("example.txt", "r")
content = file.read()
print(content)
file.close()
~~~

### Output:

~~~ 
Hello, world!
~~~

### With Statement

- The `with` statement simplifies file handling by automatically closing the file.

### Example:

~~~ 
with open("example.txt", "r") as file:
  content = file.read()
  print(content)
~~~

## Error Handling

- Python provides error handling via the `try` and `except` blocks.

- If an error occurs within the `try` block, it jumps to the `except` block.

### Example:

~~~ 
try:
  print(5/0)
except ZeroDivisionError:
  print("You can't divide by zero!")
~~~

### Output:

~~~ 
You can't divide by zero!
~~~

### Catching Multiple Exceptions

- You can catch multiple types of exceptions by specifying multiple `except` blocks.

### Example:

~~~ 
try:
  file = open("not_existing_file.txt", "r")
except FileNotFoundError:
  print("File not found!")
except Exception as e:
  print("An error occurred:", e)
~~~

### Output:

~~~ 
File not found!
~~~

## Object-Oriented Programming (OOP)

- Python supports **object-oriented programming**, which uses **objects** and **classes** to organize code.

### Classes and Objects

- A **class** is like a blueprint for creating objects.
- An **object** is an instance of a class.

### Example:

~~~ 
class Dog:
  def __init__(self, name, breed):
    self.name = name
    self.breed = breed

  def bark(self):
    print(f"{self.name} is barking!")

dog1 = Dog("Buddy", "Golden Retriever")
dog1.bark()
~~~

### Output:

~~~ 
Buddy is barking!
~~~

### Inheritance

- **Inheritance** allows one class (child class) to inherit attributes and methods from another class (parent class).

### Example:

~~~ 
class Animal:
  def speak(self):
    print("Animal is speaking")

class Dog(Animal):
  def bark(self):
    print("Dog is barking")

dog = Dog()
dog.speak()
dog.bark()
~~~

### Output:

~~~ 
Animal is speaking
Dog is barking
~~~

## Python Modules

- A **module** is a file containing Python code that you can import and use in another file.

### Importing a Module

- Use the `import` keyword to bring in a module.

### Example:

~~~ 
import math
print(math.sqrt(16))  # 4.0
~~~

### Output:

~~~ 
4.0
~~~

### Importing Specific Functions

- You can import only specific functions from a module.

### Example:

~~~ 
from math import sqrt
print(sqrt(16))  # 4.0
~~~

