## Classes and Object in Python

In Python, a **class** is a blueprint defining attributes and methods, while an **object** is an instance of that class, embodying its specific characteristics. Classes facilitate code organization, encapsulation, and reusability, enabling the creation of multiple objects with shared behaviors.

While it may not apply universally, I often find it straightforward to illustrate: In the context of Object-Oriented Programming (OOP), one can represent MySQL tables to classes and rows to objects. For instance, envisioning a `students_table` as a `Student` class, the record corresponding to John Doe becomes an object instantiated from the `Student` class.

### **Classes:**

- **Definition:** A class is a blueprint or a template for creating objects. It defines attributes (variables) and methods (functions) that characterize the objects instantiated from the class.

  - **Creation:**

    ```python
    class User:
        def __init__(self, user_id, username, email):
            self.user_id = user_id
            self.username = username
            self.email = email
    
        def display_info(self):
            print(f"User ID: {self.user_id}, Username: {self.username}, Email: {self.email}")
    ```

    **`class User:`** defines a class called `User` that serves as a blueprint for creating objects representing users in a system.

    `__init__(self, user_id, username, email):`

    

    - **Constructor:**  initializes a new User object with the given information:
      - `self.user_id`: Stores the unique ID assigned to the user.
      - `self.username`: Stores the user's chosen username.
      - `self.email`: Stores the user's email address.
    - **Attributes:** Variables like `user_id`, `username`, and `email` define details of objects created from `Student` Class
    - **Method:** `display_info(self):` Prints the user's information to the console in a formatted way:
      - It uses an f-string to interpolate the values of `user_id`, `username`, and `email` into the output string.
      - The output would look like this: `User ID: 123, Username: johndoe, Email: johndoe@example.com`
    - **Key Points:**
      - The `User` class encapsulates the core information and a basic method for displaying that information related to a user.
      - It provides a foundation for managing user data and actions within a system.
      - You can create instances of this class to represent different users, each with their own unique attributes.



### Objects:

- **Definition**: An object is an instance of a class, representing a specific entity with its unique attributes and behaviors.

- **Instantiation:**

  ```python
  user1 = User(123, "johndoe", "johndoe@example.com")
  ```

- **Attributes:** Each object, like `uset1`, has its own set of attributes (e.g., `name` and `email`).

- **Methods:** Objects can perform actions defined by the methods (e.g., `display_info(self)`).

- **Example:**

  ```python
  # Create a User object
  user1 = User(123, "johndoe", "johndoe@example.com")
  
  # Call the display_info method to print the user's information
  user1.display_info()  # Output: User ID: 123, Username: johndoe, Email: johndoe@example.com
  ```



📝 **Key Concepts:**

- **Self:** The `self` parameter refers to the instance of the class. It is a convention in Python to use `self` as the first parameter of instance methods.
- ***\*init\** Method:** The `__init__` method is a special method used for initializing object attributes when an object is created.

⚡ **Why Classes and Objects?**

- **Code Organization:** Classes provide a way to structure code, making it more organized and modular.
- **Code Reusability:** Objects enable the reuse of code templates, fostering efficiency and reducing redundancy.
- **Abstraction:** OOP promotes abstraction, allowing developers to focus on essential details while hiding complexity.

