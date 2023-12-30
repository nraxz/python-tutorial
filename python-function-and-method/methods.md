# Methods

In Python, methods are functions that are associated with objects. Unlike standalone functions, which can be called independently, methods are called on objects and operate on the data contained within those objects. Methods are a way to bundle functions with the objects they operate on, providing a way to interact with and manipulate the object's state.

Here are some key points about Python methods:

1. **Object Association:**

   - Methods are closely associated with objects. They are defined within a class and operate on instances of that class.

2. **Accessing Methods:**

   - Methods are accessed using the dot notation, where the object is followed by a dot (`.`) and the method name.

   ```python
   object.method()
   ```

3. **Self Parameter:**

   - The first parameter of a method is conventionally named `self` and refers to the instance of the object on which the method is called.

   ```python
   class MyClass:
       def my_method(self):
           # Code inside the method
   ```

4. **Built-in Methods:**

   - Python provides several built-in methods for common data types and objects. For example, string methods, list methods, dictionary methods, etc.

   ```python
   my_string = "Hello, World!"
   print(my_string.upper())  # Calling the upper() method on a string
   ```

5. **Custom Methods:**

   - Programmers can define their own methods within classes to encapsulate functionality related to the class.

   ```python
   class Circle:
       def calculate_area(self, radius):
           return 3.14 * radius**2
   ```

6. **Mutability:**

   - Methods can modify the internal state of an object. Depending on whether an object is mutable or immutable, methods can either modify the object in place (for mutable objects) or return a new object with the changes applied (for immutable objects).

7. **Function vs. Method:**

   - The terms "function" and "method" are often used interchangeably, but in the context of object-oriented programming, methods are functions associated with objects.

Here's an example illustrating a method:

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
        self.fuel = 0

    def add_fuel(self, amount):
        self.fuel += amount
        print(f"{amount} liters of fuel added to the {self.brand} {self.model}.")

# Creating an instance of the Car class
my_car = Car("Toyota", "Camry")

# Calling the add_fuel method on the my_car object
my_car.add_fuel(20)
```

In this example, `add_fuel` is a method of the `Car` class, and it is called on an instance of the class (`my_car`). The method modifies the `fuel` attribute of the `my_car` object.

Understanding methods is fundamental to object-oriented programming in Python, as they enable the encapsulation of behavior within objects, leading to more modular and maintainable code.