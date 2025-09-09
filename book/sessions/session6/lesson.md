(python_functions)=
# Session 6: Functions - Reusable Code Blocks

Functions are one of the most important concepts in programming! They allow you to write code once and use it many times. Think of functions as recipes that you can follow whenever you need to cook the same dish.

::::::{topic} Learning Objectives
By the end of this session, you will be able to:
- Create and call functions
- Pass parameters to functions
- Return values from functions
- Understand function scope
- Write reusable code with functions
::::::

## What are Functions?

A function is a block of code that performs a specific task. Instead of writing the same code over and over, you can create a function and call it whenever needed.

```python
# Simple function
def greet():
    print("Hello, World!")

# Call the function
greet()  # Output: Hello, World!
```

## Functions with Parameters

Parameters allow you to pass data into a function:

```python
# Function with parameters
def greet_person(name):
    print(f"Hello, {name}!")

# Call the function with different names
greet_person("Alice")  # Output: Hello, Alice!
greet_person("Bob")    # Output: Hello, Bob!
```

## Functions with Multiple Parameters

You can pass multiple parameters to a function:

```python
# Function with multiple parameters
def greet_with_age(name, age):
    print(f"Hello, {name}! You are {age} years old.")

# Call the function
greet_with_age("Alice", 25)  # Output: Hello, Alice! You are 25 years old.
```

## Functions that Return Values

Functions can return values using the `return` statement:

```python
# Function that returns a value
def add_numbers(a, b):
    result = a + b
    return result

# Use the returned value
sum_result = add_numbers(5, 3)
print(sum_result)  # Output: 8

# You can also use the function directly
print(add_numbers(10, 20))  # Output: 30
```

## Practical Examples

### Example 1: Calculator Functions

```python
# Calculator functions
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y != 0:
        return x / y
    else:
        return "Cannot divide by zero!"

# Use the functions
print(add(10, 5))        # Output: 15
print(subtract(10, 5))   # Output: 5
print(multiply(10, 5))   # Output: 50
print(divide(10, 5))     # Output: 2.0
print(divide(10, 0))     # Output: Cannot divide by zero!
```

### Example 2: String Functions

```python
# String manipulation functions
def format_name(first, last):
    return f"{first} {last}".title()

def create_email(first, last, domain="company.com"):
    return f"{first.lower()}.{last.lower()}@{domain}"

# Use the functions
full_name = format_name("john", "doe")
email = create_email("john", "doe")
print(full_name)  # Output: John Doe
print(email)      # Output: john.doe@company.com
```

