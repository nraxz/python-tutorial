**Inheritance in Python: Building on the User Class Example**

Inheritance is a powerful concept in Object-Oriented Programming (OOP) that allows a new class (subclass or child class) to inherit attributes and methods from an existing class (superclass or parent class). This promotes code reuse and the creation of a hierarchical structure. Let's explore inheritance using the `User` class example:

**Base Class: User**

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

**Inheritance in Action: AdminUser as a Subclass**

Let's create a new class `AdminUser` that inherits from the `User` class. The `AdminUser` class will have additional attributes and methods specific to administrative users.



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



**Using Inheritance: Creating and Using AdminUser Instances**

Now, let's create instances of both the `User` and `AdminUser` classes and see how inheritance works:

```python
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



 **Key Concepts:**

- **Base Class (`User`):** The class from which attributes and methods are inherited.
- **Subclass (`AdminUser`):** The class that inherits from the base class and may have additional attributes or methods.
- **`super()` Function:** Used to call a method from the superclass within the subclass.
- **Method Overriding:** The ability of a subclass to provide a specific implementation of a method that is already defined in its superclass.

**Easiest way to understand Inheritance:**

**Person and Student:** Consider the concept of inheritance in Object-Oriented Programming (OOP) like a family tree. A parent class could be like a "**Person**" class, and it has certain attributes and behaviors common to everyone, such as a name and the ability to speak.

Now, imagine you have a child class called "**Student**" that inherits from the "**Person**" class. The "**Student**" class automatically gets all the attributes and behaviors of the "**Person**" class but can also have additional features specific to being a student, like a "`study`" method.

In this way, inheritance allows you to create a hierarchy where the "**Student**" class is a specialized version of the more general "**Person**" class, inheriting its characteristics while adding its own unique features.

**Vehicle (Car / Bicycle):** Imagine a base class called "**Vehicle**" that has common attributes like "`speed`" and a method like "`move`." Now, consider two subclasses: "**Car**" and "**Bicycle**."

The "**Car**" class inherits from "**Vehicle**" and adds specific features like "`number of doors`" and a unique method, "`honk`." Similarly, the "**Bicycle**" class also inherits from "Vehicle" but includes its unique attributes like "`number of pedals`" and a special method, "`ringBell`."

In this scenario, "**Car**" and "**Bicycle**" inherit the common features from the "Vehicle" class but introduce their own distinctive characteristics. This illustrates how inheritance allows you to create a hierarchy of classes, promoting code reuse and organization in an Object-Oriented Programming (OOP) setting.

**Relation to `SOLID` principles**

The SOLID principle related to Inheritance is the "**Liskov Substitution Principle**" (**L in `SOLID`**). 

The **Liskov Substitution Principle** states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program. In other words, if a class is a subclass of another class, it should be able to be used interchangeably with its parent class without disrupting the behavior of the program.

This principle promotes the idea that inheritance should not introduce unexpected behaviors or violate the contract established by the superclass. It encourages creating a hierarchy where subclasses can extend or specialize the behavior of the superclass without causing issues when instances of the subclass are used in the same context as instances of the superclass.