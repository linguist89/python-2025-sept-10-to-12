(python_conditionals)=
# Session 4: Making Decisions with Conditionals

Now that you can get input from users and work with variables, let's learn how to make your programs make decisions! This is where programming gets really interesting.

::::::{topic} Learning Objectives
By the end of this session, you will be able to:
- Use `if`, `elif`, and `else` statements
- Compare values using comparison operators
- Create programs that make decisions
- Handle multiple conditions
- Use logical operators (`and`, `or`, `not`)
::::::

## Basic If Statements

The `if` statement allows your program to make decisions based on conditions:

```python
# Simple if statement
age = 18

if age >= 18:
    print("You are an adult!")
```

## Comparison Operators

Python has several operators to compare values:

```python
# Comparison operators
x = 10
y = 5

print(x > y)   # Greater than: True
print(x < y)   # Less than: False
print(x >= y)  # Greater than or equal: True
print(x <= y)  # Less than or equal: False
print(x == y)  # Equal to: False
print(x != y)  # Not equal to: True
```

## If-Else Statements

Use `else` to handle the case when the condition is false:

```python
# If-else statement
age = int(input("Enter your age: "))

if age >= 18:
    print("You can vote!")
else:
    print("You cannot vote yet.")
```

## If-Elif-Else Statements

Use `elif` (else if) to handle multiple conditions:

```python
# Multiple conditions
score = int(input("Enter your test score: "))

if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"

print(f"Your grade is: {grade}")
```

## Logical Operators

Combine conditions using `and`, `or`, and `not`:

```python
# Logical operators
age = 25
has_license = True

# AND operator - both conditions must be true
if age >= 18 and has_license:
    print("You can drive!")

# OR operator - at least one condition must be true
if age < 18 or not has_license:
    print("You cannot drive.")

# NOT operator - reverses the condition
if not has_license:
    print("You need a license to drive.")
```

## Practical Examples

### Example 1: Temperature Checker

```python
# Temperature checker
temperature = float(input("Enter the temperature in Celsius: "))

if temperature > 30:
    print("It's hot! Stay hydrated.")
elif temperature > 20:
    print("It's warm and pleasant.")
elif temperature > 10:
    print("It's cool. You might need a jacket.")
else:
    print("It's cold! Bundle up.")
```

### Example 2: Password Checker

```python
# Simple password checker
correct_password = "python123"
user_password = input("Enter the password: ")

if user_password == correct_password:
    print("Access granted!")
else:
    print("Access denied!")
```

### Example 3: Number Classifier

```python
# Number classifier
number = int(input("Enter a number: "))

if number > 0:
    print("The number is positive.")
elif number < 0:
    print("The number is negative.")
else:
    print("The number is zero.")

# Check if even or odd
if number % 2 == 0:
    print("The number is even.")
else:
    print("The number is odd.")
```

## Nested If Statements

You can put if statements inside other if statements:

```python
# Nested conditions
age = int(input("Enter your age: "))
has_license = input("Do you have a driver's license? (yes/no): ").lower()

if age >= 16:
    if has_license == "yes":
        print("You can drive!")
    else:
        print("You're old enough but need a license.")
else:
    print("You're too young to drive.")
```

