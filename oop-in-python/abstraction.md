## Abstraction

Abstraction is a fundamental concept in Object-Oriented Programming (OOP), which means simplifying complex systems by modelling classes based on essential features and behaviors while obscuring unnecessary details. It provides a high-level overview of an entity, emphasising what it does rather than how it does it. Let's explore abstraction using the User, AdminUser, and ManagerUser classes:

**Abstract Base Class: User**

```python
from abc import ABC, abstractmethod

class AbstractUser(ABC):
    def __init__(self, user_id, username, email, password):
        self._user_id = user_id
        self._username = username
        self._email = email
        self._password = password
        self._is_authenticated = False

    @abstractmethod
    def authenticate(self, entered_password):
        pass  # Abstract method, concrete implementation in subclasses

    @abstractmethod
    def get_username(self):
        pass

    @abstractmethod
    def get_email(self):
        pass

    @abstractmethod
    def set_email(self, new_email):
        pass

    @abstractmethod
    def get_id(self):
        pass

    @abstractmethod
    def is_authenticated(self):
        pass

    def display_info(self):
        print(f"User ID: {self._user_id}, Username: {self._username}, Email: {self._email}")
```



> It's not strictly necessary to create an abstract base class for subclasses in Python, but doing so can have several advantages:

 Python is a dynamically typed language, and it doesn't enforce strict adherence to abstract classes. Subclasses can choose not to inherit from an abstract base class or may not provide an implementation for all abstract methods.

In the example we discussed earlier, using an abstract base class (`User`) with an abstract method (`display_info`) was a choice made to emphasize the importance of providing a consistent interface for subclasses. Depending on your specific use case and design preferences, you may choose to use or omit abstract base classes.

**Abstract Base Class: AdminUser**

```python
from abc import ABC, abstractmethod

class AbstractAdmin(ABC):
    def __init__(self, user_id, username, email, password, role):
        super().__init__(user_id, username, email, password)  # Call the constructor of the superclass (AbstractUser)
        self._role = role

    @abstractmethod
    def promote_to_admin(self, user):
        pass  # Concrete implementation in subclasses

   
    # Overriding the display_info method for AdminUser
    def display_info(self):
        print(f"Admin User - User ID: {self._user_id}, Username: {self._username}, Email: {self._email}, Role: {self._role}")
```

- **Key Points:**
  - **Abstract Class:** Cannot be instantiated directly, serving as a foundation for user-related classes.
  - **Abstract Methods:** Defines core user actions that must be implemented in subclasses.
  - **Common Attributes:** Encapsulates shared attributes like `user_id`, `username`, `email`, `password`, and `is_authenticated`.
  - **Enforces Consistency:** Ensures all user types adhere to the same basic structure and functionality.

**Abstract Base Class: ManagerUser**

```python
from abc import ABC, abstractmethod

class AbstractManager(ABC):
    def __init__(self, user_id, username, email, password):
        super().__init__()  # Call the constructor of the superclass (User)
        self._user_id = user_id
        self._username = username
        self._email = email
        self._password = password
        self._auditions = []  # List to store auditions

    @abstractmethod
    def create_audition(self, audition_name, description, deadline):
        pass  # Abstract method, implementation will be provided in subclasses

    @abstractmethod
    def get_auditions(self):
        pass  # Abstract method, implementation will be provided in subclasses

    # Additional abstract methods for audition management:
    @abstractmethod
    def get_applications(self, audition):
        pass

    @abstractmethod
    def review_application(self, application):
        pass

    @abstractmethod
    def approve_application(self, application):
        pass

    @abstractmethod
    def reject_application(self, application):
        pass

    def display_info(self):
        print(f"Manager User - User ID: {self._user_id}, Username: {self._username}, Email: {self._email}")
```

Now, the `User` class is truly abstract with the addition of the `@abstractmethod` decorator for the `display_info` method. Subclasses (`AdminUser` and `ManagerUser`) must implement this method, adhering to the principles of abstraction. This showcases a clearer example of abstraction in action.

- **Key Points:**
  - **Abstract Class:** Cannot be instantiated directly.
  - **Common Attributes:** Inherits `user_id`, `username`, `email`, `password` from `AbstractUser`, adds `role`.
  - Abstract Methods:Defines core actions expected of admin users:
    - `promote_to_admin(self, user)`: Promotes another user to admin.
    - `manage_users(self)`: Handles user management tasks.
    - `view_logs(self)`: Accesses system logs for monitoring and troubleshooting.
  - **Overridden `display_info()`:** Prints admin-specific information.



**Relation to `SOLID` principles**

The `SOLID` principle related to **abstraction** is the "Interface Segregation Principle" (I in `SOLID`). 

> The **Interface Segregation** Principle emphasizes that a class should not be forced to implement interfaces it does not use. This principle is closely tied to abstraction because it encourages the creation of specific, client-focused interfaces rather than large, all-encompassing ones.

**Abstraction** involves simplifying complex systems by modeling classes and interfaces based on the essential features they provide. The **Interface Segregation** Principle supports this by advocating for small, focused interfaces that are tailored to the needs of the clients using them. This way, abstraction is maintained, and classes only depend on the interfaces that are relevant to their specific requirements.