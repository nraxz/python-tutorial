# String methods

String methods in Python are built-in functions that operate on string objects. These methods provide a variety of operations for manipulating and working with strings, allowing you to perform tasks such as formatting, searching, modifying, and extracting information from strings.

Here are some common string methods in Python:

1. **`str.upper()` and `str.lower()`:**

   - Converts all characters in a string to uppercase or lowercase.

   ```
   pythonCopy codemy_string = "Hello, World!"
   upper_case = my_string.upper()
   lower_case = my_string.lower()
   ```

2. **`str.capitalize()` and `str.title()`:**

   - Capitalizes the first character of a string or capitalizes the first character of each word in a string.

   ```
   pythonCopy codemy_string = "hello, world!"
   capitalized = my_string.capitalize()
   title_case = my_string.title()
   ```

3. **`str.strip()`, `str.lstrip()`, and `str.rstrip()`:**

   - Removes leading and trailing whitespaces from a string or from the left or right side only.

   ```
   pythonCopy codemy_string = "   Python   "
   stripped = my_string.strip()
   left_stripped = my_string.lstrip()
   right_stripped = my_string.rstrip()
   ```

4. **`str.replace(old, new[, count])`:**

   - Replaces occurrences of a substring with another substring. The optional `count` parameter limits the number of replacements.

   ```
   pythonCopy codemy_string = "Hello, World!"
   replaced = my_string.replace("Hello", "Hi")
   ```

5. **`str.find(substring[, start[, end]])` and `str.index(substring[, start[, end]])`:**

   - Searches for the first occurrence of a substring and returns its index. The `find` method returns -1 if the substring is not found, while `index` raises a `ValueError`.

   ```
   pythonCopy codemy_string = "Hello, World!"
   position = my_string.find("World")
   ```

6. **`str.count(substring[, start[, end]])`:**

   - Counts the number of occurrences of a substring in a string.

   ```
   pythonCopy codemy_string = "Hello, Hello, World!"
   count = my_string.count("Hello")
   ```

7. **`str.startswith(prefix[, start[, end]])` and `str.endswith(suffix[, start[, end]])`:**

   - Checks if a string starts or ends with a specified prefix or suffix.

   ```
   pythonCopy codemy_string = "Hello, World!"
   starts_with_hello = my_string.startswith("Hello")
   ends_with_world = my_string.endswith("World")
   ```

8. **`str.split(sep=None, maxsplit=-1)`:**

   - Splits a string into a list of substrings based on a specified separator (`sep`). The optional `maxsplit` parameter limits the number of splits.

   ```
   pythonCopy codemy_string = "apple,orange,banana"
   fruits = my_string.split(",")
   ```

9. **`str.join(iterable)`:**

   - Joins elements of an iterable (e.g., a list) into a single string, using the original string as a separator.

   ```
   pythonCopy codefruits = ["apple", "orange", "banana"]
   joined_string = ",".join(fruits)
   ```

These are just a few examples of the many string methods available in Python. String methods make it convenient to perform a wide range of operations on strings without having to write custom functions for each task.