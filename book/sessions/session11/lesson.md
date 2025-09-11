# Session 11: Class Methods and Attributes - Adding Behavior and Properties

## Learning Objectives

By the end of this session, you will be able to:
- Understand different types of methods (instance, class, static)
- Work with class attributes vs instance attributes
- Create methods that interact with object state
- Understand the `self` parameter thoroughly
- Apply classes to solve more complex problems

## Understanding Method Types

Think of methods like **different types of workers in a company**:

### 1. Instance Methods
Instance methods are like **personal assistants** - they work with one specific person (object) and know all their personal details.

**Real-World Analogy**: Like a personal bank teller who knows YOUR specific account balance and can help YOU make deposits.

```python
class BankAccount:
    def __init__(self, account_holder, initial_balance):
        self.account_holder = account_holder
        self.balance = initial_balance
    
    # Instance method - works with specific account
    def deposit(self, amount):
        self.balance += amount
        print(f"Deposited ${amount}. New balance: ${self.balance}")

# Using instance methods
account = BankAccount("Alice", 1000)
account.deposit(500)  # Works with Alice's specific account
```

**When to use**: When you need to work with data that belongs to a specific object (like Alice's balance, not all balances)

### 2. Class Methods
Class methods are like **company managers** - they work with company-wide information and can create new employees, but they don't deal with individual employee details.

**Real-World Analogy**: Like a bank manager who can create new types of accounts (savings, checking) and knows how many total accounts the bank has, but doesn't know your personal balance.

```python
class BankAccount:
    # Class attribute - shared by all instances
    bank_name = "Python Bank"
    total_accounts = 0
    
    def __init__(self, account_holder, initial_balance):
        self.account_holder = account_holder
        self.balance = initial_balance
        BankAccount.total_accounts += 1
    
    # Class method - works with the class, not instances
    @classmethod
    def create_savings_account(cls, account_holder, initial_balance):
        # Create account with bonus for savings
        bonus = initial_balance * 0.05  # 5% bonus
        return cls(account_holder, initial_balance + bonus)
    
    @classmethod
    def get_total_accounts(cls):
        return cls.total_accounts

# Using class methods
savings = BankAccount.create_savings_account("Bob", 1000)
print(f"Total accounts: {BankAccount.get_total_accounts()}")
```

**When to use**: When you need to work with information that applies to ALL objects of that type (like total count, alternative ways to create objects)

### 3. Static Methods
Static methods are like **utility tools** - they're helpful functions that don't need to know about any specific object or class, but they're kept in the class for organization.

**Real-World Analogy**: Like a calculator app on your phone - it doesn't need to know about your specific phone or account, it just does math calculations that anyone can use.

```python
class BankAccount:
    def __init__(self, account_holder, initial_balance):
        self.account_holder = account_holder
        self.balance = initial_balance
    
    # Static method - doesn't use self or cls
    @staticmethod
    def validate_account_number(account_number):
        # Simple validation - must be 8 digits
        return len(str(account_number)) == 8 and str(account_number).isdigit()
    
    @staticmethod
    def calculate_interest(principal, rate, time):
        return principal * rate * time

# Using static methods
is_valid = BankAccount.validate_account_number(12345678)
interest = BankAccount.calculate_interest(1000, 0.05, 2)
```

**When to use**: When you have utility functions that are related to the class but don't need access to any specific object's data (like validation, calculations, formatting)

## Understanding Private Methods

**Important**: Private methods are **not a separate type of method** - they're just regular instance methods with a special naming convention that indicates they should only be used internally.

Private methods are like **personal diary entries** - they're meant for internal use only and shouldn't be accessed from outside the class.

### Real-World Analogy: Restaurant Kitchen

Think of a restaurant:
- **Public methods** = The menu items customers can order (like `order_pizza()`)
- **Private methods** = Kitchen operations customers shouldn't see (like `prepare_dough()`, `cook_ingredients()`)

### What Makes a Method "Private"?

In Python, there are actually **two levels** of "privacy":

**Single Underscore (`_`)** - Naming convention only:
- They are still regular instance methods
- Python doesn't actually prevent access to them
- The underscore is just a signal to other programmers: "Don't use this method from outside the class"

**Double Underscore (`__`)** - Name mangling (actual access restriction):
- Python actually makes these harder to access from outside the class
- Python changes the method name internally (called "name mangling")
- This provides some protection, but it's not foolproof
- Generally not recommended for most use cases

```python
class BankAccount:
    def __init__(self, account_holder, initial_balance):
        self.account_holder = account_holder
        self.balance = initial_balance
        self.transaction_history = []
    
    # Public method - customers can use this
    def deposit(self, amount):
        if self._validate_amount(amount):  # Using private method
            self.balance += amount
            self._record_transaction("deposit", amount)
            print(f"Deposited ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid deposit amount")
    
    # Private method - internal use only
    def _validate_amount(self, amount):
        return amount > 0 and amount <= 10000
    
    # Private method - internal use only
    def _record_transaction(self, transaction_type, amount):
        transaction = {
            "type": transaction_type,
            "amount": amount,
            "balance_after": self.balance,
            "timestamp": "2024-01-01"
        }
        self.transaction_history.append(transaction)

# Using the class
account = BankAccount("Alice", 1000)
account.deposit(500)  # This works - public method

# This would work but is NOT recommended
# account._validate_amount(100)  # Don't do this! (Python allows it, but it's bad practice)

# Example of double underscore (name mangling)
class Example:
    def __init__(self):
        self.public_var = "accessible"
        self._single_underscore = "convention only"
        self.__double_underscore = "name mangled"
    
    def _private_method(self):
        return "This is accessible but not recommended"
    
    def __really_private_method(self):
        return "This is harder to access from outside"

# Usage examples:
obj = Example()
print(obj.public_var)                    # Works fine
print(obj._single_underscore)            # Works but not recommended
print(obj._private_method())             # Works but not recommended
# print(obj.__double_underscore)         # This would cause an AttributeError
# print(obj.__really_private_method())   # This would cause an AttributeError
```

### When to Use Private Methods

Use private methods when you need:
- **Internal helper functions** (like validation, formatting, calculations)
- **Implementation details** that users shouldn't access directly
- **Code organization** (break down complex public methods into smaller pieces)
- **Data protection** (prevent external code from bypassing your logic)

### Why Use Private Methods?

Think of private methods like **security guards**:
- **Encapsulation**: Hide internal complexity from users
- **Maintenance**: Change internal implementation without breaking external code
- **Safety**: Prevent users from calling methods that could break your object
- **Clarity**: Make it clear which methods are meant for external use

### Example: Enhanced Bank Account with Private Methods

```python
class BankAccount:
    def __init__(self, account_holder, initial_balance):
        self.account_holder = account_holder
        self.balance = initial_balance
        self.transaction_history = []
        self._account_number = self._generate_account_number()
    
    # Public methods - what users can do
    def deposit(self, amount):
        if self._validate_deposit(amount):
            self._process_deposit(amount)
            print(f"Deposited ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid deposit amount")
    
    def withdraw(self, amount):
        if self._validate_withdrawal(amount):
            self._process_withdrawal(amount)
            print(f"Withdrew ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid withdrawal amount")
    
    def get_balance(self):
        return self.balance
    
    # Private methods - internal implementation details
    def _generate_account_number(self):
        import random
        return f"ACC{random.randint(100000, 999999)}"
    
    def _validate_deposit(self, amount):
        return amount > 0 and amount <= 10000
    
    def _validate_withdrawal(self, amount):
        return amount > 0 and amount <= self.balance
    
    def _process_deposit(self, amount):
        self.balance += amount
        self._record_transaction("deposit", amount)
    
    def _process_withdrawal(self, amount):
        self.balance -= amount
        self._record_transaction("withdrawal", amount)
    
    def _record_transaction(self, transaction_type, amount):
        transaction = {
            "type": transaction_type,
            "amount": amount,
            "balance_after": self.balance,
            "timestamp": "2024-01-01"
        }
        self.transaction_history.append(transaction)

# Using the enhanced bank account
account = BankAccount("Alice", 1000)
account.deposit(500)    # Uses private methods internally
account.withdraw(200)   # Uses private methods internally
print(f"Balance: ${account.get_balance()}")
```

### Best Practices for Private Methods

1. **Use single underscore** (`_method_name`) for private methods - this is the recommended approach
2. **Avoid double underscores** (`__method_name`) unless you really need name mangling (rare cases)
3. **Don't access private methods from outside** the class (even though Python technically allows single underscore)
4. **Use private methods to break down complex public methods**
5. **Document what private methods do** (even though they're internal)
6. **Keep private methods focused** on single responsibilities
7. **Remember**: Single underscore is convention, double underscore provides some protection but is rarely needed

### Common Private Method Patterns

```python
class Student:
    def __init__(self, name, student_id):
        self.name = name
        self.student_id = student_id
        self.grades = []
    
    # Public method
    def add_grade(self, grade):
        if self._validate_grade(grade):
            self.grades.append(grade)
            print(f"Added grade: {grade}")
        else:
            print("Invalid grade")
    
    # Private helper methods
    def _validate_grade(self, grade):
        return 0 <= grade <= 100
    
    def _calculate_average(self):
        if not self.grades:
            return 0
        return sum(self.grades) / len(self.grades)
    
    def _format_grade_report(self):
        return f"Student: {self.name}\nGrades: {self.grades}\nAverage: {self._calculate_average():.2f}"
    
    # Public method that uses private methods
    def get_grade_report(self):
        return self._format_grade_report()
```

**When to use**: When you need internal helper functions that shouldn't be called directly by users of your class

**Key Points**: 
- **Single underscore (`_`)**: Just a naming convention - methods can still be accessed from outside, but the underscore signals they shouldn't be used externally
- **Double underscore (`__`)**: Provides some actual protection through name mangling, but is rarely needed and not recommended for most cases
- **Best practice**: Use single underscore for private methods - it's clear, conventional, and sufficient for most needs

## Class Attributes vs Instance Attributes

Think of this like **a school system**:

### Instance Attributes
Instance attributes are like **personal belongings** - each student has their own backpack, lunch, and homework.

**Real-World Analogy**: Like each student having their own name, student ID, and grades - these are personal to each individual.

```python
class Student:
    def __init__(self, name, student_id):
        # Instance attributes - different for each student
        self.name = name
        self.student_id = student_id
        self.grades = []

student1 = Student("Alice", "S001")
student2 = Student("Bob", "S002")

# Each student has their own name and grades
student1.name = "Alice"
student2.name = "Bob"
```

**When to use**: For data that's unique to each object (like personal information, individual states)

### Class Attributes
Class attributes are like **school-wide information** - all students share the same school name, mascot, and school rules.

**Real-World Analogy**: Like all students at the same school sharing the school name, school colors, and total enrollment count.

```python
class Student:
    # Class attributes - shared by all students
    school_name = "Python University"
    total_students = 0
    
    def __init__(self, name, student_id):
        # Instance attributes - different for each student
        self.name = name
        self.student_id = student_id
        self.grades = []
        Student.total_students += 1

# All students share the same school name
student1 = Student("Alice", "S001")
student2 = Student("Bob", "S002")

print(student1.school_name)  # Output: Python University
print(student2.school_name)  # Output: Python University
print(Student.total_students)  # Output: 2
```

**When to use**: For data that's the same for ALL objects of that type (like company name, default settings, counters)

## Working with the `self` Parameter

The `self` parameter is crucial in Python classes. It refers to the specific instance of the class.

### Understanding `self`

```python
class Car:
    def __init__(self, make, model, year):
        # self refers to the specific car being created
        self.make = make
        self.model = model
        self.year = year
        self.mileage = 0
    
    def drive(self, miles):
        # self refers to the specific car being driven
        self.mileage += miles
        print(f"The {self.year} {self.make} {self.model} now has {self.mileage} miles")
    
    def get_info(self):
        # self refers to the specific car's information
        return f"{self.year} {self.make} {self.model} - {self.mileage} miles"

# Creating car objects
car1 = Car("Toyota", "Camry", 2020)
car2 = Car("Honda", "Civic", 2021)

# Each car has its own self
car1.drive(100)  # self refers to car1
car2.drive(50)   # self refers to car2
```

### Methods That Interact with Object State

Methods can read and modify the object's attributes:

```python
class Library:
    def __init__(self, name):
        self.name = name
        self.books = []
        self.members = []
    
    def add_book(self, title, author):
        # Method that modifies object state
        book = {"title": title, "author": author, "available": True}
        self.books.append(book)
        print(f"Added '{title}' by {author}")
    
    def add_member(self, name, member_id):
        # Method that modifies object state
        member = {"name": name, "id": member_id, "books_borrowed": []}
        self.members.append(member)
        print(f"Added member: {name}")
    
    def borrow_book(self, member_name, book_title):
        # Method that reads and modifies object state
        # Find the member
        member = None
        for m in self.members:
            if m["name"] == member_name:
                member = m
                break
        
        # Find the book
        book = None
        for b in self.books:
            if b["title"] == book_title and b["available"]:
                book = b
                break
        
        if member and book:
            book["available"] = False
            member["books_borrowed"].append(book_title)
            print(f"{member_name} borrowed '{book_title}'")
        else:
            print("Cannot borrow book - member or book not found")
    
    def get_library_stats(self):
        # Method that reads object state
        total_books = len(self.books)
        available_books = sum(1 for book in self.books if book["available"])
        total_members = len(self.members)
        
        return {
            "total_books": total_books,
            "available_books": available_books,
            "borrowed_books": total_books - available_books,
            "total_members": total_members
        }
```

## Real-World Example: Enhanced Bank Account

Let's build a more sophisticated bank account class that demonstrates all these concepts:

```python
class BankAccount:
    # Class attributes
    bank_name = "Python Bank"
    interest_rate = 0.02  # 2% annual interest
    total_accounts = 0
    
    def __init__(self, account_holder, initial_balance, account_type="checking"):
        # Instance attributes
        self.account_holder = account_holder
        self.balance = initial_balance
        self.account_type = account_type
        self.account_number = self._generate_account_number()
        self.transaction_history = []
        
        # Update class attribute
        BankAccount.total_accounts += 1
    
    def _generate_account_number(self):
        # Private method (starts with underscore)
        import random
        return f"PB{random.randint(100000, 999999)}"
    
    def deposit(self, amount):
        # Instance method that modifies state
        if amount > 0:
            self.balance += amount
            self._record_transaction("deposit", amount)
            print(f"Deposited ${amount}. New balance: ${self.balance:.2f}")
        else:
            print("Deposit amount must be positive")
    
    def withdraw(self, amount):
        # Instance method that modifies state
        if amount > 0 and amount <= self.balance:
            self.balance -= amount
            self._record_transaction("withdrawal", amount)
            print(f"Withdrew ${amount}. New balance: ${self.balance:.2f}")
        else:
            print("Invalid withdrawal amount")
    
    def _record_transaction(self, transaction_type, amount):
        # Private method to record transactions
        transaction = {
            "type": transaction_type,
            "amount": amount,
            "balance_after": self.balance,
            "timestamp": "2024-01-01"  # Simplified timestamp
        }
        self.transaction_history.append(transaction)
    
    def get_balance(self):
        # Instance method that reads state
        return self.balance
    
    def get_account_info(self):
        # Instance method that reads state
        return {
            "account_holder": self.account_holder,
            "account_number": self.account_number,
            "account_type": self.account_type,
            "balance": self.balance,
            "transactions": len(self.transaction_history)
        }
    
    @classmethod
    def create_savings_account(cls, account_holder, initial_balance):
        # Class method - alternative constructor
        bonus = initial_balance * 0.05  # 5% bonus for savings
        return cls(account_holder, initial_balance + bonus, "savings")
    
    @classmethod
    def get_bank_info(cls):
        # Class method that works with class data
        return {
            "bank_name": cls.bank_name,
            "interest_rate": cls.interest_rate,
            "total_accounts": cls.total_accounts
        }
    
    @staticmethod
    def calculate_interest(principal, rate, time):
        # Static method - utility function
        return principal * rate * time
    
    @staticmethod
    def validate_account_number(account_number):
        # Static method - validation function
        return len(account_number) == 8 and account_number.startswith("PB")

# Using the enhanced BankAccount class
account1 = BankAccount("Alice", 1000)
account2 = BankAccount.create_savings_account("Bob", 2000)

account1.deposit(500)
account1.withdraw(200)

print(account1.get_account_info())
print(BankAccount.get_bank_info())
```

## Best Practices for Class Methods and Attributes

### 1. Use Instance Methods for Object-Specific Operations
```python
class Student:
    def __init__(self, name):
        self.name = name
        self.grades = []
    
    def add_grade(self, grade):  # Instance method - works with specific student
        self.grades.append(grade)
```

### 2. Use Class Methods for Alternative Constructors
```python
class Student:
    @classmethod
    def from_string(cls, student_string):
        # Alternative way to create a student
        name, grade = student_string.split(",")
        student = cls(name)
        student.add_grade(float(grade))
        return student
```

### 3. Use Static Methods for Utility Functions
```python
class Student:
    @staticmethod
    def calculate_gpa(grades):
        # Utility function that doesn't need class or instance data
        return sum(grades) / len(grades) if grades else 0
```

### 4. Use Class Attributes for Shared Data
```python
class Student:
    school_name = "Python University"  # Shared by all students
    total_students = 0  # Counter shared by all students
```

## Common Mistakes to Avoid

1. **Forgetting `self` in instance methods**
```python
# WRONG
def deposit(amount):  # Missing self
    self.balance += amount

# CORRECT
def deposit(self, amount):  # Has self
    self.balance += amount
```

2. **Using instance attributes when you need class attributes**
```python
# WRONG - each object gets its own counter
class Student:
    def __init__(self, name):
        self.name = name
        self.total_students = 0  # This should be a class attribute

# CORRECT - shared counter
class Student:
    total_students = 0  # Class attribute
    
    def __init__(self, name):
        self.name = name
        Student.total_students += 1
```

3. **Not using `@classmethod` or `@staticmethod` decorators**
```python
# WRONG - this is actually an instance method
def create_savings_account(cls, account_holder, initial_balance):
    return cls(account_holder, initial_balance + 100)

# CORRECT - properly decorated class method
@classmethod
def create_savings_account(cls, account_holder, initial_balance):
    return cls(account_holder, initial_balance + 100)
```

## Key Points to Remember

1. **Instance methods** - Work with specific objects, use `self`
2. **Class methods** - Work with the class, use `cls`, decorated with `@classmethod`
3. **Static methods** - Don't use class or instance data, decorated with `@staticmethod`
4. **Instance attributes** - Different for each object
5. **Class attributes** - Shared by all objects of the class
6. **`self`** - Always refers to the specific instance being used

## Next Steps

In the next sections, we'll:
- Work on real-world problems that require different types of methods
- Learn to build more complex class hierarchies
- Practice creating classes that work together
- See how these concepts make your code more organized and powerful

Remember: Understanding method types and attributes is key to building effective object-oriented programs. Each type serves a specific purpose in organizing your code!
