# Understanding Variables in Python

In Python, a variable is a symbolic name that is used to store and manipulate values. Variables are like containers or labels that hold data, and they allow you to refer to and manipulate that data throughout your program. Here are some key points about Python variables:

1. **Variable Assignment:**
   - You can create a variable by assigning a value to it using the assignment operator (`=`).
   - The general syntax is: `variable_name = value`.

```python
# Example of variable assignment
x = 10
name = "John"

```

2. **Variable Naming Rules:**

   - Variable names in Python can contain letters (a-z, A-Z), numbers (0-9), and underscores (_).

   - They cannot start with a number.

   - Python is case-sensitive, so `variable` and `Variable` are different.

```python
# Valid variable names
age = 25
user_name = "Alice"

```

3. **Dynamic Typing:**

   - Python is dynamically typed, which means you don't need to explicitly declare the type of a variable.

   - The type of a variable is determined at runtime based on the type of value it is holding.

```python
# Dynamic typing example
x = 10      # x is an integer
x = "hello" # x is now a string

```



4. **Data Types:**
   - Variables in Python can hold values of various data types, such as integers, floats, strings, lists, tuples, dictionaries, and more.

```python
# Variables with different data types
age = 25          # integer
height = 5.9      # float
name = "John"     # string
is_student = True  # boolean

```



5. **Reassignment:**
   - You can change the value of a variable by assigning a new value to it.

```python
x = 5
print(x)  # Output: 5

x = x + 1
print(x)  # Output: 6
```

6. **Constants:**
   - Although Python doesn't have a strict concept of constants, it is a convention to use uppercase names for variables whose values should not be changed.

```python
PI = 3.14
```

7. **Deleting Variables:**
   - You can use the `del` statement to delete a variable.

```python
x = 10
print(x)  # Output: 10

del x     # Deletes the variable x
# print(x)  # This would raise an error since x is no longer defined

```

Understanding how to use variables is fundamental to programming in Python, as they allow you to store, retrieve, and manipulate data in your programs.