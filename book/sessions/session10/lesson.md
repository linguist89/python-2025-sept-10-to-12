# Session 10: Introduction to Classes - The Building Blocks of Object-Oriented Programming

## Learning Objectives

By the end of this session, you will be able to:
- Understand what classes are and why we use them
- Create your first simple classes
- Understand the difference between classes and objects
- Use classes to model real-world entities
- See how classes organize related data and behavior

## What Are Classes?

A **class** is like a blueprint or template for creating objects. Think of it as a cookie cutter - you use the same cutter to make many cookies, but each cookie can have different decorations.

### Real-World Analogies

- **Blueprint for a house** - The blueprint is the class, each house built from it is an object
- **Recipe for cookies** - The recipe is the class, each batch of cookies is an object
- **Car design** - The design is the class, each car made from that design is an object
- **Employee form** - The form template is the class, each filled-out form is an object

### Why Use Classes?

Classes help us organize our code by:
1. **Grouping related data and functions together** - Like keeping all your kitchen tools in one drawer
2. **Creating reusable templates** - Like having a standard form that you can fill out multiple times
3. **Modeling real-world concepts** - Like creating a digital version of real things
4. **Making code easier to understand and maintain** - Like organizing a messy room into labeled boxes

### When to Use Classes

Use classes when you want to:
- **Model real-world entities** (like a Student, BankAccount, or Car)
- **Group related data and behavior** (like a shopping cart with items and checkout methods)
- **Create multiple similar objects** (like multiple bank accounts or students)
- **Organize complex code** (when you have lots of related functions and variables)

### Why Classes Make Code Better

Think of classes like **organized filing cabinets**:
- **Before classes**: Your code is like papers scattered all over your desk
- **With classes**: Your code is like papers neatly organized in labeled folders
- **Result**: You can find what you need quickly and add new papers in the right place

## Basic Class Structure

```python
class ClassName:
    def __init__(self, parameter1, parameter2):
        self.attribute1 = parameter1
        self.attribute2 = parameter2
    
    def method_name(self):
        # What the method does
        pass
```

### Key Components Explained

Think of a class like a **job application form**:

1. **`class` keyword** - Like the form header that says "Job Application"
2. **`__init__` method** - Like the form setup process that creates a new application
3. **`self` parameter** - Like the application ID that identifies THIS specific application
4. **Attributes** - Like the blank fields on the form (name, address, phone)
5. **Methods** - Like the actions you can do with the form (submit, save, print)

### When to Use Each Component

- **Use `__init__`** when you need to set up an object with initial data (like filling in basic info on a form)
- **Use attributes** when you need to store data that belongs to the object (like personal information)
- **Use methods** when you need actions the object can perform (like submitting the form)
- **Use `self`** whenever you want to access or modify the object's own data

## Creating Your First Class

### Example: A Simple Person Class

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def introduce(self):
        print(f"Hi, I'm {self.name} and I'm {self.age} years old.")

# Creating objects from the class
person1 = Person("Alice", 25)
person2 = Person("Bob", 30)

# Using the objects
person1.introduce()  # Output: Hi, I'm Alice and I'm 25 years old.
person2.introduce()  # Output: Hi, I'm Bob and I'm 30 years old.
```

### Understanding the Code

1. **`class Person:`** - Creates a new class called Person
2. **`def __init__(self, name, age):`** - Special method that runs when creating a new Person
3. **`self.name = name`** - Stores the name in the object
4. **`self.age = age`** - Stores the age in the object
5. **`person1 = Person("Alice", 25)`** - Creates a new Person object
6. **`person1.introduce()`** - Calls the introduce method on person1

## Class vs Object

Think of this like **a factory and the products it makes**:

- **Class** - The factory blueprint and machinery (like a car factory)
- **Object** - The actual products made by the factory (like individual cars)

### Real-World Analogy: Pizza Restaurant

- **Class** = The pizza recipe and kitchen equipment
- **Object** = Each individual pizza made using that recipe

```python
# Class definition (the factory blueprint)
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year

# Creating objects (individual products) from the class
car1 = Car("Toyota", "Camry", 2020)  # Car #1 from the factory
car2 = Car("Honda", "Civic", 2021)   # Car #2 from the factory
car3 = Car("Ford", "Focus", 2019)    # Car #3 from the factory

# Each object has its own data (like each car has its own license plate)
print(car1.brand)  # Output: Toyota
print(car2.brand)  # Output: Honda
print(car3.brand)  # Output: Ford
```

### When to Create Objects

Create objects when you need:
- **Multiple similar things** (like multiple bank accounts)
- **Individual instances** (like different students in a class)
- **Unique data** (like each car having different colors and features)

## Adding Methods to Classes

Methods are like **tools that belong to an object** - they're the actions the object can perform.

### Real-World Analogy: Smartphone

Think of a smartphone class:
- **Attributes** = The phone's data (battery level, storage, apps installed)
- **Methods** = The phone's capabilities (make calls, send texts, take photos)

### Example: Bank Account Class

```python
class BankAccount:
    def __init__(self, account_holder, initial_balance):
        self.account_holder = account_holder
        self.balance = initial_balance
    
    def deposit(self, amount):
        self.balance = self.balance + amount
        print(f"Deposited ${amount}. New balance: ${self.balance}")
    
    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance = self.balance - amount
            print(f"Withdrew ${amount}. New balance: ${self.balance}")
        else:
            print("Insufficient funds!")
    
    def check_balance(self):
        print(f"Account holder: {self.account_holder}")
        print(f"Current balance: ${self.balance}")

# Using the BankAccount class
account = BankAccount("Alice", 1000)
account.check_balance()  # Shows initial balance
account.deposit(500)     # Deposits $500
account.withdraw(200)    # Withdraws $200
account.check_balance()  # Shows final balance
```

### When to Add Methods

Add methods when you need:
- **Actions the object can perform** (like a car that can start, stop, drive)
- **Ways to interact with the object's data** (like checking balance, updating info)
- **Business logic** (like validation rules, calculations)
- **User interface** (like displaying information, getting input)

## Real-World Example: Student Class

```python
class Student:
    def __init__(self, name, student_id, major):
        self.name = name
        self.student_id = student_id
        self.major = major
        self.grades = []
    
    def add_grade(self, grade):
        self.grades.append(grade)
        print(f"Added grade: {grade}")
    
    def calculate_average(self):
        if len(self.grades) > 0:
            average = sum(self.grades) / len(self.grades)
            return average
        else:
            return 0
    
    def get_info(self):
        print(f"Student: {self.name}")
        print(f"ID: {self.student_id}")
        print(f"Major: {self.major}")
        print(f"Grades: {self.grades}")
        print(f"Average: {self.calculate_average():.2f}")

# Creating and using student objects
student1 = Student("John", "S12345", "Computer Science")
student1.add_grade(85)
student1.add_grade(92)
student1.add_grade(78)
student1.get_info()
```

## Key Concepts to Remember

### 1. The `self` Parameter
Think of `self` like **a name tag** that says "this is MY data":
- `self` refers to the specific object being used (like "this specific car")
- Always the first parameter in class methods
- Python automatically passes the object as `self`

**When to use `self`**: Whenever you want to access or modify the object's own data

### 2. Attributes vs Methods
Think of this like **a person's profile**:
- **Attributes** - The person's information (name, age, height) - like `self.name`, `self.age`
- **Methods** - The person's abilities (walk, talk, eat) - like `introduce()`, `deposit()`

**When to use each**:
- **Attributes**: Store data that describes the object
- **Methods**: Define actions the object can perform

### 3. The `__init__` Method
Think of `__init__` like **a construction worker** who sets up a new building:
- Special method that runs when creating a new object
- Used to set up the object's initial state
- Like a constructor in other programming languages

**When to use `__init__`**: Always! It's how you give your objects their starting data

## Common Mistakes to Avoid

1. **Forgetting `self`** - Always include `self` as the first parameter in methods
2. **Wrong indentation** - Class methods must be indented under the class
3. **Not calling `__init__`** - Python calls it automatically when creating objects
4. **Mixing up class and object** - Remember: class is the blueprint, object is the instance

```python
# WRONG - Missing self
class Person:
    def __init__(name, age):  # Missing self!
        self.name = name
        self.age = age

# CORRECT - Including self
class Person:
    def __init__(self, name, age):  # Has self
        self.name = name
        self.age = age
```

## Best Practices

1. **Use descriptive class names** - `Student` is better than `S`
2. **Use descriptive attribute names** - `student_name` is better than `n`
3. **Keep classes focused** - One class should represent one concept
4. **Use docstrings** - Document what your class does

```python
class Book:
    """A class to represent a book with title, author, and pages."""
    
    def __init__(self, title, author, pages):
        self.title = title
        self.author = author
        self.pages = pages
    
    def get_info(self):
        """Return a formatted string with book information."""
        return f"'{self.title}' by {self.author} ({self.pages} pages)"
```

## Real-World Applications

Classes are used everywhere in programming:
- **User accounts** - Store user information and login methods
- **Shopping carts** - Track items and calculate totals
- **Game characters** - Store stats and abilities
- **File systems** - Represent files and folders
- **Database records** - Model real-world entities

## Practice Makes Perfect

The best way to learn classes is to practice creating them for real-world scenarios:
- **Library system** - Books, borrowers, loans
- **Restaurant** - Menu items, orders, customers
- **School** - Students, teachers, courses
- **Bank** - Accounts, transactions, customers

## Next Steps

In the next sections, we'll:
- Work on real-world problems that need classes
- Learn to create more complex classes with multiple methods
- Practice organizing related data and behavior together
- See how classes make code more organized and reusable

Remember: Classes are like blueprints for creating objects. Start simple, and you'll be building complex programs in no time!
