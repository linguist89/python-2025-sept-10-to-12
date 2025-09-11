# Practice Classes: Advanced Methods and Attributes

## Instructions

For each problem below, create a class that demonstrates different types of methods and attributes. Remember to:
- Use instance methods for object-specific operations
- Use class methods for alternative constructors or class-level operations
- Use static methods for utility functions
- Use class attributes for shared data
- Test your classes with the provided data

## Problem 1: Enhanced Student Class

### Scenario
A university needs a more sophisticated student management system with class-level tracking and utility functions.

### Requirements
Create an enhanced `Student` class that includes:
- Instance attributes: name, student_id, major, grades
- Class attributes: school_name, total_students
- Instance methods: add_grade, calculate_gpa, get_info
- Class method: create_honor_student (GPA bonus)
- Static method: calculate_letter_grade (percentage to letter)

### Test Data
- Regular student: "Alice Johnson", "S12345", "Computer Science"
- Honor student: "Bob Smith", "S12346", "Mathematics" (with 3.8 GPA bonus)
- Grades: 85, 92, 78, 96, 88
- Expected GPA: 3.48 (B+)

### Your Class
```python
class Student:
    # Class attributes
    school_name = "Python University"
    total_students = 0
    
    def __init__(self, name, student_id, major):
        # Instance attributes
        # Your code here
        pass
    
    def add_grade(self, grade):
        # Instance method
        # Your code here
        pass
    
    def calculate_gpa(self):
        # Instance method
        # Your code here
        pass
    
    def get_info(self):
        # Instance method
        # Your code here
        pass
    
    @classmethod
    def create_honor_student(cls, name, student_id, major, gpa_bonus):
        # Class method - alternative constructor
        # Your code here
        pass
    
    @staticmethod
    def calculate_letter_grade(percentage):
        # Static method - utility function
        # Your code here
        pass
```

## Problem 2: Library Management System

### Scenario
A library needs to track books, members, and borrowing with class-level statistics.

### Requirements
Create a `Library` class that includes:
- Instance attributes: name, books, members, borrowed_books
- Class attributes: total_libraries, library_types
- Instance methods: add_book, add_member, borrow_book, return_book, get_stats
- Class method: create_digital_library
- Static method: validate_isbn

### Test Data
- Library: "Central Library"
- Add books: "Python Guide" (ISBN: 1234567890), "Java Basics" (ISBN: 0987654321)
- Add member: "Alice", "M001"
- Borrow: Alice borrows "Python Guide"
- Expected: 1 book borrowed, 1 available

### Your Class
```python
class Library:
    # Class attributes
    total_libraries = 0
    library_types = ["public", "academic", "digital"]
    
    def __init__(self, name, library_type="public"):
        # Instance attributes
        # Your code here
        pass
    
    def add_book(self, title, author, isbn):
        # Instance method
        # Your code here
        pass
    
    def add_member(self, name, member_id):
        # Instance method
        # Your code here
        pass
    
    def borrow_book(self, member_id, isbn):
        # Instance method
        # Your code here
        pass
    
    def return_book(self, member_id, isbn):
        # Instance method
        # Your code here
        pass
    
    def get_stats(self):
        # Instance method
        # Your code here
        pass
    
    @classmethod
    def create_digital_library(cls, name):
        # Class method - alternative constructor
        # Your code here
        pass
    
    @staticmethod
    def validate_isbn(isbn):
        # Static method - utility function
        # Your code here
        pass
```

## Problem 3: Bank Account with Advanced Features

### Scenario
A bank needs an advanced account system with different account types and class-level banking operations.

### Requirements
Create a `BankAccount` class that includes:
- Instance attributes: account_holder, balance, account_type, account_number, transactions
- Class attributes: bank_name, interest_rate, total_accounts, account_types
- Instance methods: deposit, withdraw, get_balance, get_statement
- Class method: create_business_account (higher interest)
- Static method: calculate_compound_interest

### Test Data
- Regular account: "Alice", $1000, "checking"
- Business account: "Bob's Company", $5000, "business" (2% bonus interest)
- Transactions: Deposit $500, Withdraw $200
- Expected final balance: $1300

### Your Class
```python
class BankAccount:
    # Class attributes
    bank_name = "Python Bank"
    interest_rate = 0.02
    total_accounts = 0
    account_types = ["checking", "savings", "business"]
    
    def __init__(self, account_holder, initial_balance, account_type="checking"):
        # Instance attributes
        # Your code here
        pass
    
    def deposit(self, amount):
        # Instance method
        # Your code here
        pass
    
    def withdraw(self, amount):
        # Instance method
        # Your code here
        pass
    
    def get_balance(self):
        # Instance method
        # Your code here
        pass
    
    def get_statement(self):
        # Instance method
        # Your code here
        pass
    
    @classmethod
    def create_business_account(cls, account_holder, initial_balance):
        # Class method - alternative constructor
        # Your code here
        pass
    
    @staticmethod
    def calculate_compound_interest(principal, rate, time, compounds_per_year=12):
        # Static method - utility function
        # Your code here
        pass
```

## Problem 4: Shopping Cart with Inventory Management

### Scenario
An e-commerce platform needs a shopping cart system with inventory tracking and class-level analytics.

### Requirements
Create a `ShoppingCart` class that includes:
- Instance attributes: customer_name, items, total_cost, cart_id
- Class attributes: total_carts, store_name, tax_rate
- Instance methods: add_item, remove_item, calculate_total, apply_discount
- Class method: create_guest_cart
- Static method: calculate_tax

### Test Data
- Customer: "Alice"
- Add items: "Laptop" ($999), "Mouse" ($25), "Keyboard" ($75)
- Apply 10% discount
- Expected total with tax: $1098.90 (assuming 8% tax)

### Your Class
```python
class ShoppingCart:
    # Class attributes
    total_carts = 0
    store_name = "Python Store"
    tax_rate = 0.08
    
    def __init__(self, customer_name):
        # Instance attributes
        # Your code here
        pass
    
    def add_item(self, item_name, price, quantity=1):
        # Instance method
        # Your code here
        pass
    
    def remove_item(self, item_name):
        # Instance method
        # Your code here
        pass
    
    def calculate_total(self):
        # Instance method
        # Your code here
        pass
    
    def apply_discount(self, discount_percentage):
        # Instance method
        # Your code here
        pass
    
    def get_cart_summary(self):
        # Instance method
        # Your code here
        pass
    
    @classmethod
    def create_guest_cart(cls):
        # Class method - alternative constructor
        # Your code here
        pass
    
    @staticmethod
    def calculate_tax(subtotal, tax_rate):
        # Static method - utility function
        # Your code here
        pass
```

## Problem 5: Employee Management System

### Scenario
A company needs an employee management system with different employee types and class-level HR operations.

### Requirements
Create an `Employee` class that includes:
- Instance attributes: name, employee_id, department, salary, hire_date
- Class attributes: company_name, total_employees, departments
- Instance methods: get_salary, update_salary, get_tenure, get_info
- Class method: create_manager (salary bonus)
- Static method: calculate_annual_bonus

### Test Data
- Regular employee: "Alice", "E001", "Engineering", $75000
- Manager: "Bob", "E002", "Engineering", $90000 (20% bonus)
- Expected manager salary: $108000

### Your Class
```python
class Employee:
    # Class attributes
    company_name = "Python Corp"
    total_employees = 0
    departments = ["Engineering", "Marketing", "Sales", "HR"]
    
    def __init__(self, name, employee_id, department, salary, hire_date="2024-01-01"):
        # Instance attributes
        # Your code here
        pass
    
    def get_salary(self):
        # Instance method
        # Your code here
        pass
    
    def update_salary(self, new_salary):
        # Instance method
        # Your code here
        pass
    
    def get_tenure(self):
        # Instance method
        # Your code here
        pass
    
    def get_info(self):
        # Instance method
        # Your code here
        pass
    
    @classmethod
    def create_manager(cls, name, employee_id, department, base_salary, bonus_percentage=0.2):
        # Class method - alternative constructor
        # Your code here
        pass
    
    @staticmethod
    def calculate_annual_bonus(salary, performance_rating):
        # Static method - utility function
        # Your code here
        pass
```

## Problem 6: Temperature Converter with History

### Scenario
A weather application needs a temperature converter that tracks conversion history and provides class-level statistics.

### Requirements
Create a `TemperatureConverter` class that includes:
- Instance attributes: current_temp, current_unit, conversion_history
- Class attributes: supported_units, total_conversions
- Instance methods: convert_to, get_history, get_current_temp
- Class method: create_from_celsius
- Static method: validate_temperature

### Test Data
- Start with: 25°C
- Convert to Fahrenheit: 77°F
- Convert to Kelvin: 298.15K
- Expected history: 3 conversions

### Your Class
```python
class TemperatureConverter:
    # Class attributes
    supported_units = ["celsius", "fahrenheit", "kelvin"]
    total_conversions = 0
    
    def __init__(self, temperature, unit="celsius"):
        # Instance attributes
        # Your code here
        pass
    
    def convert_to(self, target_unit):
        # Instance method
        # Your code here
        pass
    
    def get_history(self):
        # Instance method
        # Your code here
        pass
    
    def get_current_temp(self):
        # Instance method
        # Your code here
        pass
    
    @classmethod
    def create_from_celsius(cls, temperature):
        # Class method - alternative constructor
        # Your code here
        pass
    
    @staticmethod
    def validate_temperature(temp, unit):
        # Static method - utility function
        # Your code here
        pass
```

## Problem 7: Recipe Manager with Nutrition Tracking

### Scenario
A cooking app needs a recipe management system with nutrition calculations and class-level recipe statistics.

### Requirements
Create a `Recipe` class that includes:
- Instance attributes: name, ingredients, instructions, servings, prep_time
- Class attributes: total_recipes, cuisine_types, difficulty_levels
- Instance methods: add_ingredient, calculate_nutrition, get_recipe_info
- Class method: create_quick_recipe (under 30 minutes)
- Static method: calculate_calories_per_serving

### Test Data
- Recipe: "Pasta Carbonara", 4 servings, 25 minutes
- Ingredients: "Pasta" (400g), "Eggs" (4), "Cheese" (100g)
- Expected: Quick recipe (under 30 minutes)

### Your Class
```python
class Recipe:
    # Class attributes
    total_recipes = 0
    cuisine_types = ["Italian", "Mexican", "Asian", "American"]
    difficulty_levels = ["Easy", "Medium", "Hard"]
    
    def __init__(self, name, servings, prep_time, difficulty="Easy"):
        # Instance attributes
        # Your code here
        pass
    
    def add_ingredient(self, ingredient, amount, unit="g"):
        # Instance method
        # Your code here
        pass
    
    def calculate_nutrition(self):
        # Instance method
        # Your code here
        pass
    
    def get_recipe_info(self):
        # Instance method
        # Your code here
        pass
    
    @classmethod
    def create_quick_recipe(cls, name, servings):
        # Class method - alternative constructor
        # Your code here
        pass
    
    @staticmethod
    def calculate_calories_per_serving(ingredients, servings):
        # Static method - utility function
        # Your code here
        pass
```

## Problem 8: Game Character with Class Abilities

### Scenario
A game needs a character system with different character types and class-level game statistics.

### Requirements
Create a `GameCharacter` class that includes:
- Instance attributes: name, character_class, level, health, experience
- Class attributes: total_characters, character_classes, max_level
- Instance methods: level_up, take_damage, heal, get_stats
- Class method: create_hero_character (bonus stats)
- Static method: calculate_damage

### Test Data
- Regular character: "Alice", "Warrior", Level 1, 100 HP
- Hero character: "Bob", "Mage", Level 1, 120 HP (20% bonus)
- Level up: +50 XP, +10 HP
- Expected: Level 2, 110 HP

### Your Class
```python
class GameCharacter:
    # Class attributes
    total_characters = 0
    character_classes = ["Warrior", "Mage", "Rogue", "Archer"]
    max_level = 100
    
    def __init__(self, name, character_class, level=1):
        # Instance attributes
        # Your code here
        pass
    
    def level_up(self, experience_gained):
        # Instance method
        # Your code here
        pass
    
    def take_damage(self, damage):
        # Instance method
        # Your code here
        pass
    
    def heal(self, healing_amount):
        # Instance method
        # Your code here
        pass
    
    def get_stats(self):
        # Instance method
        # Your code here
        pass
    
    @classmethod
    def create_hero_character(cls, name, character_class, bonus_percentage=0.2):
        # Class method - alternative constructor
        # Your code here
        pass
    
    @staticmethod
    def calculate_damage(base_damage, level, character_class):
        # Static method - utility function
        # Your code here
        pass
```

## Testing Your Classes

After writing each class, test it with the provided data:

```python
# Example testing for Student class
student1 = Student("Alice Johnson", "S12345", "Computer Science")
student1.add_grade(85)
student1.add_grade(92)
student1.add_grade(78)
student1.add_grade(96)
student1.add_grade(88)

honor_student = Student.create_honor_student("Bob Smith", "S12346", "Mathematics", 0.3)
letter_grade = Student.calculate_letter_grade(87.8)

print(f"Total students: {Student.total_students}")
print(f"School: {Student.school_name}")
```

## Advanced Challenges

Once you've completed the basic classes, try these advanced challenges:

### Challenge 1: Class Composition
Create a `School` class that manages multiple `Student` objects:

```python
class School:
    def __init__(self, name):
        self.name = name
        self.students = []
    
    def enroll_student(self, student):
        self.students.append(student)
    
    def get_school_stats(self):
        # Calculate statistics for all students
        pass
```

### Challenge 2: Method Chaining
Modify one of your classes to support method chaining:

```python
# Example: cart.add_item("Laptop", 999).add_item("Mouse", 25).apply_discount(10)
```

## Reflection Questions

After completing all classes, consider:

1. **When did you use class methods vs static methods?**
2. **How did class attributes help organize your code?**
3. **Which methods were most useful for your specific scenarios?**
4. **How could you make your classes more robust?**
5. **What real-world applications could benefit from these patterns?**

## Best Practices Summary

1. **Use instance methods for object-specific operations**
2. **Use class methods for alternative constructors**
3. **Use static methods for utility functions**
4. **Use class attributes for shared data**
5. **Keep methods focused on single responsibilities**
6. **Document your methods with clear docstrings**

## Next Steps

Once you've mastered these advanced class concepts, you'll be ready to move on to inheritance and polymorphism in the next session, including:
- Creating class hierarchies
- Method overriding
- The `super()` function
- Building complex object-oriented systems
