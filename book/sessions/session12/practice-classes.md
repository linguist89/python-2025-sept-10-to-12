# Practice Classes: Inheritance and Advanced Concepts

## Instructions

For each problem below, create a class hierarchy using inheritance. Remember to:
- Use inheritance for "is-a" relationships
- Override methods when child classes need different behavior
- Use `super()` to call parent class methods
- Test your inheritance hierarchies with the provided data
- Apply polymorphism where appropriate

## Problem 1: Vehicle Hierarchy

### Scenario
A car dealership needs to manage different types of vehicles with common features and specialized behaviors.

### Requirements
Create a vehicle inheritance hierarchy:
- **Vehicle** (parent): make, model, year, mileage, start(), stop(), drive()
- **Car** (child of Vehicle): doors, honk(), get_info()
- **Truck** (child of Vehicle): cargo_capacity, load_cargo(), get_info()
- **Motorcycle** (child of Vehicle): engine_size, wheelie(), get_info()

### Test Data
- Car: "Toyota", "Camry", 2021, 4 doors
- Truck: "Ford", "F-150", 2020, 1000 lbs cargo capacity
- Motorcycle: "Honda", "CBR600", 2022, 600cc engine
- Drive each vehicle 100 miles

### Your Classes
```python
class Vehicle:
    def __init__(self, make, model, year):
        # Your code here
        pass
    
    def start(self):
        # Your code here
        pass
    
    def stop(self):
        # Your code here
        pass
    
    def drive(self, miles):
        # Your code here
        pass
    
    def get_info(self):
        # Your code here
        pass

class Car(Vehicle):
    def __init__(self, make, model, year, doors):
        # Your code here
        pass
    
    def honk(self):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class Truck(Vehicle):
    def __init__(self, make, model, year, cargo_capacity):
        # Your code here
        pass
    
    def load_cargo(self, weight):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class Motorcycle(Vehicle):
    def __init__(self, make, model, year, engine_size):
        # Your code here
        pass
    
    def wheelie(self):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass
```

## Problem 2: Animal Kingdom

### Scenario
A zoo management system needs to track different types of animals with common behaviors and specialized features.

### Requirements
Create an animal inheritance hierarchy:
- **Animal** (parent): name, species, age, make_sound(), move(), eat()
- **Mammal** (child of Animal): fur_color, give_birth(), get_info()
- **Bird** (child of Animal): wing_span, fly(), get_info()
- **Fish** (child of Animal): water_type, swim(), get_info()

### Test Data
- Mammal: "Buddy", "Dog", 3 years, "Brown"
- Bird: "Tweety", "Canary", 2 years, 15cm wingspan
- Fish: "Goldie", "Goldfish", 1 year, "Freshwater"
- Each animal should make its sound and move

### Your Classes
```python
class Animal:
    def __init__(self, name, species, age):
        # Your code here
        pass
    
    def make_sound(self):
        # Your code here
        pass
    
    def move(self):
        # Your code here
        pass
    
    def eat(self):
        # Your code here
        pass
    
    def get_info(self):
        # Your code here
        pass

class Mammal(Animal):
    def __init__(self, name, species, age, fur_color):
        # Your code here
        pass
    
    def give_birth(self):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class Bird(Animal):
    def __init__(self, name, species, age, wing_span):
        # Your code here
        pass
    
    def fly(self):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class Fish(Animal):
    def __init__(self, name, species, age, water_type):
        # Your code here
        pass
    
    def swim(self):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass
```

## Problem 3: Employee Management System

### Scenario
A company needs to manage different types of employees with varying responsibilities and compensation.

### Requirements
Create an employee inheritance hierarchy:
- **Employee** (parent): name, employee_id, salary, work(), get_salary()
- **Manager** (child of Employee): team_size, manage_team(), get_salary() (with bonus)
- **Developer** (child of Employee): programming_language, code(), get_salary()
- **Salesperson** (child of Employee): commission_rate, make_sale(), get_salary() (with commission)

### Test Data
- Manager: "Alice", "M001", $75000, team of 5 people
- Developer: "Bob", "D001", $65000, "Python"
- Salesperson: "Carol", "S001", $50000, 5% commission
- Each employee should work and show their total compensation

### Your Classes
```python
class Employee:
    def __init__(self, name, employee_id, salary):
        # Your code here
        pass
    
    def work(self):
        # Your code here
        pass
    
    def get_salary(self):
        # Your code here
        pass
    
    def get_info(self):
        # Your code here
        pass

class Manager(Employee):
    def __init__(self, name, employee_id, salary, team_size):
        # Your code here
        pass
    
    def manage_team(self):
        # Your code here
        pass
    
    def get_salary(self):
        # Override with bonus
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class Developer(Employee):
    def __init__(self, name, employee_id, salary, programming_language):
        # Your code here
        pass
    
    def code(self):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class Salesperson(Employee):
    def __init__(self, name, employee_id, salary, commission_rate):
        # Your code here
        pass
    
    def make_sale(self, sale_amount):
        # Your code here
        pass
    
    def get_salary(self):
        # Override with commission
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass
```

## Problem 4: Library Item System

### Scenario
A library needs to manage different types of items with common borrowing features and specialized information.

### Requirements
Create a library item inheritance hierarchy:
- **LibraryItem** (parent): title, author, item_id, available, borrow(), return_item()
- **Book** (child of LibraryItem): pages, genre, get_info()
- **DVD** (child of LibraryItem): duration, rating, get_info()
- **Magazine** (child of LibraryItem): issue_number, publication_date, get_info()

### Test Data
- Book: "Python Guide", "Jane Doe", "B001", 350 pages, "Programming"
- DVD: "The Matrix", "Wachowskis", "D001", 136 minutes, "R"
- Magazine: "National Geographic", "NG Society", "M001", Issue 2024, "January 2024"
- Borrow each item to "Alice", then return them

### Your Classes
```python
class LibraryItem:
    def __init__(self, title, author, item_id):
        # Your code here
        pass
    
    def borrow(self, borrower_name):
        # Your code here
        pass
    
    def return_item(self):
        # Your code here
        pass
    
    def get_info(self):
        # Your code here
        pass

class Book(LibraryItem):
    def __init__(self, title, author, item_id, pages, genre):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class DVD(LibraryItem):
    def __init__(self, title, director, item_id, duration, rating):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class Magazine(LibraryItem):
    def __init__(self, title, publisher, item_id, issue_number, publication_date):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass
```

## Problem 5: Shape Hierarchy

### Scenario
A geometry application needs to calculate areas and perimeters for different shapes with common properties.

### Requirements
Create a shape inheritance hierarchy:
- **Shape** (parent): name, area(), perimeter(), describe()
- **Rectangle** (child of Shape): width, height, area(), perimeter()
- **Circle** (child of Shape): radius, area(), perimeter()
- **Triangle** (child of Shape): base, height, side1, side2, area(), perimeter()

### Test Data
- Rectangle: width=5, height=3 (area=15, perimeter=16)
- Circle: radius=4 (area≈50.27, perimeter≈25.13)
- Triangle: base=6, height=4, sides=5,5 (area=12, perimeter=16)

### Your Classes
```python
class Shape:
    def __init__(self, name):
        # Your code here
        pass
    
    def area(self):
        # Your code here
        pass
    
    def perimeter(self):
        # Your code here
        pass
    
    def describe(self):
        # Your code here
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        # Your code here
        pass
    
    def area(self):
        # Override parent method
        # Your code here
        pass
    
    def perimeter(self):
        # Override parent method
        # Your code here
        pass

class Circle(Shape):
    def __init__(self, radius):
        # Your code here
        pass
    
    def area(self):
        # Override parent method
        # Your code here
        pass
    
    def perimeter(self):
        # Override parent method
        # Your code here
        pass

class Triangle(Shape):
    def __init__(self, base, height, side1, side2):
        # Your code here
        pass
    
    def area(self):
        # Override parent method
        # Your code here
        pass
    
    def perimeter(self):
        # Override parent method
        # Your code here
        pass
```

## Problem 6: Game Character System

### Scenario
A role-playing game needs different character classes with common attributes and specialized abilities.

### Requirements
Create a character inheritance hierarchy:
- **Character** (parent): name, level, health, experience, attack(), level_up()
- **Warrior** (child of Character): strength, heavy_attack(), get_stats()
- **Mage** (child of Character): mana, cast_spell(), get_stats()
- **Rogue** (child of Character): stealth, sneak_attack(), get_stats()

### Test Data
- Warrior: "Conan", Level 1, 120 HP, 15 strength
- Mage: "Gandalf", Level 1, 80 HP, 100 mana
- Rogue: "Shadow", Level 1, 100 HP, 20 stealth
- Each character should attack and level up

### Your Classes
```python
class Character:
    def __init__(self, name, level=1):
        # Your code here
        pass
    
    def attack(self):
        # Your code here
        pass
    
    def level_up(self):
        # Your code here
        pass
    
    def get_stats(self):
        # Your code here
        pass

class Warrior(Character):
    def __init__(self, name, level=1, strength=10):
        # Your code here
        pass
    
    def heavy_attack(self):
        # Your code here
        pass
    
    def get_stats(self):
        # Override parent method
        # Your code here
        pass

class Mage(Character):
    def __init__(self, name, level=1, mana=50):
        # Your code here
        pass
    
    def cast_spell(self):
        # Your code here
        pass
    
    def get_stats(self):
        # Override parent method
        # Your code here
        pass

class Rogue(Character):
    def __init__(self, name, level=1, stealth=10):
        # Your code here
        pass
    
    def sneak_attack(self):
        # Your code here
        pass
    
    def get_stats(self):
        # Override parent method
        # Your code here
        pass
```

## Problem 7: Restaurant Menu System

### Scenario
A restaurant needs to manage different types of menu items with common features and specialized pricing.

### Requirements
Create a menu item inheritance hierarchy:
- **MenuItem** (parent): name, price, description, get_info()
- **Appetizer** (child of MenuItem): serving_size, get_info()
- **MainCourse** (child of MenuItem): cooking_time, get_info()
- **Dessert** (child of MenuItem): sweetness_level, get_info()

### Test Data
- Appetizer: "Caesar Salad", $8.99, "Fresh greens with dressing", "Small"
- Main Course: "Grilled Salmon", $18.99, "Fresh Atlantic salmon", 20 minutes
- Dessert: "Chocolate Cake", $6.99, "Rich chocolate cake", "Very Sweet"

### Your Classes
```python
class MenuItem:
    def __init__(self, name, price, description):
        # Your code here
        pass
    
    def get_info(self):
        # Your code here
        pass

class Appetizer(MenuItem):
    def __init__(self, name, price, description, serving_size):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class MainCourse(MenuItem):
    def __init__(self, name, price, description, cooking_time):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class Dessert(MenuItem):
    def __init__(self, name, price, description, sweetness_level):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass
```

## Problem 8: Bank Account Hierarchy

### Scenario
A bank needs different types of accounts with common banking features and specialized benefits.

### Requirements
Create a bank account inheritance hierarchy:
- **BankAccount** (parent): account_holder, balance, deposit(), withdraw(), get_balance()
- **CheckingAccount** (child of BankAccount): monthly_fee, apply_monthly_fee(), get_balance()
- **SavingsAccount** (child of BankAccount): interest_rate, add_interest(), get_balance()
- **BusinessAccount** (child of BankAccount): transaction_limit, withdraw() (with limit check)

### Test Data
- Checking: "Alice", $1000, $5 monthly fee
- Savings: "Bob", $5000, 2% interest rate
- Business: "Company XYZ", $10000, $2000 transaction limit
- Test deposits, withdrawals, and account-specific features

### Your Classes
```python
class BankAccount:
    def __init__(self, account_holder, initial_balance):
        # Your code here
        pass
    
    def deposit(self, amount):
        # Your code here
        pass
    
    def withdraw(self, amount):
        # Your code here
        pass
    
    def get_balance(self):
        # Your code here
        pass
    
    def get_info(self):
        # Your code here
        pass

class CheckingAccount(BankAccount):
    def __init__(self, account_holder, initial_balance, monthly_fee):
        # Your code here
        pass
    
    def apply_monthly_fee(self):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class SavingsAccount(BankAccount):
    def __init__(self, account_holder, initial_balance, interest_rate):
        # Your code here
        pass
    
    def add_interest(self):
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass

class BusinessAccount(BankAccount):
    def __init__(self, account_holder, initial_balance, transaction_limit):
        # Your code here
        pass
    
    def withdraw(self, amount):
        # Override with limit check
        # Your code here
        pass
    
    def get_info(self):
        # Override parent method
        # Your code here
        pass
```

## Testing Your Inheritance Hierarchies

After writing each class hierarchy, test it with the provided data:

```python
# Example testing for Vehicle hierarchy
vehicles = [
    Car("Toyota", "Camry", 2021, 4),
    Truck("Ford", "F-150", 2020, 1000),
    Motorcycle("Honda", "CBR600", 2022, 600)
]

# Polymorphism in action
for vehicle in vehicles:
    vehicle.start()
    vehicle.drive(100)
    print(vehicle.get_info())
    print()
```

## Advanced Challenges

Once you've completed the basic inheritance hierarchies, try these advanced challenges:

### Challenge 1: Multi-Level Inheritance
Create a three-level hierarchy:

```python
class Animal:
    pass

class Mammal(Animal):
    pass

class Dog(Mammal):
    pass
```

### Challenge 2: Method Chaining with Inheritance
Modify one of your hierarchies to support method chaining:

```python
# Example: car.start().drive(100).stop()
```

### Challenge 3: Composition vs Inheritance
Create a class that uses composition instead of inheritance:

```python
class Car:
    def __init__(self):
        self.engine = Engine()  # Composition
        self.wheels = [Wheel() for _ in range(4)]  # Composition
```

## Reflection Questions

After completing all inheritance hierarchies, consider:

1. **Which inheritance hierarchy was most challenging to design?**
2. **How did you decide when to override methods vs when to use parent methods?**
3. **What are the benefits of using inheritance in your solutions?**
4. **How did polymorphism make your code more flexible?**
5. **What real-world scenarios could benefit from these inheritance patterns?**

## Best Practices Summary

1. **Use inheritance for "is-a" relationships**
2. **Override methods when child classes need different behavior**
3. **Use `super()` to call parent class methods**
4. **Keep inheritance hierarchies shallow and focused**
5. **Apply polymorphism to make code more flexible**
6. **Consider composition as an alternative to inheritance**

## Next Steps

Once you've mastered inheritance and polymorphism, you'll be ready to:
- Build more complex object-oriented systems
- Work with existing Python libraries that use these patterns
- Create reusable, extensible code components
- Design better software architectures using OOP principles

Remember: Inheritance is a powerful tool for organizing code and creating reusable, extensible systems. Use it wisely to build better programs!
