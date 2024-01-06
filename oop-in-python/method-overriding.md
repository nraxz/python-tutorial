## Method Overriding

- **Definition:** Method overriding allows a subclass to redefine a method inherited from its superclass, providing a specialized implementation tailored to its specific needs.
- **Key Concepts:**
  - **Inheritance:** Establishes an "is-a" relationship between classes, enabling subclasses to inherit attributes and methods from their parent class.
  - **Polymorphism:** The ability to treat objects of different classes in a uniform way based on shared interfaces, enabling dynamic method calls based on object type.

**Example with User, AdminUser, and ManagerUser Classes:**

```python
class User:
    def __init__(self, user_id, username, email):
        self.user_id = user_id
        self.username = username
        self.email = email

    def display_info(self):
        print(f"User ID: {self.user_id}, Username: {self.username}, Email: {self.email}")

class AdminUser(User):
    def __init__(self, user_id, username, email, role):
        super().__init__(user_id, username, email)
        self.role = role

    # Overriding the display_info method for AdminUser
    def display_info(self):
        print(f"Admin User - User ID: {self.user_id}, Username: {self.username}, Email: {self.email}, Role: {self.role}")

class ManagerUser(User):
    def __init__(self, user_id, username, email, team):
        super().__init__(user_id, username, email)
        self.team = team

    # Overriding the display_info method for ManagerUser
    def display_info(self):
        print(f"Manager User - User ID: {self.user_id}, Username: {self.username}, Email: {self.email}, Team: {self.team}")

```



**Explanation:**

- **Inheritance:** `AdminUser` and `ManagerUser` inherit from `User`, gaining its attributes and methods.
- **Method Overriding:** Both subclasses override the `display_info()` method to provide their own versions, tailoring the output to their specific information.
- **Polymorphism in Action:** When you call `display_info()` on an object of either subclass, the appropriate overridden version is executed, demonstrating polymorphism.

**Benefits of Method Overriding:**

- **Customization:** Tailor functionality to specific subclass needs without modifying the superclass.
- **Extensibility:** Easily add new features to subclasses without affecting the core functionality.
- **Code Reusability:** Share common code in the superclass while allowing for specialized behavior in subclasses.
- **Encapsulation:** Hide implementation details within subclasses, promoting modularity and maintainability.

**Relation to `SOLID` principles**

The `SOLID` principle related to method overriding is the "**Open/Closed** Principle" (**O** in `SOLID`). 

> The **Open/Closed** Principle states that a class should be open for extension but closed for modification. 

In the context of method overriding, this principle encourages designing classes and methods in a way that allows for extension (new functionality) without modifying the existing code.

When you override a method in a subclass, you are extending the behavior without modifying the original method in the superclass. This aligns with the Open/Closed Principle, as it enables you to introduce new functionalities by creating new subclasses or overriding methods without altering the existing codebase. This promotes code stability, scalability, and maintainability in the face of changing requirements.