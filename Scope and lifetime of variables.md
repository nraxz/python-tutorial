# Scope and lifetime of variables

In Python, the scope and lifetime of a variable define where the variable can be accessed and how long it exists during the execution of a program.

### Scope of a Variable:

**Scope refers to the region of the code where a variable is visible and can be accessed.**

1. **Global Scope:**

   - Variables declared outside of any function or block have a global scope.
   - They can be accessed from any part of the code, including within functions.

   ```python
   global_variable = 10
   
   def my_function():
       print(global_variable)
   
   my_function()  # Output: 10
   ```

2. **Local Scope:**

   - Variables declared inside a function have a local scope.
   - They are only accessible within that function.

   ```python
   def my_function():
       local_variable = 5
       print(local_variable)
   
   my_function()  # Output: 5
   
   # Attempting to access local_variable outside the function will result in an error
   ```

### Lifetime of a Variable:

**Lifetime refers to the duration for which a variable exists in the memory during program execution.**

1. **Global Variable Lifetime:**

   - Global variables exist throughout the entire program's execution.
   - They are created when the program starts and persist until the program terminates.

   ```python
   global_variable = 10
   
   def my_function():
       print(global_variable)
   
   my_function()  # Output: 10
   
   # The global_variable continues to exist even after the function call
   ```

2. **Local Variable Lifetime:**

   - Local variables are created when a function is called and destroyed when the function exits.
   - They exist only during the execution of the function.

   ```python
   def my_function():
       local_variable = 5
       print(local_variable)
   
   my_function()  # Output: 5
   
   # After the function call, local_variable no longer exists
   ```

### Global and Local Variables in the Same Name:

- If a local variable has the same name as a global variable, the local variable takes precedence within its scope.

  ```python
  variable = 100  # Global variable
  
  def my_function():
      variable = 50  # Local variable with the same name
      print(variable)
  
  my_function()  # Output: 50
  
  # Accessing variable outside the function will refer to the global variable
  ```

Understanding the scope and lifetime of variables is crucial for writing maintainable and bug-free code. It helps prevent unintended variable name clashes and ensures that variables are used in the appropriate context.