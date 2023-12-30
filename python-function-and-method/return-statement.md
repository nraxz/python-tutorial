# Return Statement

In Python, the `return` statement is used to exit a function and return a value back to the caller. When a function is called and the `return` statement is encountered, the function immediately terminates, and the specified value (or `None` if no value is provided) is sent back to the calling code.

### Syntax:

```python
def function_name(parameters):
    # Function body

    # Optional: Return statement
    return expression
```

- **`function_name`:** The name of the function.
- **`parameters`:** Optional parameters that the function may take.
- **`return`:** Keyword indicating the start of the return statement.
- **`expression`:** The value to be returned to the caller.

### Example:

```python
def add_numbers(x, y):
    result = x + y
    return result

# Calling the function and capturing the returned value
sum_result = add_numbers(3, 5)

# Using the returned value
print("Sum:", sum_result)
```

In this example, the `add_numbers` function takes two parameters (`x` and `y`). Inside the function, the sum of `x` and `y` is calculated and assigned to the variable `result`. The `return result` statement sends the value of `result` back to the caller.

### Use Cases of `return` Statement:

1. **Returning a Value:**
   - The primary use of `return` is to provide the result or output of a function back to the calling code.
2. **Exiting Early:**
   - `return` is also used to exit a function prematurely if certain conditions are met.
3. **Returning Multiple Values:**
   - Multiple values can be returned as a tuple or other data structures.
4. **Returning `None`:**
   - If no value is specified after `return`, the function returns `None` by default.

### Example with Multiple Returns:

```python
def divide_numbers(x, y):
    if y == 0:
        return "Cannot divide by zero"
    else:
        quotient = x / y
        remainder = x % y
        return quotient, remainder

# Calling the function and capturing the returned values
result = divide_numbers(10, 3)

# Using the returned values
print("Quotient:", result[0])
print("Remainder:", result[1])
```

In this example, the `divide_numbers` function returns a tuple containing the quotient and remainder of the division. The calling code can capture these values and use them as needed.

Understanding how to use the `return` statement allows you to create functions that provide meaningful results and enhance code modularity.