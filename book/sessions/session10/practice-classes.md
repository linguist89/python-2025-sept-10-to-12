# Practice Classes: Building Your First Classes

## Instructions

For each problem below, create a simple class that solves the real-world scenario. Remember to:
- Start with the `__init__` method to set up your object
- Add methods that work with the object's data
- Test your class with the provided data
- Use clear, descriptive names for your classes and methods

## Problem 1: Student Class

### Scenario
A school needs to track student information including grades and calculate averages.

### Requirements
Create a `Student` class that can:
- Store student name, ID, and major
- Add grades to the student's record
- Calculate the average grade
- Display student information

### Test Data
- Name: "Alice Johnson", ID: "S12345", Major: "Computer Science"
- Grades: 85, 92, 78, 96, 88
- Expected average: 87.8

### Your Class
```python
class Student:
    def __init__(self, name, student_id, major):
        # Your code here
        pass
    
    def add_grade(self, grade):
        # Your code here
        pass
    
    def calculate_average(self):
        # Your code here
        pass
    
    def display_info(self):
        # Your code here
        pass
```

## Problem 2: Bank Account Class

### Scenario
A bank needs to manage customer accounts with deposits, withdrawals, and balance checking.

### Requirements
Create a `BankAccount` class that can:
- Store account holder name and initial balance
- Make deposits
- Make withdrawals (check for sufficient funds)
- Check current balance
- Display account information

### Test Data
- Account holder: "John Smith", Initial balance: $1000
- Deposit: $500
- Withdrawal: $200
- Final balance should be: $1300

### Your Class
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
    
    def display_account_info(self):
        # Your code here
        pass
```

## Problem 3: Car Class

### Scenario
A car dealership needs to track inventory with basic car information and mileage.

### Requirements
Create a `Car` class that can:
- Store car make, model, year, and current mileage
- Add miles to the car (simulate driving)
- Display car information
- Calculate car age (current year - car year)

### Test Data
- Make: "Toyota", Model: "Camry", Year: 2020, Mileage: 25000
- Add 1000 miles
- Expected final mileage: 26000
- Expected age: 4 years (assuming current year is 2024)

### Your Class
```python
class Car:
    def __init__(self, make, model, year, mileage):
        # Your code here
        pass
    
    def add_miles(self, miles):
        # Your code here
        pass
    
    def get_age(self):
        # Your code here
        pass
    
    def display_info(self):
        # Your code here
        pass
```

## Problem 4: Book Class

### Scenario
A library needs to track books with basic information and reading status.

### Requirements
Create a `Book` class that can:
- Store book title, author, pages, and reading status
- Mark book as read or unread
- Display book information
- Calculate reading progress (if partially read)

### Test Data
- Title: "Python Programming", Author: "Jane Doe", Pages: 300
- Mark as read
- Expected status: "Read"

### Your Class
```python
class Book:
    def __init__(self, title, author, pages):
        # Your code here
        pass
    
    def mark_as_read(self):
        # Your code here
        pass
    
    def mark_as_unread(self):
        # Your code here
        pass
    
    def get_status(self):
        # Your code here
        pass
    
    def display_info(self):
        # Your code here
        pass
```

## Problem 5: Rectangle Class

### Scenario
A geometry application needs to calculate areas and perimeters of rectangles.

### Requirements
Create a `Rectangle` class that can:
- Store length and width
- Calculate area (length × width)
- Calculate perimeter (2 × (length + width))
- Display rectangle information

### Test Data
- Length: 10, Width: 5
- Expected area: 50
- Expected perimeter: 30

### Your Class
```python
class Rectangle:
    def __init__(self, length, width):
        # Your code here
        pass
    
    def calculate_area(self):
        # Your code here
        pass
    
    def calculate_perimeter(self):
        # Your code here
        pass
    
    def display_info(self):
        # Your code here
        pass
```

## Problem 6: Calculator Class

### Scenario
A simple calculator application needs to perform basic operations and keep track of the result.

### Requirements
Create a `Calculator` class that can:
- Store a current result (start at 0)
- Add, subtract, multiply, and divide
- Display the current result
- Reset the calculator

### Test Data
- Start with result: 0
- Add 10, then multiply by 3, then subtract 5
- Expected final result: 25

### Your Class
```python
class Calculator:
    def __init__(self):
        # Your code here
        pass
    
    def add(self, number):
        # Your code here
        pass
    
    def subtract(self, number):
        # Your code here
        pass
    
    def multiply(self, number):
        # Your code here
        pass
    
    def divide(self, number):
        # Your code here
        pass
    
    def get_result(self):
        # Your code here
        pass
    
    def reset(self):
        # Your code here
        pass
```

## Problem 7: Shopping Cart Class

### Scenario
An online store needs to track items in a customer's shopping cart.

### Requirements
Create a `ShoppingCart` class that can:
- Store a list of items and their prices
- Add items to the cart
- Remove items from the cart
- Calculate total cost
- Display cart contents

### Test Data
- Add items: "Laptop" ($999), "Mouse" ($25), "Keyboard" ($75)
- Remove "Mouse"
- Expected total: $1074

### Your Class
```python
class ShoppingCart:
    def __init__(self):
        # Your code here
        pass
    
    def add_item(self, item_name, price):
        # Your code here
        pass
    
    def remove_item(self, item_name):
        # Your code here
        pass
    
    def calculate_total(self):
        # Your code here
        pass
    
    def display_cart(self):
        # Your code here
        pass
```

## Problem 8: Temperature Converter Class

### Scenario
A weather application needs to convert temperatures between Celsius and Fahrenheit.

### Requirements
Create a `TemperatureConverter` class that can:
- Store a temperature value and its unit
- Convert between Celsius and Fahrenheit
- Display the temperature in both units
- Update the temperature value

### Test Data
- Initial: 25°C
- Convert to Fahrenheit: 77°F
- Update to 30°C, then convert: 86°F

### Your Class
```python
class TemperatureConverter:
    def __init__(self, temperature, unit):
        # Your code here
        pass
    
    def to_celsius(self):
        # Your code here
        pass
    
    def to_fahrenheit(self):
        # Your code here
        pass
    
    def update_temperature(self, temperature):
        # Your code here
        pass
    
    def display_both_units(self):
        # Your code here
        pass
```

## Testing Your Classes

After writing each class, test it with the provided data:

```python
# Example testing for Student class
student = Student("Alice Johnson", "S12345", "Computer Science")
student.add_grade(85)
student.add_grade(92)
student.add_grade(78)
student.add_grade(96)
student.add_grade(88)
student.display_info()
# Should show: Name, ID, Major, Grades, and Average: 87.8
```

## Building More Complex Classes

Once you've completed the basic classes, try combining them:

### Example: Library System
```python
class Library:
    def __init__(self, name):
        self.name = name
        self.books = []
        self.students = []
    
    def add_book(self, book):
        self.books.append(book)
    
    def add_student(self, student):
        self.students.append(student)
    
    def display_library_info(self):
        print(f"Library: {self.name}")
        print(f"Books: {len(self.books)}")
        print(f"Students: {len(self.students)}")
```

## Reflection Questions

After completing all classes, think about:

1. **Which class was easiest to create? Why?**
2. **Which class was most challenging? What made it difficult?**
3. **How did you decide what attributes and methods to include?**
4. **What would you do differently next time?**
5. **How could you make your classes more useful?**

## Next Steps

Once you've mastered these basic classes, you'll be ready to move on to more advanced class concepts in the next session, including:
- Different types of methods (class methods, static methods)
- Class attributes vs instance attributes
- More complex interactions between objects
- Better ways to organize and structure your classes
