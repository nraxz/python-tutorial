# Variable Types in Python

In Python, variables can hold values of various types. Here are some common variable types in Python:

1. **Integers (`int`):**

   - Whole numbers without a fractional component.

   ```python
   age = 25
   ```

2. **Floating-point Numbers (`float`):**

   - Numbers with a decimal point or in scientific notation.

   ```python
   height = 5.9
   ```

3. **Strings (`str`):**

   - Sequences of characters enclosed in single or double quotes.

   ```python
   name = "John"
   ```

4. **Booleans (`bool`):**

   - Represents either True or False.

   ```python
   is_student = True
   ```

5. **Lists (`list`):**

   - Ordered, mutable collections of elements.

   ```python
   numbers = [1, 2, 3, 4, 5]
   ```

6. **Tuples (`tuple`):**

   - Ordered, immutable collections of elements.

   ```python
   coordinates = (3, 4)
   ```

7. **Sets (`set`):**

   - Unordered collections of unique elements.

   ```python
   unique_numbers = {1, 2, 3, 4, 5}
   ```

8. **Dictionaries (`dict`):**

   - Unordered collections of key-value pairs.

   ```python
   person = {'name': 'Alice', 'age': 30}
   ```

9. **NoneType (`None`):**

   - Represents the absence of a value or a null value.

   ```python
   result = None
   ```

10. **Complex Numbers (`complex`):**

- Numbers with a real and an imaginary part.

```python
complex_num = 3 + 4j
```

These are some of the fundamental types, but Python is a dynamically typed language, which means that a variable's type is determined at runtime. Additionally, there are more specialized types and custom classes that can be used to represent specific kinds of data.

In Python, variable types are dynamically inferred based on the assigned values. The interpreter determines the type of a variable at runtime. In the case of `age = 25`, the interpreter recognizes `25` as an integer and assigns the variable `age` the type of integer. If you were to later assign a string value to `age`, the type would change accordingly. This flexibility is a characteristic of dynamic typing in Python.

### Interview Questions:

1. **What is dynamic typing in Python?**
   - **Answer:** Dynamic typing in Python means that the type of a variable is determined at runtime and can change during the execution of a program.
2. **How does Python handle variable typing?**
   - **Answer:** Python uses dynamic typing, where variables are associated with types based on the values they hold.
3. **Explain the concept of type inference in Python.**
   - **Answer:** Type inference refers to the automatic detection of variable types by the Python interpreter based on the assigned values.
4. **What is the difference between mutable and immutable data types in Python?**
   - **Answer:** Mutable data types can be modified after creation (e.g., lists), while immutable data types cannot be changed once created (e.g., tuples).
5. **How do you check the type of a variable in Python?**
   - **Answer:** The `type()` function can be used to determine the type of a variable. For example, `type(age)` returns the type of the variable `age`.
6. **Explain the concept of type conversion in Python.**
   - **Answer:** Type conversion involves changing the type of a variable explicitly, using functions like `int()`, `float()`, `str()`, etc.
7. **What is the purpose of NoneType in Python?**
   - **Answer:** `NoneType` represents the absence of a value or a null value in Python.
8. **Differentiate between local and global variables in Python.**
   - **Answer:** Local variables are declared within a function and have limited scope, while global variables are declared outside functions and can be accessed throughout the program.
9. **How can you make a variable global inside a function?**
   - **Answer:** To make a variable global inside a function, use the `global` keyword followed by the variable name, e.g., `global x`.
10. **Explain the concept of type hints in Python.**
    - **Answer:** Type hints are annotations used to indicate the expected type of a variable or the return type of a function. They are a form of static typing introduced to improve code readability and maintainability.

It's worth noting that Python supports type inference, allowing variables to be assigned values of different types during their lifetime. For example, a variable can be assigned an integer value initially and later be assigned a string. This dynamic typing is one of the features that makes Python flexible and easy to use.