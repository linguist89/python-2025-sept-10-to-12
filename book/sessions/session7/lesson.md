# Session 7: Your First Functions

## Learning Objectives

By the end of this session, you will be able to:
- Understand what functions are and why we use them
- Write your first simple functions
- Use functions to solve basic problems
- See how functions make code reusable

## What Are Functions?

A **function** is like a recipe in cooking. You write the recipe once, and then you can use it whenever you want to make that dish. In programming, a function is a piece of code that does something specific, and you can use it over and over again.

### Why Use Functions?

Think about these everyday examples:
- **Calculator buttons** - Each button does one thing (add, subtract, multiply)
- **Kitchen appliances** - A toaster always toasts bread the same way
- **Remote control** - Each button has one job (volume up, change channel)

Functions work the same way in programming:
1. **Reusability** - Write once, use many times
2. **Organization** - Break big problems into smaller pieces
3. **Simplicity** - Each function does one thing well

## Writing Your First Function

### Basic Function Structure

```python
def function_name():
    # What the function does goes here
    print("Hello from my function!")
```

### Example: A Simple Greeting Function

```python
def say_hello():
    print("Hello, world!")

# Using the function
say_hello()  # This will print "Hello, world!"
```

### Example: A Function That Does Math

```python
def add_numbers():
    result = 5 + 3
    print(f"5 + 3 = {result}")

# Using the function
add_numbers()  # This will print "5 + 3 = 8"
```

## Functions with Parameters

Sometimes you want your function to work with different numbers or text. You can give your function **parameters** (inputs).

### Example: Adding Any Two Numbers

```python
def add_two_numbers(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")

# Using the function with different numbers
add_two_numbers(5, 3)    # Prints "5 + 3 = 8"
add_two_numbers(10, 7)   # Prints "10 + 7 = 17"
add_two_numbers(100, 50) # Prints "100 + 50 = 150"
```

### Example: Greeting Different People

```python
def greet_person(name):
    print(f"Hello, {name}! Nice to meet you!")

# Using the function with different names
greet_person("Alice")  # Prints "Hello, Alice! Nice to meet you!"
greet_person("Bob")    # Prints "Hello, Bob! Nice to meet you!"
greet_person("Carol")  # Prints "Hello, Carol! Nice to meet you!"
```

## Functions That Give You Answers

Sometimes you want your function to give you a result that you can use later. You use `return` for this.

### Example: A Calculator Function

```python
def multiply_numbers(x, y):
    answer = x * y
    return answer

# Using the function and saving the result
result1 = multiply_numbers(4, 5)
print(f"4 × 5 = {result1}")  # Prints "4 × 5 = 20"

result2 = multiply_numbers(6, 7)
print(f"6 × 7 = {result2}")  # Prints "6 × 7 = 42"
```

### Example: Converting Temperature

```python
def celsius_to_fahrenheit(celsius):
    fahrenheit = (celsius * 9/5) + 32
    return fahrenheit

# Using the function
temp_c = 25
temp_f = celsius_to_fahrenheit(temp_c)
print(f"{temp_c}°C is {temp_f}°F")  # Prints "25°C is 77.0°F"
```

## Real-World Example: Simple Calculator

Let's build a simple calculator with different functions:

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    return a / b

# Using our calculator functions
print("Simple Calculator")
print("================")

num1 = 10
num2 = 3

print(f"{num1} + {num2} = {add(num1, num2)}")
print(f"{num1} - {num2} = {subtract(num1, num2)}")
print(f"{num1} × {num2} = {multiply(num1, num2)}")
print(f"{num1} ÷ {num2} = {divide(num1, num2)}")
```

## Key Points to Remember

### 1. Function Definition vs Function Call
```python
# Definition - creating the function
def my_function():
    print("This is my function")

# Call - using the function
my_function()  # This actually runs the function
```

### 2. Parameters vs Arguments
- **Parameters**: The names in the function definition (`a`, `b`)
- **Arguments**: The actual values you give when calling the function (`5`, `3`)

```python
def add_numbers(a, b):  # a and b are parameters
    return a + b

add_numbers(5, 3)  # 5 and 3 are arguments
```

### 3. Return vs Print
- **Print**: Shows something on the screen
- **Return**: Gives you a value you can use

```python
def print_result(x, y):
    print(x + y)  # Shows the result on screen

def get_result(x, y):
    return x + y  # Gives you the result to use

# Using print_result
print_result(5, 3)  # Shows "8" on screen

# Using get_result
answer = get_result(5, 3)  # answer is now 8
print(f"The answer is {answer}")  # Shows "The answer is 8"
```

## Common Mistakes to Avoid

1. **Forgetting the colon** after `def function_name():`
2. **Wrong indentation** - the function body must be indented
3. **Not calling the function** - defining it isn't enough, you need to call it
4. **Mixing up print and return** - use print to show, return to give a value

## Practice Makes Perfect

The best way to learn functions is to practice! Try writing functions for:
- Converting between different units (feet to meters, pounds to kilograms)
- Calculating areas and perimeters
- Working with text (counting letters, changing case)
- Simple games (guessing numbers, rock-paper-scissors)

## Next Steps

In the next sections, we'll:
- Work on real-world problems that need functions
- Learn to break big problems into smaller function pieces
- Practice creating functions that solve practical problems

Remember: Functions are like building blocks. Start simple, and you'll be building amazing programs in no time!
