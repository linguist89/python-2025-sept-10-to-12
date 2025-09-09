# Session 2: Guided Questions - Step by Step

Work through these questions step by step. Each question will guide you through the thinking process and show you exactly how to solve it.

### Question 1: Basic Addition with Variables
**Problem:** Create two variables with numbers and add them together.

**Step 1:** Create the variables
```python
a = 10
b = 5
```

**Step 2:** Add them together
```python
result = a + b
print(f"{a} + {b} = {result}")
```

**Step 3:** Test with different numbers
Try changing the values of `a` and `b` to see different results.

### Question 2: String Concatenation
**Problem:** Create two string variables and combine them into one string.

**Step 1:** Create the string variables
```python
first_name = "John"
last_name = "Doe"
```

**Step 2:** Combine them
```python
full_name = first_name + " " + last_name
print("Full name:", full_name)
```

**Step 3:** Try different combinations
Experiment with different names and see how they combine.

### Question 3: Mathematical Operations
**Problem:** Create variables and perform all basic math operations.

**Step 1:** Create the variables
```python
x = 20
y = 4
```

**Step 2:** Perform all operations
```python
addition = x + y
subtraction = x - y
multiplication = x * y
division = x / y
print(f"Addition: {addition}")
print(f"Subtraction: {subtraction}")
print(f"Multiplication: {multiplication}")
print(f"Division: {division}")
```

### Question 4: Variable Reassignment
**Problem:** Create a variable, then change its value using the += operator.

**Step 1:** Create the initial variable
```python
count = 5
print("Initial count:", count)
```

**Step 2:** Use += to add to it
```python
count += 3
print("After adding 3:", count)
```

**Step 3:** Try other operators
```python
count -= 2
count *= 2
print("Final count:", count)
```

### Question 5: String Repetition
**Problem:** Create a string and repeat it multiple times.

**Step 1:** Create the string
```python
greeting = "Hello! "
```

**Step 2:** Repeat it
```python
repeated = greeting * 3
print(repeated)
```

**Step 3:** Try different numbers
Experiment with different repetition counts.

### Question 6: Type Conversion
**Problem:** Convert a string number to an integer and do math with it.

**Step 1:** Create a string number
```python
age_string = "25"
```

**Step 2:** Convert to integer
```python
age = int(age_string)
```

**Step 3:** Do math with it
```python
next_year = age + 1
print(f"Next year you'll be {next_year}")
```

### Question 7: Area Calculation
**Problem:** Calculate the area of a rectangle using variables.

**Step 1:** Create the dimensions
```python
length = 8
width = 6
```

**Step 2:** Calculate the area
```python
area = length * width
print(f"Area of rectangle: {area} square units")
```

**Step 3:** Try different dimensions
Change the length and width to see different areas.

### Question 8: Percentage Calculation
**Problem:** Calculate a percentage using variables.

**Step 1:** Create the values
```python
total_points = 100
earned_points = 85
```

**Step 2:** Calculate the percentage
```python
percentage = (earned_points / total_points) * 100
print(f"You scored {percentage}%")
```

**Step 3:** Try different scores
Experiment with different earned points.

### Question 9: Temperature Conversion
**Problem:** Convert Celsius to Fahrenheit using variables.

**Step 1:** Create the Celsius temperature
```python
celsius = 25
```

**Step 2:** Convert to Fahrenheit
```python
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius}°C is {fahrenheit}°F")
```

**Step 3:** Try different temperatures
Test with different Celsius values.

### Question 10: String Length
**Problem:** Find the length of a string using the len() function.

**Step 1:** Create a string
```python
name = "Python Programming"
```

**Step 2:** Find its length
```python
length = len(name)
print(f"The string '{name}' has {length} characters")
```

**Step 3:** Try different strings
Test with strings of different lengths.

### Question 11: Modulo Operation
**Problem:** Use the modulo operator to find the remainder.

**Step 1:** Create the variables
```python
dividend = 17
divisor = 5
```

**Step 2:** Find the remainder
```python
remainder = dividend % divisor
print(f"{dividend} divided by {divisor} has remainder {remainder}")
```

**Step 3:** Try different numbers
Experiment with different dividend and divisor values.

### Question 12: Exponentiation
**Problem:** Calculate a number raised to a power.

**Step 1:** Create the base and exponent
```python
base = 2
exponent = 3
```

**Step 2:** Calculate the power
```python
result = base ** exponent
print(f"{base} to the power of {exponent} is {result}")
```

**Step 3:** Try different powers
Test with different base and exponent values.

### Question 13: Floor Division
**Problem:** Use floor division to get whole number results.

**Step 1:** Create the variables
```python
a = 10
b = 3
```

**Step 2:** Compare regular and floor division
```python
regular_division = a / b
floor_division = a // b
print(f"Regular division: {regular_division}")
print(f"Floor division: {floor_division}")
```

**Step 3:** Understand the difference
Notice how floor division gives you the whole number part.

### Question 14: String Formatting with Numbers
**Problem:** Format numbers in strings with specific decimal places.

**Step 1:** Create a decimal number
```python
price = 19.99
```

**Step 2:** Format it in a string
```python
formatted_price = f"${price:.2f}"
print(f"The price is {formatted_price}")
```

**Step 3:** Try different formatting
Experiment with different decimal places.

### Question 15: Variable Swapping
**Problem:** Swap the values of two variables.

**Step 1:** Create the variables
```python
x = 10
y = 20
print(f"Before swap: x = {x}, y = {y}")
```

**Step 2:** Swap the values
```python
x, y = y, x
print(f"After swap: x = {x}, y = {y}")
```

**Step 3:** Verify the swap
Make sure the values have actually swapped.

### Question 16: Compound Assignment
**Problem:** Use compound assignment operators to modify variables.

**Step 1:** Create a variable
```python
score = 100
```

**Step 2:** Use compound operators
```python
score += 10  # Same as score = score + 10
score -= 5   # Same as score = score - 5
score *= 2   # Same as score = score * 2
print(f"Final score: {score}")
```

**Step 3:** Understand the shorthand
Notice how these operators make code shorter.

### Question 17: String Methods
**Problem:** Use string methods to modify strings.

**Step 1:** Create a string
```python
name = "  john doe  "
```

**Step 2:** Use string methods
```python
trimmed = name.strip()  # Remove spaces
capitalized = trimmed.title()  # Capitalize words
print(f"Original: '{name}'")
print(f"Trimmed: '{trimmed}'")
print(f"Capitalized: '{capitalized}'")
```

**Step 3:** Try other methods
Experiment with other string methods like upper() and lower().

### Question 18: Number Rounding
**Problem:** Round a decimal number to a specific number of decimal places.

**Step 1:** Create a decimal number
```python
pi = 3.14159
```

**Step 2:** Round it
```python
rounded_2 = round(pi, 2)
rounded_3 = round(pi, 3)
print(f"Original: {pi}")
print(f"Rounded to 2 places: {rounded_2}")
print(f"Rounded to 3 places: {rounded_3}")
```

**Step 3:** Try different numbers
Test with different decimal numbers.

### Question 19: String Indexing
**Problem:** Access specific characters in a string using indexing.

**Step 1:** Create a string
```python
word = "Python"
```

**Step 2:** Access characters
```python
first_char = word[0]
last_char = word[-1]
print(f"First character: {first_char}")
print(f"Last character: {last_char}")
```

**Step 3:** Try different positions
Experiment with different index positions.

### Question 20: Complex Expression
**Problem:** Create a complex mathematical expression using multiple variables.

**Step 1:** Create the variables
```python
a = 5
b = 3
c = 2
```

**Step 2:** Create a complex expression
```python
result = (a + b) * c - (a - b)
print(f"({a} + {b}) * {c} - ({a} - {b}) = {result}")
```

**Step 3:** Break it down
Understand how the expression is evaluated step by step.
