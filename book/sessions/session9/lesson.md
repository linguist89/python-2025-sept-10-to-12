# Session 9: Introduction to *args and **kwargs

## Learning Objectives

By the end of this session, you will be able to:
- Understand what `*args` and `**kwargs` are and when to use them
- Write functions that accept variable numbers of arguments
- Use `*args` to handle multiple positional arguments
- Use `**kwargs` to handle multiple keyword arguments
- Apply these concepts to solve real-world problems

## What Are *args and **kwargs?

`*args` and `**kwargs` are special syntax in Python that allow functions to accept a variable number of arguments. Think of them as flexible containers that can hold any number of items.

### Real-World Analogy

Imagine you're organizing a party:
- **Regular function**: Like having a fixed guest list - you know exactly who's coming
- **Function with *args**: Like having an open invitation - anyone can show up
- **Function with **kwargs**: Like having a sign-up sheet where people can write their name and what they're bringing

## Understanding *args

`*args` allows a function to accept any number of positional arguments. The `*` tells Python to collect all the extra arguments into a tuple.

### Basic *args Example

```python
def add_numbers(*args):
    """Add any number of numbers together"""
    total = 0
    for number in args:
        total = total + number
    return total

# Using the function with different numbers of arguments
print(add_numbers(1, 2))           # Output: 3
print(add_numbers(1, 2, 3))        # Output: 6
print(add_numbers(1, 2, 3, 4, 5))  # Output: 15
```

### How *args Works

```python
def show_args(*args):
    """Show what *args contains"""
    print(f"Type of args: {type(args)}")
    print(f"Contents: {args}")
    print(f"Number of arguments: {len(args)}")

show_args(1, 2, 3)
# Output:
# Type of args: <class 'tuple'>
# Contents: (1, 2, 3)
# Number of arguments: 3
```

## Understanding **kwargs

`**kwargs` allows a function to accept any number of keyword arguments. The `**` tells Python to collect all the extra keyword arguments into a dictionary.

### Basic **kwargs Example

```python
def create_profile(**kwargs):
    """Create a user profile with any number of attributes"""
    print("User Profile:")
    for key, value in kwargs.items():
        print(f"  {key}: {value}")

# Using the function with different keyword arguments
create_profile(name="Alice", age=25, city="New York")
# Output:
# User Profile:
#   name: Alice
#   age: 25
#   city: New York

create_profile(name="Bob", occupation="Engineer", hobby="Reading")
# Output:
# User Profile:
#   name: Bob
#   occupation: Engineer
#   hobby: Reading
```

### How **kwargs Works

```python
def show_kwargs(**kwargs):
    """Show what **kwargs contains"""
    print(f"Type of kwargs: {type(kwargs)}")
    print(f"Contents: {kwargs}")
    print(f"Number of keyword arguments: {len(kwargs)}")

show_kwargs(name="Alice", age=25, city="Boston")
# Output:
# Type of kwargs: <class 'dict'>
# Contents: {'name': 'Alice', 'age': 25, 'city': 'Boston'}
# Number of keyword arguments: 3
```

## Combining *args and **kwargs

You can use both `*args` and `**kwargs` in the same function, but `*args` must come before `**kwargs`.

### Example: Flexible Function

```python
def flexible_function(required_arg, *args, **kwargs):
    """Function that accepts required argument, optional args, and keyword args"""
    print(f"Required argument: {required_arg}")
    print(f"Optional arguments: {args}")
    print(f"Keyword arguments: {kwargs}")

# Using the function
flexible_function("Hello", 1, 2, 3, name="Alice", age=25)
# Output:
# Required argument: Hello
# Optional arguments: (1, 2, 3)
# Keyword arguments: {'name': 'Alice', 'age': 25}
```

## When to Use *args and **kwargs

### Use *args when:
- You don't know how many arguments the function will receive
- You want to make a function more flexible
- You're working with lists or collections of similar items

### Use **kwargs when:
- You want to accept optional configuration parameters
- You're building functions that need to be highly customizable
- You're working with settings or options

## Real-World Examples

### Example 1: Shopping Cart Calculator

```python
def calculate_total(*prices):
    """Calculate total cost of any number of items"""
    total = 0
    for price in prices:
        total = total + price
    return total

# Calculate totals for different shopping trips
trip1 = calculate_total(10.99, 5.50, 3.25)  # 3 items
trip2 = calculate_total(25.00, 15.00, 8.99, 12.50, 6.75)  # 5 items
print(f"Trip 1 total: ${trip1:.2f}")  # Output: Trip 1 total: $19.74
print(f"Trip 2 total: ${trip2:.2f}")  # Output: Trip 2 total: $68.24
```

### Example 2: User Registration

```python
def register_user(**user_info):
    """Register a user with any number of optional fields"""
    print("Registering new user...")
    for field, value in user_info.items():
        print(f"  {field}: {value}")
    print("User registered successfully!")

# Register users with different information
register_user(name="Alice", email="alice@example.com", age=25)
register_user(name="Bob", email="bob@example.com", phone="555-1234", city="Boston")
```

### Example 3: Flexible Calculator

```python
def calculate(operation, *numbers, **options):
    """Perform calculations with any number of numbers and options"""
    if operation == "add":
        result = sum(numbers)
    elif operation == "multiply":
        result = 1
        for num in numbers:
            result = result * num
    else:
        return "Unknown operation"
    
    # Apply options
    if options.get("round", False):
        result = round(result)
    
    return result

# Using the flexible calculator
print(calculate("add", 1, 2, 3, 4))  # Output: 10
print(calculate("multiply", 2, 3, 4))  # Output: 24
print(calculate("add", 1.5, 2.7, round=True))  # Output: 4
```

## Key Points to Remember

### 1. Order Matters
```python
def correct_order(required, *args, **kwargs):
    pass  # This is correct

def wrong_order(required, **kwargs, *args):
    pass  # This will cause an error
```

### 2. Naming Convention
- `*args` and `**kwargs` are just conventions
- You can use any names: `*numbers`, `**options`, etc.
- The `*` and `**` are what matter, not the names

### 3. Unpacking Arguments
```python
def add_three(a, b, c):
    return a + b + c

numbers = [1, 2, 3]
result = add_three(*numbers)  # Unpacks the list
print(result)  # Output: 6

options = {"name": "Alice", "age": 25}
# You can unpack dictionaries too (but keys must match parameter names)
```

## Common Mistakes to Avoid

1. **Wrong order**: `**kwargs` must come after `*args`
2. **Forgetting the asterisks**: `*args` not `args`, `**kwargs` not `kwargs`
3. **Using both when you only need one**: Don't overcomplicate simple functions
4. **Not handling empty cases**: What happens when no extra arguments are passed?

## Best Practices

1. **Use descriptive names**: `*numbers` instead of `*args` when appropriate
2. **Document your functions**: Explain what arguments are expected
3. **Handle edge cases**: What if no arguments are passed?
4. **Keep it simple**: Don't use `*args` and `**kwargs` unless you need the flexibility

## Practice Makes Perfect

The best way to learn `*args` and `**kwargs` is to practice with real examples:
- Functions that work with lists of unknown length
- Configuration functions with optional parameters
- Utility functions that need to be flexible
- Functions that wrap other functions

## Next Steps

In the next sections, we'll:
- Work through real-world problems that need flexible functions
- Learn to build functions that can handle any number of arguments
- Practice creating reusable, flexible code
- See how these concepts make your code more powerful and adaptable

Remember: `*args` and `**kwargs` are tools for making your functions more flexible and reusable. Use them when you need that flexibility, but don't overcomplicate simple functions!
