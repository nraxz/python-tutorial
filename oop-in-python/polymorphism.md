**Polymorphism in Python**

Polymorphism, a fundamental concept in Object-Oriented Programming (OOP), allows objects of various classes to be considered as objects of a common base class. This promotes flexibility and enables programming to change dynamically dependent on the type of object with which it interacts. Let's look at polymorphism in the context of an Audition Manager by using the **User**, **AdminUser**, and **ManagerUser** classes:

**Base Class: User**

```python
class AdminUser(User):
    def __init__(self, user_id, username, email, password, role):
        super().__init__(user_id, username, email, password)
        self._role = role

    def promote_to_admin(self):
        print(f"User {self._username} promoted to admin.")

    # Overriding the display_info method for AdminUser
    def display_info(self):
        print(f"Admin User - User ID: {self._user_id}, Username: {self._username}, Email: {self._email}, Role: {self._role}")

    # Create a regular user
    regular_user = User(1, "JohnDoe", "john.doe@email.com", "secret_password")

    # Create an admin user
    admin_user = AdminUser(2, "AdminJohn", "admin.john@email.com", "admin_password", "Administrator")

    # Display user information
    regular_user.display_info()  
    # Output: User ID: 1, Username: JohnDoe, Email: john.doe@email.com
    admin_user.display_info()    
    # Output: Admin User - User ID: 2, Username: AdminJohn, Email: admin.john@email.com, Role: Administrator

    # Promote the admin user
    admin_user.promote_to_admin()  
    # Output: User AdminJohn promoted to admin.
```



**Derived Class 1: AdminUser**

```python
class AdminUser(User):
    def __init__(self, user_id, username, email, password, role):
        super().__init__(user_id, username, email, password)
        self._role = role

    def promote_to_admin(self):
        print(f"User {self._username} promoted to admin.")

    # Overriding the display_info method for AdminUser
    def display_info(self):
        print(f"Admin User - User ID: {self._user_id}, Username: {self._username}, Email: {self._email}, Role: {self._role}")
```

**Derived Class 2: ManagerUser**

```python
class ManagerUser(User):
    def __init__(self, user_id, username, email, password, role):
        super().__init__(user_id, username, email, password)
        self._auditions = []  # List to store auditions created by this manager

    def promote_to_manager(self):
        print(f"User {self._username} promoted to manager.")
        
    def create_audition(self, audition_name, description, deadline):
        new_audition = Audition(audition_name, description, deadline, manager=self)
        self._auditions.append(new_audition)
        print(f"Audition '{audition_name}' created successfully.")
        return new_audition

    def get_auditions(self):
        return self._auditions

    # Additional methods for audition management:
    def get_applications(self, audition):
        # Retrieve applications for the specified audition
        return audition.get_applications()  # Assuming Audition class has a method to access applications

    def review_application(self, application):
        # Implement logic for reviewing an application
        pass

    def approve_application(self, application):
        # Implement logic for approving an application
        pass

    def reject_application(self, application):
        # Implement logic for rejecting an application
        pass

    def display_info(self):
        print(f"Manager User - User ID: {self._user_id}, Username: {self._username}, Email: {self._email}")
```

**Polymorphism in Action: Audition Manager Scenario**

Now, let's see how polymorphism allows us to interact with different user types seamlessly:

```python
# Create instances of different user types
regular_user = User(1, "JohnDoe", "john.doe@email.com", "secret_password")
admin_user = AdminUser(2, "AdminJohn", "admin.john@email.com", "admin_password", "Administrator")
manager_user = ManagerUser(3, "ManagerJane", "manager.jane@email.com", "manager_password", "Casting Department")

# Display user information using polymorphism
users = [regular_user, admin_user, manager_user]

for user in users:
    user.display_info()
```



**Key Concepts:**

- **Polymorphism:** Treating objects of different classes through a common interface (e.g., `display_info` method).
- **Method Overriding:** Providing a specific implementation of a method in a subclass that is already defined in its superclass.
- **Base Class (`User`):** Common characteristics and methods shared among different user types.
- **Derived Classes (`AdminUser`, `ManagerUser`):** Specialized classes that inherit and extend the functionality of the base class.



The `SOLID` principle related to **polymorphism** is the "**Liskov Substitution** Principle" (L in `SOLID`). 

> The **Liskov Substitution** Principle states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program. This principle directly supports the idea of polymorphism.

**Polymorphism** allows objects of different types to be treated as objects of a common type, and the **Liskov Substitution** Principle ensures that this substitution can happen seamlessly. It encourages the use of a common interface or base class so that different implementations (subclasses) can be used interchangeably, promoting flexibility and extensibility in the codebase.