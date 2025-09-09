(python_variables_2)=
# Session 2: Working with Variables - Operations and Manipulation

Now that you understand the basics of variables, let's learn how to work with them! In this session, you'll discover how to perform operations on variables and manipulate their values.

::::::{topic} Learning Objectives
By the end of this session, you will be able to:
- Perform mathematical operations with variables
- Manipulate string variables
- Update variable values
- Understand variable reassignment
- Use variables in expressions
::::::

## Mathematical Operations with Variables

You can perform mathematical operations using variables just like you would with numbers:

```python
# Basic arithmetic operations
a = 10
b = 3

# Addition
sum_result = a + b
print(sum_result)  # Output: 13

# Subtraction
difference = a - b
print(difference)  # Output: 7

# Multiplication
product = a * b
print(product)     # Output: 30

# Division
quotient = a / b
print(quotient)    # Output: 3.3333333333333335

# Floor division (whole number division)
floor_quotient = a // b
print(floor_quotient)  # Output: 3

# Modulus (remainder)
remainder = a % b
print(remainder)   # Output: 1

# Exponentiation (power)
power = a ** b
print(power)       # Output: 1000
```

## String Operations

Strings can be combined and manipulated in various ways:

```python
# String concatenation (joining strings)
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name
print(full_name)  # Output: John Doe

# String repetition
greeting = "Hello! "
repeated_greeting = greeting * 3
print(repeated_greeting)  # Output: Hello! Hello! Hello!

# String length
name_length = len(full_name)
print(name_length)  # Output: 8
```

## Updating Variable Values

Variables can be updated by assigning new values to them:

```python
# Initial value
count = 5
print("Initial count:", count)

# Update the value
count = count + 1  # This is the same as count += 1
print("After adding 1:", count)

# Shortcut operators
count += 2  # Same as count = count + 2
print("After adding 2:", count)

count -= 1  # Same as count = count - 1
print("After subtracting 1:", count)

count *= 2  # Same as count = count * 2
print("After multiplying by 2:", count)
```

## Variables in Expressions

You can use variables in complex expressions:

```python
# Calculate the area of a rectangle
length = 10
width = 5
area = length * width
print(f"The area is {area} square units")

# Calculate a percentage
total_points = 100
earned_points = 85
percentage = (earned_points / total_points) * 100
print(f"You scored {percentage}%")

# Temperature conversion
celsius = 25
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius}°C is {fahrenheit}°F")
```

## Type Conversion

Sometimes you need to convert between different data types:

```python
# Converting numbers to strings
age = 25
age_string = str(age)
print("I am " + age_string + " years old")

# Converting strings to numbers
user_input = "42"
number = int(user_input)
doubled = number * 2
print(f"Double of {number} is {doubled}")

# Converting to float
price_string = "19.99"
price = float(price_string)
tax = price * 0.08
print(f"Tax on ${price} is ${tax:.2f}")
```
