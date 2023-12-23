# Primary Scope of variables (Local vs Global)

In Python, variables can have different scopes, and the two primary scopes are local and global. The scope of a variable determines where in the code it can be accessed or modified. Here's an explanation of local and global variables in Python:

1. **Local Variables:**

   - A variable declared inside a function is known as a local variable.
   - It is only accessible within the function where it is defined.
   - Once the function execution is complete, the local variable is destroyed, and its value is no longer accessible.

   ```python
   def my_function():
       local_variable = 10
       print(local_variable)
   
   my_function()  # Output: 10
   
   # Attempting to access the local variable outside the function would result in an error
   # print(local_variable)  # This would raise an error
   
   ```

   

2. **Global Variables:**

   - A variable declared outside of any function or block is considered a global variable.

   - Global variables are accessible throughout the entire program, including inside functions.

   - However, if a function tries to modify the value of a global variable, it needs to use the `global` keyword.

   ```python
   global_variable = 20
   
   def my_function():
       # Accessing the global variable
       print(global_variable)
   
   my_function()  # Output: 20
   
   def modify_global():
       global global_variable
       global_variable = 30
   
   modify_global()
   print(global_variable)  # Output: 30
   
   ```

   

3. **Scope Hierarchy:**

   - When both local and global variables have the same name, the local variable takes precedence within its scope.

   - If a variable is not found in the local scope, Python looks for it in the enclosing (non-local) scopes, including the global scope.

   ```python
   x = 50  # Global variable
   
   def my_function():
       x = 10  # Local variable with the same name as the global variable
       print(x)
   
   my_function()  # Output: 10
   print(x)       # Output: 50 (global variable)
   
   ```



In the example above, the `print(x)` statement inside `my_function` refers to the local variable `x`, while the `print(x)` statement outside the 	function refers to the global variable `x`.

Understanding the scope of variables is crucial for writing maintainable and bug-free code. It helps prevent unintended side effects and ensures that variables are used appropriately within their intended contexts.

