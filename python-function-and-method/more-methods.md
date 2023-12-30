# More Methods

In addition to the methods available for lists, dictionaries, and strings, Python provides a variety of methods for other built-in data types and objects. Here are some common methods for other types:

### 1. Tuple Methods:

Tuples are immutable, so they have fewer methods compared to lists.

- **`tuple.count(x)`:**

  - Returns the number of occurrences of the specified value in the tuple.

    ```python
    my_tuple = (1, 2, 2, 3, 4)
    count = my_tuple.count(2)  # Result: 2
    ```

- **`tuple.index(x[, start[, end]])`:**

  - Returns the index of the first occurrence of the specified value in the tuple.

    ```
    my_tuple = (1, 2, 3, 2, 4)
    index = my_tuple.index(2)  # Result: 1
    ```

### 2. Set Methods:

Sets are unordered and do not have index-based methods.

- **`set.add(element)`:**

  - Adds an element to the set.

    ```python
    my_set = {1, 2, 3}
    my_set.add(4)  # Result: {1, 2, 3, 4}
    ```

- **`set.remove(element)`:**

  - Removes the specified element from the set. Raises a `KeyError` if the element is not found.

    ```python
    my_set = {1, 2, 3}
    my_set.remove(2)  # Result: {1, 3}
    ```

- **`set.discard(element)`:**

  - Removes the specified element from the set if it is present, without raising an error if the element is not found.

    ```python
    my_set = {1, 2, 3}
    my_set.discard(2)  # Result: {1, 3}
    ```

- **`set.union(other_set[, ...])` and `set.update(other_set[, ...])`:**

  - Returns a new set with elements from the set and others.

  - `update` adds elements from sets (or other iterables) to the set.

    ```python
    set1 = {1, 2, 3}
    set2 = {3, 4, 5}
    union_set = set1.union(set2)  # Result: {1, 2, 3, 4, 5}
    set1.update(set2)  # Result: {1, 2, 3, 4, 5}
    ```

### 3. Numeric Type Methods:

- **`abs(x)`:**

  - Returns the absolute value of a number.

    ```python
    absolute_value = abs(-5)  # Result: 5
    ```

- **`round(number[, ndigits])`:**

  - Rounds a floating-point number to the specified number of decimals.

    ```python
    rounded_number = round(3.14159, 2)  # Result: 3.14
    ```

These are just a few examples, and there are more methods and functions available for other built-in types in Python. Understanding the methods associated with different data types is essential for effective programming and data manipulation.

### Interview Questions

Prepare for interviews with a set of carefully crafted questions and detailed answers for functions and methods in Python.

## Contribution

If you find any issues, errors, or want to contribute improvements, feel free to open an issue or submit a pull request.

Happy coding!