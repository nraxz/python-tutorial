## Encapsulation

Encapsulation is a key concept in Object-Oriented Programming (OOP) that includes grouping data (attributes) and methods (functions) that operate on the data into a single unit called a class. It acts as a safeguard, prohibiting direct access to specific parts of an object and ensuring regulated interactions.

**Key Advantages of Encapsulation:**

- **Data security:** Prevents the unintentional or unauthorised modification of sensitive data.
- **Modular Code:** Classes become self-contained units that can be reused and modified independently in modular code.
- **Reduced Complexity:** Hides implementation details, making code more understandable and maintainable.
- **Increased Flexibility:** Internal data structures and procedures can be changed without affecting external code.

Encapsulation in Action: The User Class Example

Consider a `User` class where we encapsulate user-related information:

```python
class User:
    def __init__(self, user_id, username, email, password):
        self._user_id = user_id
        self._username = username
        self._email = email
        self._password = password  # Consider hashing for security
        self._is_authenticated = False

    def authenticate(self, entered_password):
        if entered_password == self._password:
            self._is_authenticated = True
            print("Authentication successful.")
            return True  # Explicitly return success status
        else:
            print("Authentication failed.")
            return False  # Explicitly return failure status

    def get_username(self):
        return self._username

    def get_email(self):
        return self._email

    def set_email(self, new_email):
        self._email = new_email
        print("Email updated successfully.")

    def get_id(self):
        return self._user_id

    def is_authenticated(self):
        return self._is_authenticated

    def display_info(self):
        print(f"User ID: {self.get_id()}, Username: {self.get_username()}, Email: {self.get_email()}")
```



In the example:

- The attributes (`_username`, `_email`, `_password`, `_is_authenticated`) are marked with a single leading underscore, indicating that they are intended to be accessed within the class or by subclasses.
- External access to these attributes is controlled through methods like `authenticate`, `get_username`, and `update_email`, providing a layer of abstraction.

**Using Encapsulation:**

```python
# Create a user
my_user = User("JohnDoe", "john.doe@email.com", "secret_password")

# Attempt to access attributes directly
print(my_user._username)  # Avoid direct access

# Authenticate and access information through methods
my_user.authenticate("wrong_password")  # Output: Authentication failed.
my_user.authenticate("secret_password")  # Output: Authentication successful.
print(my_user.get_username())  # Output: JohnDoe

# Update email through a method
my_user.update_email("john.doe.new@email.com")  # Output: Email updated successfully.
```



**Easiest way to understand Encapsulation:**

**TV Remote:** Imagine encapsulation in Object-Oriented Programming (OOP) like a TV remote. The inner workings of the remote (its circuitry, buttons, etc.) are encapsulated inside a protective case. Users can interact with the remote through a simplified interface (pressing buttons), and they don't need to understand or tamper with the internal complexities. Similarly, in OOP, encapsulation involves bundling data and methods into a class, shielding the inner details and offering a clean, user-friendly way to interact with objects.

**Gift Box:** Consider encapsulation in OOP as a gift box. The box contains a carefully arranged gift, and the wrapping serves as a protective layer. Recipients can appreciate and interact with the gift without knowing its intricate details. Similarly, in OOP, encapsulation involves packaging data and methods within a class, shielding the internal complexities. Users interact with the class through a well-defined interface, promoting simplicity and effective use.

**Magic Show:** Think of encapsulation in OOP like a magic show. The magician performs intricate tricks using various props, but the audience only sees the final, mesmerizing act. The details of how each trick works are hidden behind the scenes. In OOP, encapsulation involves hiding the inner workings of a class, exposing only what's necessary for users to interact with, creating a kind of "magic" where complexity is managed behind a simplified interface.

**Relation to `SOLID` principles**

> The Single Responsibility (**S**) Principle specifically emphasizes that a class should have only one reason to change. 

This principle encourages encapsulating a class's responsibilities and functionalities, ensuring that it has a single, well-defined purpose. By adhering to the Single Responsibility Principle, you reinforce the idea of encapsulation in your code, making classes more focused and maintainable.