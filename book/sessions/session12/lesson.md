# Session 12: Inheritance and Advanced Class Concepts - Building on What You Know

## Learning Objectives

By the end of this session, you will be able to:
- Understand inheritance and why it's powerful
- Create parent and child classes
- Override methods in child classes
- Understand polymorphism and method overriding
- Apply inheritance to solve complex real-world problems

## What is Inheritance?

**Inheritance** is like **a family tree** - children inherit characteristics from their parents, but they can also have their own unique features and abilities.

### Real-World Analogies

Think of inheritance like **manufacturing**:
- **Vehicle Family Tree**: Vehicle → Car → Sports Car (each level adds more specific features)
- **Animal Kingdom**: Animal → Mammal → Dog → Golden Retriever (each level gets more specialized)
- **Company Structure**: Employee → Manager → CEO (each level has more responsibilities)
- **Library System**: Item → Book → Fiction Book → Mystery Novel (each level is more specific)

### Why Use Inheritance?

Inheritance is like **genetic inheritance** in real life:
1. **Code Reuse** - Like inheriting your parents' genes, you don't have to rewrite everything
2. **Organization** - Like organizing a family tree, it creates logical relationships
3. **Extensibility** - Like children developing their own talents, you can add new features
4. **Maintainability** - Like family traits, changes in parent classes affect all children

### When to Use Inheritance

Use inheritance when you have:
- **"Is-A" relationships** (a Car IS-A Vehicle, a Dog IS-A Animal)
- **Shared characteristics** (all vehicles have wheels, all animals can move)
- **Specialized versions** (Sports Car is a specialized Car)
- **Common behavior** (all employees can work, but managers can also manage)

### Why Inheritance Makes Code Better

Think of inheritance like **a library system**:
- **Without inheritance**: You'd have to rewrite the same code for every book type
- **With inheritance**: All books share basic properties (title, author), but fiction books add plot, mystery books add clues, etc.
- **Result**: Less code, better organization, easier to add new book types

## Basic Inheritance Syntax

```python
class ParentClass:
    def __init__(self, attribute1, attribute2):
        self.attribute1 = attribute1
        self.attribute2 = attribute2
    
    def parent_method(self):
        print("This is a parent method")

class ChildClass(ParentClass):
    def __init__(self, attribute1, attribute2, attribute3):
        super().__init__(attribute1, attribute2)  # Call parent's __init__
        self.attribute3 = attribute3
    
    def child_method(self):
        print("This is a child method")
```

## Creating Your First Inheritance Hierarchy

### Example: Vehicle Inheritance

Let's start with a simple vehicle hierarchy:

```python
class Vehicle:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
        self.mileage = 0
    
    def start(self):
        print(f"The {self.year} {self.make} {self.model} is starting...")
    
    def stop(self):
        print(f"The {self.year} {self.make} {self.model} is stopping...")
    
    def drive(self, miles):
        self.mileage += miles
        print(f"Driving {miles} miles. Total mileage: {self.mileage}")
    
    def get_info(self):
        return f"{self.year} {self.make} {self.model} - {self.mileage} miles"

class Car(Vehicle):
    def __init__(self, make, model, year, doors):
        super().__init__(make, model, year)  # Call parent's __init__
        self.doors = doors
        self.fuel_type = "gasoline"
    
    def honk(self):
        print(f"The {self.model} goes 'Beep Beep!'")
    
    def get_info(self):
        # Override parent method
        base_info = super().get_info()
        return f"{base_info} - {self.doors} doors, {self.fuel_type}"

class ElectricCar(Car):
    def __init__(self, make, model, year, doors, battery_capacity):
        super().__init__(make, model, year, doors)
        self.fuel_type = "electric"
        self.battery_capacity = battery_capacity
        self.charge_level = 100
    
    def charge(self, percentage):
        self.charge_level = min(100, self.charge_level + percentage)
        print(f"Charging... Battery level: {self.charge_level}%")
    
    def get_info(self):
        # Override parent method
        base_info = super().get_info()
        return f"{base_info} - {self.battery_capacity}kWh battery, {self.charge_level}% charged"

# Using the inheritance hierarchy
vehicle = Vehicle("Generic", "Vehicle", 2020)
car = Car("Toyota", "Camry", 2021, 4)
electric_car = ElectricCar("Tesla", "Model 3", 2022, 4, 75)

# All objects can use parent methods
vehicle.start()
car.start()
electric_car.start()

# Each object has its own specialized methods
car.honk()
electric_car.charge(20)

# Method overriding in action
print(vehicle.get_info())
print(car.get_info())
print(electric_car.get_info())
```

## Understanding Method Overriding

Method overriding is like **actors playing the same role differently** - each actor brings their own interpretation to the same character.

### Real-World Analogy: Musical Instruments

Think of a music class hierarchy:
- **Parent class**: All instruments can "play music"
- **Child classes**: Piano plays differently than Guitar, which plays differently than Drums
- **Same method name**: `play_music()`
- **Different behavior**: Each instrument makes different sounds

### Example: Animal Hierarchy

```python
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species
    
    def make_sound(self):
        print(f"{self.name} makes a generic animal sound")
    
    def move(self):
        print(f"{self.name} moves around")
    
    def eat(self):
        print(f"{self.name} eats food")

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name, "Canine")
        self.breed = breed
    
    def make_sound(self):
        # Override parent method - like a dog actor playing the "make sound" role
        print(f"{self.name} barks: Woof! Woof!")
    
    def fetch(self):
        print(f"{self.name} fetches the ball")

class Cat(Animal):
    def __init__(self, name, breed):
        super().__init__(name, "Feline")
        self.breed = breed
    
    def make_sound(self):
        # Override parent method - like a cat actor playing the "make sound" role
        print(f"{self.name} meows: Meow! Meow!")
    
    def climb(self):
        print(f"{self.name} climbs up the tree")

# Using the animal hierarchy
animals = [
    Animal("Generic", "Unknown"),
    Dog("Buddy", "Golden Retriever"),
    Cat("Whiskers", "Persian")
]

# Polymorphism in action - same method, different behavior
for animal in animals:
    animal.make_sound()
    animal.move()
    print()  # Empty line for readability
```

### When to Override Methods

Override methods when:
- **Child classes need different behavior** (dogs bark, cats meow)
- **You want to customize inherited functionality** (different animals move differently)
- **You need specialized implementations** (managers work differently than regular employees)

## The `super()` Function

The `super()` function is like **calling your parents for advice** - it lets you use what your parent class already knows while adding your own special touches.

### Real-World Analogy: Building a House

Think of building a house:
- **Parent class**: Knows how to build the foundation and basic structure
- **Child class**: Wants to add a second floor and special features
- **`super()`**: Like calling the parent contractor to do the foundation work first, then adding your own customizations

### Understanding `super()`

```python
class Parent:
    def __init__(self, name):
        self.name = name
        print("Parent __init__ called")
    
    def method(self):
        print("Parent method")

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)  # Call parent's __init__ - like getting the foundation
        self.age = age
        print("Child __init__ called")
    
    def method(self):
        super().method()  # Call parent's method - like using parent's knowledge
        print("Child method")

# Creating a child object
child = Child("Alice", 25)
child.method()
```

### When to Use `super()`

Use `super()` when:
- **Setting up child objects** - Call parent's `__init__` to get the basic setup
- **Extending parent functionality** - Use parent's method and add your own features
- **Avoiding code duplication** - Don't rewrite what the parent already does
- **Maintaining inheritance chain** - Keep the family relationship working properly

### Real-World Example: Employee Hierarchy

```python
class Employee:
    def __init__(self, name, employee_id, salary):
        self.name = name
        self.employee_id = employee_id
        self.salary = salary
        self.department = "General"
    
    def get_salary(self):
        return self.salary
    
    def work(self):
        print(f"{self.name} is working on general tasks")
    
    def get_info(self):
        return f"Employee: {self.name} (ID: {self.employee_id}) - ${self.salary}"

class Manager(Employee):
    def __init__(self, name, employee_id, salary, team_size):
        super().__init__(name, employee_id, salary)
        self.team_size = team_size
        self.department = "Management"
        self.bonus = 0
    
    def work(self):
        # Override parent method
        print(f"{self.name} is managing a team of {self.team_size} people")
    
    def give_bonus(self, amount):
        self.bonus += amount
        print(f"{self.name} received a ${amount} bonus")
    
    def get_salary(self):
        # Override parent method
        return self.salary + self.bonus
    
    def get_info(self):
        # Override parent method
        base_info = super().get_info()
        return f"{base_info} - Manager of {self.team_size} people"

class Developer(Employee):
    def __init__(self, name, employee_id, salary, programming_language):
        super().__init__(name, employee_id, salary)
        self.programming_language = programming_language
        self.department = "Engineering"
        self.projects_completed = 0
    
    def work(self):
        # Override parent method
        print(f"{self.name} is coding in {self.programming_language}")
    
    def complete_project(self):
        self.projects_completed += 1
        print(f"{self.name} completed a project! Total: {self.projects_completed}")
    
    def get_info(self):
        # Override parent method
        base_info = super().get_info()
        return f"{base_info} - {self.programming_language} Developer"

# Using the employee hierarchy
employees = [
    Employee("John", "E001", 50000),
    Manager("Alice", "E002", 75000, 5),
    Developer("Bob", "E003", 60000, "Python")
]

# Polymorphism - same method, different behavior
for employee in employees:
    employee.work()
    print(f"Salary: ${employee.get_salary()}")
    print(employee.get_info())
    print()
```

## Polymorphism in Action

Polymorphism means "many forms" - like **the same actor playing different roles** - the same method can behave differently depending on the object type.

### Real-World Analogy: Transportation

Think of different ways to get to work:
- **Same action**: "Go to work"
- **Different methods**: Drive a car, take a bus, ride a bike, walk
- **Same goal**: Get to work
- **Different implementations**: Each transportation method works differently

### Example: Shape Hierarchy

```python
class Shape:
    def __init__(self, name):
        self.name = name
    
    def area(self):
        # This will be overridden by child classes
        return 0
    
    def perimeter(self):
        # This will be overridden by child classes
        return 0
    
    def describe(self):
        return f"{self.name} - Area: {self.area():.2f}, Perimeter: {self.perimeter():.2f}"

class Rectangle(Shape):
    def __init__(self, width, height):
        super().__init__("Rectangle")
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)

class Circle(Shape):
    def __init__(self, radius):
        super().__init__("Circle")
        self.radius = radius
    
    def area(self):
        import math
        return math.pi * self.radius ** 2
    
    def perimeter(self):
        import math
        return 2 * math.pi * self.radius

class Triangle(Shape):
    def __init__(self, base, height, side1, side2):
        super().__init__("Triangle")
        self.base = base
        self.height = height
        self.side1 = side1
        self.side2 = side2
    
    def area(self):
        return 0.5 * self.base * self.height
    
    def perimeter(self):
        return self.base + self.side1 + self.side2

# Using polymorphism
shapes = [
    Rectangle(5, 3),
    Circle(4),
    Triangle(6, 4, 5, 5)
]

# Same method call, different implementations
for shape in shapes:
    print(shape.describe())
```

### When to Use Polymorphism

Use polymorphism when:
- **You have objects that share common behavior** (all shapes can calculate area)
- **You want to treat different objects the same way** (loop through all shapes)
- **You need flexible, extensible code** (easy to add new shape types)
- **You want to avoid complex if/else statements** (let each object handle its own behavior)

## Real-World Example: Library System

Let's build a comprehensive library system using inheritance:

```python
class LibraryItem:
    def __init__(self, title, author, item_id):
        self.title = title
        self.author = author
        self.item_id = item_id
        self.available = True
        self.borrower = None
        self.due_date = None
    
    def borrow(self, borrower_name, due_date):
        if self.available:
            self.available = False
            self.borrower = borrower_name
            self.due_date = due_date
            print(f"'{self.title}' borrowed by {borrower_name}")
        else:
            print(f"'{self.title}' is not available")
    
    def return_item(self):
        if not self.available:
            self.available = True
            borrower = self.borrower
            self.borrower = None
            self.due_date = None
            print(f"'{self.title}' returned by {borrower}")
        else:
            print(f"'{self.title}' is already available")
    
    def get_info(self):
        status = "Available" if self.available else f"Borrowed by {self.borrower}"
        return f"{self.title} by {self.author} - {status}"

class Book(LibraryItem):
    def __init__(self, title, author, item_id, pages, genre):
        super().__init__(title, author, item_id)
        self.pages = pages
        self.genre = genre
        self.item_type = "Book"
    
    def get_info(self):
        base_info = super().get_info()
        return f"{base_info} - {self.pages} pages, {self.genre}"

class DVD(LibraryItem):
    def __init__(self, title, director, item_id, duration, rating):
        super().__init__(title, director, item_id)
        self.duration = duration
        self.rating = rating
        self.item_type = "DVD"
    
    def get_info(self):
        base_info = super().get_info()
        return f"{base_info} - {self.duration} minutes, Rated {self.rating}"

class Magazine(LibraryItem):
    def __init__(self, title, publisher, item_id, issue_number, publication_date):
        super().__init__(title, publisher, item_id)
        self.issue_number = issue_number
        self.publication_date = publication_date
        self.item_type = "Magazine"
    
    def get_info(self):
        base_info = super().get_info()
        return f"{base_info} - Issue #{self.issue_number}, {self.publication_date}"

# Using the library system
library_items = [
    Book("Python Programming", "Jane Doe", "B001", 350, "Programming"),
    DVD("The Matrix", "Wachowskis", "D001", 136, "R"),
    Magazine("National Geographic", "NG Society", "M001", 2024, "January 2024")
]

# Polymorphism in action
for item in library_items:
    print(item.get_info())
    item.borrow("Alice", "2024-02-01")
    print()
```

## Best Practices for Inheritance

### 1. Use Inheritance for "Is-A" Relationships
```python
# GOOD - Car IS-A Vehicle
class Car(Vehicle):
    pass

# BAD - Car HAS-A Engine (use composition instead)
class Car:
    def __init__(self):
        self.engine = Engine()  # Composition, not inheritance
```

### 2. Keep Inheritance Hierarchies Shallow
```python
# GOOD - Simple hierarchy
class Animal:
    pass

class Dog(Animal):
    pass

# AVOID - Deep hierarchy
class Animal:
    pass

class Mammal(Animal):
    pass

class Canine(Mammal):
    pass

class Dog(Canine):
    pass
```

### 3. Use `super()` for Parent Method Calls
```python
class Parent:
    def __init__(self, name):
        self.name = name

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)  # GOOD
        self.age = age
```

### 4. Override Methods When Needed
```python
class Animal:
    def make_sound(self):
        print("Generic animal sound")

class Dog(Animal):
    def make_sound(self):
        print("Woof!")  # Override for specific behavior
```

## Common Mistakes to Avoid

1. **Forgetting to call `super().__init__()`**
```python
# WRONG
class Child(Parent):
    def __init__(self, name, age):
        self.age = age  # Parent's __init__ not called

# CORRECT
class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)  # Call parent's __init__
        self.age = age
```

2. **Using inheritance when composition is better**
```python
# WRONG - Car doesn't need to inherit from Engine
class Car(Engine):
    pass

# CORRECT - Car has an engine
class Car:
    def __init__(self):
        self.engine = Engine()
```

3. **Not overriding methods when you should**
```python
# WRONG - Generic behavior for all animals
class Dog(Animal):
    pass  # Dog will make "generic animal sound"

# CORRECT - Specific behavior for dogs
class Dog(Animal):
    def make_sound(self):
        print("Woof!")
```

## Key Points to Remember

1. **Inheritance** - Create new classes based on existing ones
2. **Method Overriding** - Child classes can provide their own method implementations
3. **`super()`** - Call parent class methods from child classes
4. **Polymorphism** - Same method, different behavior based on object type
5. **"Is-A" Relationship** - Use inheritance when child IS-A parent
6. **Code Reuse** - Don't repeat code, inherit it instead

## Next Steps

In the next sections, we'll:
- Work on real-world problems that require inheritance
- Learn to build complex class hierarchies
- Practice creating polymorphic systems
- See how inheritance makes code more organized and maintainable

Remember: Inheritance is a powerful tool for organizing code and creating reusable, extensible systems. Use it wisely to build better programs!
