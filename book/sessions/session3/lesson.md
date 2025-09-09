(python_input_output)=
# Session 3: User Input and Output

Great job on learning about variables! Now let's learn how to make your Python programs interactive by getting input from users and displaying output in different ways.

::::::{topic} Learning Objectives
By the end of this session, you will be able to:
- Get input from users using the `input()` function
- Display output using different methods
- Format strings for better output
- Handle different types of user input
- Create interactive programs
::::::

## Getting User Input

The `input()` function allows your program to get text from the user:

```python
# Basic input
name = input("What's your name? ")
print("Hello, " + name + "!")

# Input with a number
age = input("How old are you? ")
print("You are " + age + " years old")
```

## Important: Input Always Returns Strings

The `input()` function always returns a string, even if the user types a number:

```python
# This will cause an error!
age = input("Enter your age: ")
next_year = age + 1  # ERROR! Can't add string and number
print("Next year you'll be", next_year)
```

To fix this, you need to convert the string to a number:

```python
# Correct way to handle numeric input
age = input("Enter your age: ")
age = int(age)  # Convert string to integer
next_year = age + 1
print("Next year you'll be", next_year)

# Or do it in one line
age = int(input("Enter your age: "))
next_year = age + 1
print("Next year you'll be", next_year)
```

## Different Ways to Display Output

### 1. Basic Print Statements

```python
name = "Alice"
age = 25

# Multiple arguments (automatically separated by spaces)
print("Name:", name, "Age:", age)

# Using commas
print("Hello", name, "you are", age, "years old")
```

### 2. String Formatting with f-strings

F-strings (formatted string literals) are the modern way to format strings in Python:

```python
name = "Alice"
age = 25
height = 5.6

# f-string formatting
print(f"Hello {name}, you are {age} years old")
print(f"Your height is {height} feet")

# Formatting numbers
price = 19.99
print(f"The price is ${price:.2f}")  # Shows 2 decimal places
```

### 3. String Concatenation

```python
name = "Alice"
age = 25

# String concatenation
message = "Hello " + name + ", you are " + str(age) + " years old"
print(message)
```

## Creating Interactive Programs

Let's create a simple interactive program:

```python
# Interactive greeting program
print("Welcome to our Python program!")
print("=" * 30)

# Get user information
name = input("What's your name? ")
age = int(input("How old are you? "))
favorite_color = input("What's your favorite color? ")

# Display personalized message
print(f"\nNice to meet you, {name}!")
print(f"You are {age} years old.")
print(f"Your favorite color is {favorite_color}.")

# Calculate something
birth_year = 2024 - age
print(f"You were probably born in {birth_year}.")
```

## Handling Different Input Types

```python
# Getting a number
number = int(input("Enter a number: "))
doubled = number * 2
print(f"Double of {number} is {doubled}")

# Getting a decimal number
price = float(input("Enter a price: "))
tax = price * 0.08
total = price + tax
print(f"Price: ${price:.2f}")
print(f"Tax: ${tax:.2f}")
print(f"Total: ${total:.2f}")

# Getting a boolean-like input
response = input("Do you like Python? (yes/no): ")
if response.lower() == "yes":
    print("Great! Python is awesome!")
else:
    print("Maybe you'll change your mind after this course!")
```

