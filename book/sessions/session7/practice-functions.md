# Practice Functions: Building Your First Functions

## Instructions

For each problem below, create a simple function that solves the problem. Remember to:
- Start with the simplest version first
- Test your function with the provided data
- Make sure your function does one thing well
- Use clear, descriptive names for your functions

## Problem 1: Temperature Converter

### Scenario
You're building a simple weather app that needs to convert temperatures between Celsius and Fahrenheit.

### Requirements
Create a function that converts Celsius to Fahrenheit using the formula: `F = (C × 9/5) + 32`

### Test Data
- 0°C = 32°F
- 25°C = 77°F
- 100°C = 212°F

### Your Function
```python
def celsius_to_fahrenheit(celsius):
    # Your code here
    pass
```

## Problem 2: Area Calculator

### Scenario
A construction worker needs to calculate the area of different shapes for building projects.

### Requirements
Create a function that calculates the area of a rectangle using the formula: `Area = length × width`

### Test Data
- Length: 5, Width: 3 → Area: 15
- Length: 10, Width: 7 → Area: 70
- Length: 12, Width: 8 → Area: 96

### Your Function
```python
def calculate_rectangle_area(length, width):
    # Your code here
    pass
```

## Problem 3: Simple Interest Calculator

### Scenario
A bank needs to calculate simple interest for loans and savings accounts.

### Requirements
Create a function that calculates simple interest using the formula: `Interest = Principal × Rate × Time`

### Test Data
- Principal: $1000, Rate: 5%, Time: 2 years → Interest: $100
- Principal: $5000, Rate: 3%, Time: 4 years → Interest: $600

### Your Function
```python
def calculate_simple_interest(principal, rate, time):
    # Your code here
    pass
```

## Problem 4: BMI Calculator

### Scenario
A fitness app needs to calculate Body Mass Index (BMI) to help users track their health.

### Requirements
Create a function that calculates BMI using the formula: `BMI = weight(kg) / height(m)²`

### Test Data
- Weight: 70 kg, Height: 1.75 m → BMI: 22.86
- Weight: 60 kg, Height: 1.65 m → BMI: 22.04

### Your Function
```python
def calculate_bmi(weight, height):
    # Your code here
    pass
```

## Problem 5: Text Formatter

### Scenario
A website needs to format user names consistently.

### Requirements
Create a function that takes a first name and last name and returns a properly formatted full name.

### Test Data
- First: "john", Last: "doe" → "John Doe"
- First: "MARY", Last: "SMITH" → "Mary Smith"
- First: "alice", Last: "JOHNSON" → "Alice Johnson"

### Your Function
```python
def format_full_name(first_name, last_name):
    # Your code here
    pass
```

## Problem 6: Shopping Calculator

### Scenario
A store needs to calculate the total cost of items including tax.

### Requirements
Create a function that calculates the total cost including tax.

### Test Data
- Items: $50, Tax rate: 8% → Total: $54.00
- Items: $100, Tax rate: 10% → Total: $110.00
- Items: $25, Tax rate: 6% → Total: $26.50

### Your Function
```python
def calculate_total_with_tax(item_cost, tax_rate):
    # Your code here
    pass
```

## Problem 7: Number Checker

### Scenario
A game needs to check if a number is even or odd.

### Requirements
Create a function that returns "even" if the number is even, "odd" if it's odd.

### Test Data
- 4 → "even"
- 7 → "odd"
- 12 → "even"
- 15 → "odd"

### Your Function
```python
def check_even_or_odd(number):
    # Your code here
    pass
```

## Problem 8: Simple Password Checker

### Scenario
A website needs to check if a password is long enough.

### Requirements
Create a function that returns True if the password is at least 8 characters long, False otherwise.

### Test Data
- "password123" → True
- "short" → False
- "mypassword" → True
- "123" → False

### Your Function
```python
def is_password_long_enough(password):
    # Your code here
    pass
```

## Testing Your Functions

After writing each function, test it with the provided data:

```python
# Example testing
result = celsius_to_fahrenheit(25)
print(f"25°C = {result}°F")  # Should output: 25°C = 77.0°F
```

## Building More Complex Functions

Once you've completed the basic functions, try combining them:

### Example: Complete Temperature Converter
```python
def convert_temperature(value, from_unit, to_unit):
    if from_unit == "celsius" and to_unit == "fahrenheit":
        return celsius_to_fahrenheit(value)
    elif from_unit == "fahrenheit" and to_unit == "celsius":
        # You could add a fahrenheit_to_celsius function here
        return "Not implemented yet"
    else:
        return "Invalid conversion"
```

### Example: Complete Shopping Calculator
```python
def calculate_shopping_total(item_costs, tax_rate):
    subtotal = 0
    for cost in item_costs:
        subtotal = subtotal + cost
    
    total = calculate_total_with_tax(subtotal, tax_rate)
    return subtotal, total
```

## Reflection Questions

After completing all functions, think about:

1. **Which function was easiest to write? Why?**
2. **Which function was most challenging? What made it difficult?**
3. **How did you test your functions?**
4. **What would you do differently next time?**
5. **How could you make your functions more useful?**

## Next Steps

Once you've mastered these basic functions, you'll be ready to move on to more advanced function concepts in the next session, including:
- Functions with more complex logic
- Functions that work with different types of data
- Functions that call other functions
- Better ways to organize and structure your code